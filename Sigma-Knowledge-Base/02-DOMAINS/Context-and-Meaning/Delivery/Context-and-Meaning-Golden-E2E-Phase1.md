# Context & Meaning --- Golden E2E, Phase 1 DoD & Runbook

**Status:** v0.1 execution baseline

## 1. Goal

Prove that C&M can turn a real domain change into trusted operational
meaning with evidence and lifecycle --- without becoming an autonomous
recommendation engine.

------------------------------------------------------------------------

## 2. Recommended Golden E2E

Reference scenario:

> **Operation X is delayed. An explicitly related resource/force no
> longer overlaps the new execution window.**

The exact second domain must be selected according to real available
contracts; do not invent a source solely for the demo.

``` text
Operations changes Operation X timeline
             ↓
       OperationChanged
             ↓
         Event Router
             ↓
    resolve Operation X context
             ↓
 retrieve current plan + explicit relationship
             ↓
 retrieve second-domain availability/state
             ↓
        EvidenceBundle
             ↓
      versioned overlap rule
             ↓
       Candidate Signal
             ↓
        Evidence Gate
             ↓
 OperationalSignal ACTIVE
             ↓
       SignalCreated event
             ↓
   Commander Experience consumes
             ↓
 source fact changes / condition disappears
             ↓
          re-evaluate
             ↓
 OperationalSignal RESOLVED
```

------------------------------------------------------------------------

## 3. Why this slice

It proves:

-   event-driven backbone;
-   multi-domain evidence;
-   explicit relationship;
-   rule-derived meaning;
-   evidence trace;
-   lifecycle;
-   consumer contract;
-   re-evaluation.

It does not require AI to prove the product.

------------------------------------------------------------------------

## 4. Phase 1 Scope

### In

-   Operations event input.
-   One additional real factual input if required.
-   Event Router.
-   Context Resolver.
-   EvidenceBundle.
-   Two Signal types maximum initially.
-   deterministic/rule-derived synthesis.
-   Evidence Gate.
-   conflict behavior.
-   Signal Store/lifecycle.
-   Signal events.
-   evidence API.
-   one real Commander Experience consumer.
-   evaluation fixtures.

### Out

-   general autonomous agent;
-   broad enterprise source ingestion;
-   recommendation engine;
-   commander-specific ranking;
-   arbitrary AI confidence;
-   large Signal taxonomy;
-   prediction;
-   automatic resolution of conflicts;
-   LLM dependency for core slice.

------------------------------------------------------------------------

## 5. Candidate Initial Signal Types

Choose based on real data availability. Good candidates:

1.  `EXECUTION_WINDOW_MISMATCH`
2.  `DEPENDENCY_IMPACT`
3.  `SOURCE_CONFLICT`

Phase 1 should implement only the smallest set needed to prove the
architecture.

------------------------------------------------------------------------

## 6. Phase 1 Definition of Done

-   [ ] Producer contracts documented.
-   [ ] Versioned event envelope.
-   [ ] Idempotent event consumption.
-   [ ] Out-of-order behavior tested.
-   [ ] Context Resolver uses explicit IDs/relationships.
-   [ ] EvidenceBundle implemented.
-   [ ] ≥2 Signal types or 1 strong Signal type + conflict path.
-   [ ] Deterministic/rule-derived synthesis works.
-   [ ] Rules are versioned.
-   [ ] Evidence Gate rejects unsupported candidate.
-   [ ] Material Signal persisted.
-   [ ] Signal can change/resolve.
-   [ ] Deduplication prevents duplicate noise.
-   [ ] Evidence retrievable from Signal.
-   [ ] Conflict is preserved when no authority rule exists.
-   [ ] Signal lifecycle events published.
-   [ ] One real consumer uses Signal contract.
-   [ ] Event-to-Signal latency observable.
-   [ ] Evaluation fixtures include expected Signal and expected
    no-Signal.
-   [ ] Security/classification approved for synthesized output.

------------------------------------------------------------------------

## 7. Exception Runbook

  -----------------------------------------------------------------------
  Condition               Behavior                Never do
  ----------------------- ----------------------- -----------------------
  Duplicate domain event  idempotent processing   duplicate Signal

  Out-of-order event      version/time-aware      blindly roll state
                          re-evaluation           backward

  Required evidence       Gate rejection/degraded invent evidence
  unavailable             state per Signal policy 

  Evidence stale          expose staleness; Gate  hide age
                          policy                  

  Two sources conflict    authoritative rule or   let AI choose truth
                          unresolved conflict     

  Unknown relationship    no impact inference     infer relation from
                          requiring that          wording alone
                          relationship            

  Rule errors             no material Signal +    publish partially
                          alert                   evaluated Signal

  AI output unsupported   Gate reject             publish because text
                                                  sounds plausible

  Signal duplicate        update/no-op            create notification
                                                  noise

  Underlying condition    mark Signal resolved    delete history
  resolves                                        

  Source correction       re-evaluate affected    preserve obsolete
                          Signals                 meaning as active

  Signal store failure    fail/retry              emit successful
                          transactionally         SignalCreated without
                                                  persistence

  Consumer unavailable    retain Signal; event    lose business object
                          retry policy            
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 8. Evidence Gate Test Cases

### Pass

All required facts, explicit relationship, compatible times, versioned
rule.

### Reject --- Missing evidence

Resource availability cannot be retrieved.

### Reject --- Unsupported relation

Operation and resource exist but no allocation/dependency relationship
exists.

### Conflict

Two availability claims disagree and no authority rule exists. Produce
conflict representation/Signal if material; do not produce definitive
mismatch based on chosen claim.

### Re-evaluation

Availability changes and overlap returns; existing Signal resolves.

------------------------------------------------------------------------

## 9. Evaluation Set

Maintain version-controlled cases:

``` text
fixtures/
  should_signal/
  should_not_signal/
  conflicts/
  missing_evidence/
  lifecycle/
```

Each fixture defines:

-   input facts/events;
-   expected relationships;
-   expected Signal type or no-Signal;
-   expected evidence;
-   expected lifecycle state;
-   prohibited unsupported claims.

------------------------------------------------------------------------

## 10. Phase 1 Metrics

-   Evidence Gate pass/reject.
-   unsupported Signal rate.
-   duplicate Signal rate.
-   event-to-Signal latency.
-   \% Signals with complete evidence trace.
-   re-evaluation success.
-   conflict visibility.
-   user validation of Signal relevance.

Do **not** use Signal volume as a success metric.

------------------------------------------------------------------------

## 11. On-demand Investigation --- Phase 1/2 Gate

After trusted Signals work, add:

``` text
"Why is this Signal active?"
        ↓
retrieve Signal + EvidenceBundle
        ↓
bounded explanation
        ↓
answer with evidence
```

Broader natural-language orchestration should follow only after domain
query contracts are stable.

------------------------------------------------------------------------

## 12. AI Introduction Gate

AI-assisted synthesis should be added only when:

1.  a valuable Signal/explanation cannot be expressed adequately through
    deterministic/rule logic;
2.  evidence contract is stable;
3.  evaluation fixtures exist;
4.  unsupported-claim measurement exists;
5.  security/model access is approved;
6.  fallback behavior is defined.

AI is an implementation capability, not the product definition.

------------------------------------------------------------------------

## 13. Handoff Questions the Team Must Close

-   Which real operation/use case is the first slice?
-   What is the second factual domain, if needed?
-   Which 1--2 Signal types?
-   What exact rule makes each Signal true?
-   What makes it resolve?
-   Which evidence is mandatory?
-   Which source is authoritative for each fact?
-   Which Commander Experience surface consumes it?
-   What latency is actually required?
-   How will users validate relevance/correctness?


## 14. Expansion Sequence After Phase 1

Only after the first Signal is proven end-to-end:

1. **Second Signal type** using as much of the same pipeline as possible.
2. **Lifecycle hardening** — changed / resolved / superseded patterns.
3. **Conflict handling** where a real use case requires it.
4. **Geography integration** for a cross-domain spatial Signal.
5. **On-demand investigation** over existing trusted Signals/evidence.
6. **AI-assisted synthesis** only for cases that rules cannot express well.

The test for every expansion is reuse: the next capability should reuse the same contracts, evidence model and lifecycle rather than create a parallel path.
