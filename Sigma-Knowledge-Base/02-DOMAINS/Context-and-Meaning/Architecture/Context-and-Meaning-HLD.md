# Context & Meaning --- High Level Design

**Status:** v0.1 --- Company Brain / Handoff\
**Architecture:** Event-driven synthesis service + on-demand
investigation\
**Canonical business object:** Operational Signal

------------------------------------------------------------------------

## 1. Architectural Intent

Context & Meaning consumes domain-owned facts and changes and produces
evidence-backed operational meaning.

Target:

``` text
Domain Events / Queries
        ↓
Context Resolution
        ↓
Relationship / Conflict Evaluation
        ↓
Evidence Assembly
        ↓
Synthesis
        ↓
Evidence Gate
        ↓
Operational Signal Lifecycle
```

It must not become a hidden replacement for source systems or Commander
Experience.

------------------------------------------------------------------------

## 2. Target Architecture

``` text
                 DOMAIN PRODUCERS
 Operations     Geography     Other approved domains
     |              |                    |
     +------ events / query contracts ---+
                    |
                    v
          +----------------------+
          | EVENT ROUTER         |
          | relevance / routing  |
          +----------+-----------+
                     |
                     v
          +----------------------+
          | CONTEXT RESOLVER     |
          | subjects / relations |
          | time / dependencies  |
          +----------+-----------+
                     |
          +----------+-----------+
          |                      |
          v                      v
 RELATIONSHIP EVALUATOR    CONFLICT DETECTOR
          |                      |
          +----------+-----------+
                     v
             EVIDENCE ASSEMBLER
                     |
                     v
          +----------------------+
          | SYNTHESIS ENGINE     |
          | deterministic        |
          | rules                |
          | AI-assisted          |
          +----------+-----------+
                     |
                     v
               EVIDENCE GATE
                     |
          candidate accepted?
             /              \
           no                yes
           |                  |
      telemetry           SIGNAL SERVICE
                              |
                    +---------+---------+
                    |                   |
                    v                   v
               Signal Store       Signal Events
                    |
                    v
             Query / Investigation API
                    |
             Commander Experience

On-demand:
Commander Experience → C&M Orchestrator → domain queries → Evidence → Synthesis
```

------------------------------------------------------------------------

## 3. Components

  ---------------------------------------------------------------------------------------------
  Component               Responsibility                                Out of scope
  ----------------------- --------------------------------------------- -----------------------
  Event Router            consume/filter relevant domain changes        semantic synthesis

  Context Resolver        identify affected subjects, relationships,    invent relationships
                          time context                                  

  Relationship Evaluator  evaluate known dependencies/relations         spatial math owned by
                                                                        Geography

  Conflict Detector       identify incompatible claims and apply        arbitrary truth
                          authoritative rules                           resolution

  Evidence Assembler      fetch/package source facts, provenance,       change source facts
                          versions                                      

  Deterministic Evaluator exact factual/change conditions               semantic AI inference

  Rule Engine             versioned derived rules                       opaque business logic

  AI Synthesis            concise semantic synthesis from grounded      unsupported facts
                          evidence                                      

  Evidence Gate           validate grounding/completeness/conflict      commander priority
                          constraints                                   

  Signal Service          create/update/deduplicate/resolve/supersede   Commander UX
                          Signals                                       

  Signal Store            persist material Signal lifecycle             raw enterprise data
                                                                        lake

  On-demand Orchestrator  decompose multi-domain investigation          domain-specific
                                                                        computation

  API/Event Layer         consumer contracts                            screen-specific
                                                                        presentation
  ---------------------------------------------------------------------------------------------

------------------------------------------------------------------------

## 4. Storage Model

### Signal Store

Persists material Operational Signals and lifecycle state.

### Evidence References / Snapshot

Store sufficient evidence references and, where required for
reconstruction, immutable decision/synthesis-relevant fact snapshots or
source versions.

Do not copy full source systems by default.

### Conflict Store / Embedded Conflict

Conflicts may be embedded in Signal evidence or persisted as first-class
objects when reuse/lifecycle justifies it.

### Rule / Configuration Registry

Versioned:

-   rule definitions;
-   Signal type configuration;
-   authoritative source rules;
-   materiality thresholds with defined semantics;
-   model/prompt/config references for AI-assisted synthesis.

------------------------------------------------------------------------

## 5. Event-driven Flow

``` text
Domain Event
   ↓
validate schema / version
   ↓
Event Router
   ↓
resolve affected context
   ↓
fetch required current facts
   ↓
evaluate relationships/conflicts
   ↓
build EvidenceBundle
   ↓
deterministic/rule/AI synthesis
   ↓
Evidence Gate
   ↓
deduplicate / compare existing Signal
   ↓
create | update | resolve | supersede | no-op
   ↓
publish Signal event
```

------------------------------------------------------------------------

## 6. On-demand Flow

``` text
Question / investigation request
        ↓
C&M Orchestrator
        ↓
intent + required domain questions
        ├── Operations query
        ├── Geography spatial query
        └── other approved domain query
        ↓
EvidenceBundle
        ↓
Synthesis
        ↓
grounding/evidence validation
        ↓
Answer + evidence
```

On-demand answers do not automatically become persisted Signals.
Persistence requires Signal materiality/lifecycle semantics.

------------------------------------------------------------------------

## 7. Evidence Bundle

Suggested internal contract:

``` yaml
EvidenceBundle:
  bundle_id: string
  subject_refs: []
  time_context: object
  facts:
    - fact_id: string
      domain: string
      source_ref: string
      value: object
      observed_at: datetime?
      source_updated_at: datetime?
      version: string?
  relationships: []
  conflicts: []
  unavailable_inputs: []
  assembled_at: datetime
```

Evidence is the boundary between data retrieval and synthesis.

------------------------------------------------------------------------

## 8. Synthesis Pipeline

### Deterministic

Directly maps explicit state/change to a candidate.

### Rule-derived

``` text
facts + explicit relationship + versioned rule → candidate
```

### AI-assisted

``` text
EvidenceBundle
    ↓
bounded synthesis instruction
    ↓
structured candidate
    ↓
claim/evidence validation
    ↓
Evidence Gate
```

AI output should be structured before becoming a Signal.

------------------------------------------------------------------------

## 9. Evidence Gate

Candidate validation may include:

-   all required evidence exists;
-   references resolve;
-   evidence time is compatible with claim;
-   no unsupported entity introduced;
-   required source is not unavailable;
-   conflict is represented;
-   claim type is allowed for inference class;
-   rule/model/config version exists;
-   materiality conditions are met.

Failed candidates are observable but do not become material Signals.

------------------------------------------------------------------------

## 10. Conflict Resolution Architecture

``` text
Claim A + Claim B
       ↓
Conflict Detector
       ↓
Authoritative Rule Registry?
       ├── yes → deterministic resolution + provenance
       └── no  → unresolved Conflict
                     ↓
             synthesis may produce
             conflict Signal
```

Authoritative rules are explicit configuration/contracts, not model
judgment.

------------------------------------------------------------------------

## 11. Signal Lifecycle

``` text
candidate
   ↓
deduplication key / semantic match
   ↓
new? ───── yes ─→ ACTIVE
 |
 no
 ↓
same meaning? → update last_evaluated_at / evidence
changed meaning? → CHANGED or SUPERSEDE
underlying impact gone? → RESOLVED
replacement Signal? → SUPERSEDED
```

Exact deduplication semantics are an open implementation decision and
must be testable.

------------------------------------------------------------------------

## 12. Initial API Surface

``` text
GET  /v1/signals/{signal_id}
GET  /v1/signals?subject_ref=...
POST /v1/investigate
GET  /v1/signals/{signal_id}/evidence
GET  /v1/conflicts/{conflict_id}        # if conflicts become first-class
```

Internal/producer interfaces may include event subscriptions rather than
public write APIs.

------------------------------------------------------------------------

## 13. Signal Events

Candidate initial vocabulary:

``` text
OperationalSignalCreated
OperationalSignalChanged
OperationalSignalResolved
OperationalSignalSuperseded
ConflictDetected
ConflictResolved
```

Signal events include IDs, subject refs, lifecycle state, timestamps and
version. Consumers fetch full evidence when required.

------------------------------------------------------------------------

## 14. Domain Integration

### Operations

Consumes:

-   operation/activity changes;
-   plan vs actual;
-   dependencies;
-   factual artifact/entity statuses.

Does not overwrite Operations truth.

### Geography

Calls deterministic spatial capabilities when a spatial fact is
required.

C&M must not duplicate `WITHIN`, `INTERSECTS`, distance, heatmap or
other Geography logic.

### Commander Experience

Consumes Signals and evidence. Owns role-aware relevance, attention
priority, presentation and decision/action UX.

------------------------------------------------------------------------

## 15. Consistency

C&M operates over multiple independently updated domains. Perfect global
transactional consistency is not assumed.

Every Signal must therefore preserve:

-   evidence timestamps;
-   source versions where available;
-   synthesis time;
-   unavailable inputs;
-   conflicts;
-   last evaluation time.

------------------------------------------------------------------------

## 16. Failure Semantics

  -----------------------------------------------------------------------
  Condition                           Behavior
  ----------------------------------- -----------------------------------
  Domain event duplicated             idempotent processing

  Event out of order                  use domain version/source time;
                                      re-evaluate safely

  Required evidence unavailable       no Signal or explicit
                                      degraded/unknown candidate
                                      according to Signal type

  Optional evidence unavailable       mark incompleteness; Gate decides

  Conflict without authority rule     preserve conflict

  Rule failure                        no material Signal; observable
                                      error

  AI synthesis timeout/failure        retry/fallback according to class;
                                      never fabricate

  AI unsupported claim                Gate rejection

  Signal store unavailable            processing must not claim
                                      successful persistence/event
                                      publication

  Existing Signal duplicate           deduplicate/update rather than
                                      create noise

  Source fact corrected               re-evaluate affected Signals
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 17. Security

Synthesized meaning can be more sensitive than individual facts.

Requirements:

-   propagate identity/access context where domain fetch requires it;
-   enforce classification rules on evidence and Signal;
-   prevent unauthorized evidence disclosure;
-   define whether a consumer can see Signal statement but not all
    evidence;
-   audit sensitive investigation queries;
-   govern model access to classified evidence.

------------------------------------------------------------------------

## 18. Observability

### Pipeline

-   event lag;
-   events routed/dropped;
-   contexts resolved;
-   candidates generated;
-   Evidence Gate pass/reject;
-   Signal create/change/resolve;
-   deduplication rate.

### Trust

-   missing evidence;
-   conflict count;
-   unsupported claim rejection;
-   stale evidence;
-   AI-assisted grounding failures.

### Performance

-   event-to-Signal latency;
-   domain fetch latency;
-   synthesis latency;
-   investigation latency.

------------------------------------------------------------------------

## 19. Evaluation Architecture

Before broad rollout, maintain an evaluation set of representative
scenarios:

-   expected Signal;
-   expected no-Signal;
-   conflict;
-   missing evidence;
-   changed evidence;
-   resolved Signal;
-   AI-assisted synthesis examples.

Evaluation should measure correctness/relevance and unsupported
inference, not only language quality.

------------------------------------------------------------------------

## 20. Evolution

### Phase 1 --- Trusted Signal Foundation

-   Operations as primary input.
-   one additional domain where needed.
-   small Signal taxonomy.
-   deterministic + rule-derived first.
-   evidence bundle/gate.
-   lifecycle/deduplication.
-   one real Commander Experience consumer.

### Phase 2 --- Cross-domain Expansion

-   Geography integration.
-   richer conflict handling.
-   more Signal types.
-   on-demand investigation.
-   improved materiality.

### Phase 3 --- AI-assisted Meaning

-   bounded AI-assisted synthesis for cases rules cannot express well.
-   systematic evaluation.
-   richer explanation and continuity.

AI is not a prerequisite for proving the product contract.

------------------------------------------------------------------------

## 21. Architecture Guardrails

1.  No domain truth copied into C&M as a competing source.
2.  No spatial computation duplicated from Geography.
3.  No commander-specific priority in Signal core.
4.  No arbitrary AI confidence.
5.  No Signal without evidence.
6.  No silent conflict resolution.
7.  No persistence of every candidate.
8.  No LLM call for every domain event.
9.  No on-demand answer automatically persisted.
10. No new Signal type without evaluation cases.

------------------------------------------------------------------------

## 22. Phase 1 Technical DoD

-   versioned input contract;
-   idempotent event processing;
-   Context Resolver for chosen scenario;
-   EvidenceBundle contract;
-   ≥2 Signal types;
-   deterministic/rule-derived pipeline;
-   Evidence Gate;
-   Signal lifecycle persistence;
-   evidence retrieval;
-   Signal events;
-   duplicate/out-of-order handling;
-   conflict behavior;
-   observability;
-   one real consumer;
-   evaluation fixtures.
