# Context & Meaning --- Architecture Decision Record

**Status:** Accepted baseline decisions

## ADR-01 --- Canonical output is Operational Signal

**Decision:** C&M produces evidence-backed operational meaning, not only
raw relationships and not commander recommendations.

**Boundary:** `Facts → Meaning` belongs here.
`Meaning → commander-specific priority/decision UX` belongs to Commander
Experience.

------------------------------------------------------------------------

## ADR-02 --- Material Signals are persisted

Candidate correlations are ephemeral. A Signal that becomes a meaningful
operational object is persisted and receives lifecycle.

Statuses: `active`, `changed`, `resolved`, `superseded`.

------------------------------------------------------------------------

## ADR-03 --- Hybrid synthesis with Evidence Gate

Support deterministic, rule-derived and AI-assisted synthesis.

AI-assisted synthesis is allowed only over grounded evidence and must
pass an Evidence Gate.

No arbitrary percentage confidence.

------------------------------------------------------------------------

## ADR-04 --- Commander Experience owns attention prioritization

C&M may calculate/expose impact and materiality attributes. It does not
set `commander_priority` or homepage placement.

------------------------------------------------------------------------

## ADR-05 --- Hybrid operating model with Event-driven backbone

Continuous event-driven processing discovers new meaning.

On-demand processing supports investigation and questions.

> **Continuous synthesis discovers meaning. On-demand synthesis
> investigates meaning.**

------------------------------------------------------------------------

## ADR-06 --- Preserve conflicts

When sources disagree, preserve the conflict unless an explicit
authoritative rule determines which source owns that fact.

The model does not decide truth.

------------------------------------------------------------------------

## ADR-07 --- Conflict can itself be operational meaning

An unresolved contradiction that affects interpretation may generate a
Signal.

------------------------------------------------------------------------

## ADR-08 --- Cross-domain orchestration belongs to C&M

For multi-domain questions, C&M decomposes the request and calls domain
capabilities.

Domain-specific computation remains with its owner; e.g. Geography
performs spatial computation.

------------------------------------------------------------------------

## ADR-09 --- AI is not invoked for every event

Use event routing, context resolution, deterministic checks and rules to
reduce scope before expensive/semantic synthesis.

------------------------------------------------------------------------

## ADR-10 --- Evidence is a first-class contract

Synthesis receives a structured EvidenceBundle. A Signal must retain
sufficient references/versions/time metadata to explain and reconstruct
its basis.

------------------------------------------------------------------------

## ADR-11 --- No automatic persistence of on-demand answers

An investigation answer becomes a persisted Signal only if it
independently satisfies Signal materiality/lifecycle rules.

------------------------------------------------------------------------

## ADR-12 --- Explicit uncertainty over false certainty

Missing input, stale evidence and unresolved conflict are represented
explicitly. They are not hidden to create a cleaner narrative.

------------------------------------------------------------------------

## Decision Summary

  Topic                        Baseline
  ---------------------------- ------------------------------------
  Canonical output             Operational Signal
  Persistence                  material Signals only
  Synthesis                    deterministic + rules + bounded AI
  Grounding                    Evidence Gate
  Priority                     Commander Experience
  Runtime                      event-driven + on-demand
  Backbone                     event-driven
  Conflict                     preserve unless authority rule
  Cross-domain orchestration   C&M
  Spatial compute              Geography
  Domain truth                 source domains


---

## ADR-13 — Phase 1 proves one Signal only

**Decision:** The first implementation proves exactly one material Operational Signal end-to-end.

Phase 1 is not a platform build and not a Signal taxonomy exercise.

The first Signal must prove:

```text
real domain change
    ↓
context / relationship
    ↓
evidence
    ↓
deterministic or rule-derived meaning
    ↓
Evidence Gate
    ↓
material Signal
    ↓
Commander Experience
    ↓
re-evaluation / resolution
```

**Expansion gate:** Additional Signal types, conflict infrastructure, generic orchestration and AI-assisted synthesis are added only after the first Signal proves real value and reuse.
