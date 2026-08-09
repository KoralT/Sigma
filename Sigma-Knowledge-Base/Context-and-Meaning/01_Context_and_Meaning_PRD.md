# Context & Meaning --- Product Requirements Document

**Status:** v0.1 --- Company Brain / Handoff\
**Domain question:** **מה המשמעות של הדברים ביחד?**\
**Canonical output:** Operational Signal\
**Operating model:** Event-driven backbone + On-demand investigation\
**Date:** August 2026

------------------------------------------------------------------------

## 1. Executive Summary

Context & Meaning היא שכבת הסינתזה של SIGMA. תפקידה לחבר עובדות ושינויים
ממספר דומיינים, להבין קשרים והשפעות ביניהם, לזהות סתירות, להרכיב
evidence ולהפיק **Operational Signals** אמינים וניתנים להסבר.

היא אינה Source of Truth של הדומיינים ואינה שכבת ה-Commander UX.

עקרון הליבה:

> **Context & Meaning owns operational meaning, not domain truth and not
> commander decisions.**

המערכת מקבלת Domain Facts / Events, פותרת את ההקשר הרלוונטי, בוחנת
relationships/dependencies, מרכיבה evidence ומייצרת Signal שמסביר:

1.  מה השתנה?
2.  על מה זה משפיע?
3.  למה זה משמעותי?
4.  מה תומך בטענה?
5.  מה לא ידוע / חלקי / סותר?

Commander Experience אחראי לשאלה אחרת: מה רלוונטי **למפקד הזה עכשיו**,
איך לתעדף ולהציג, ומהי חוויית החקירה/החלטה/פעולה.

------------------------------------------------------------------------

## 2. Problem

המידע הדרוש להבנת מצב מבצעי מפוזר בין דומיינים:

-   Operations --- תוכנית, פעילות, dependencies ומצב מבצעי עובדתי.
-   Geography --- facts ויחסים מרחביים.
-   מקורות מקצועיים נוספים --- סטטוסים, אישורים, סד"כ, דיווחים וידע
    בהתאם לחוזים העתידיים.

הבעיה אינה רק גישה למידע. גם כאשר העובדות זמינות, המשתמש נדרש לבצע
ידנית:

-   correlation בין שינויים;
-   הבנת dependencies;
-   זיהוי conflict;
-   חיבור עובדות ממקורות שונים;
-   הערכת impact;
-   בדיקת evidence;
-   הבנת מה השתנה מאז התמונה הקודמת.

ללא שכבה משותפת, כל consumer עלול לממש synthesis משלו ולהגיע למשמעות
שונה מאותן עובדות.

------------------------------------------------------------------------

## 3. Product Thesis

``` text
Domain Facts
     ↓
Relationships + Context
     ↓
Evidence-backed Synthesis
     ↓
Operational Meaning
```

Context & Meaning אינו "AI שעונה על הכול".

הוא Domain Product עם contracts, lifecycle ו-guardrails ברורים.

------------------------------------------------------------------------

## 4. Domain Boundaries

  -----------------------------------------------------------------------
  Domain                  השאלה                   Ownership
  ----------------------- ----------------------- -----------------------
  Operations              מה מתוכנן ומתבצע?       Operation, plan,
                                                  activities,
                                                  dependencies, factual
                                                  operational state

  Geography               מה קורה במרחב?          spatial facts,
                                                  relationships and
                                                  deterministic spatial
                                                  computation

  Context & Meaning       מה המשמעות של הדברים    cross-domain synthesis,
                          ביחד?                   impact, conflict,
                                                  evidence and
                                                  Operational Signals

  Commander Experience    מה המפקד צריך להבין     role relevance,
                          ולעשות?                 attention
                                                  prioritization,
                                                  presentation,
                                                  investigation,
                                                  decision/action
  -----------------------------------------------------------------------

### Boundary example

Operations:

> Operation X shifted by four hours.

Professional source:

> Force Z is unavailable in the new window.

Context & Meaning:

> The schedule change created a mismatch between Operation X's execution
> window and Force Z availability.

Commander Experience:

> Determines whether/how this Signal should appear to a specific
> commander.

------------------------------------------------------------------------

## 5. Canonical Output --- Operational Signal

Context & Meaning's primary persisted business object is a **material
Operational Signal**.

A Signal is not merely a copied fact. It is a traceable statement about
the meaning or impact of one or more facts in context.

Minimum semantics:

``` yaml
OperationalSignal:
  signal_id: string
  subject_refs: []
  signal_type: string
  statement: string
  impact: object
  evidence_refs: []
  inference_class: deterministic | rule_derived | ai_assisted
  uncertainty: object?
  conflict_refs: []
  first_detected_at: datetime
  last_evaluated_at: datetime
  status: active | changed | resolved | superseded
```

Detailed schema is defined in
`05_Context_and_Meaning_Operational_Signal_Schema.md`.

------------------------------------------------------------------------

## 6. Signal Lifecycle

Not every correlation becomes a persistent Signal.

``` text
Domain change
    ↓
Affected-context resolution
    ↓
Candidate Signal
    ↓
Evidence Gate
    ↓
Materiality evaluation
    ├── not material → discard / telemetry
    └── material
          ↓
     Operational Signal
          ↓
 active → changed → resolved / superseded
```

### Persistence rule

Persist a Signal when it becomes a meaningful operational object that
must support continuity, consumption, investigation or later
reconstruction.

Do not persist every intermediate inference.

------------------------------------------------------------------------

## 7. Synthesis Model

Context & Meaning supports three synthesis classes.

### Level 1 --- Deterministic

Examples:

-   status changed;
-   deadline passed;
-   dependency state changed;
-   approval changed;
-   a spatial relation returned by Geography changed.

These are reproducible from explicit facts.

### Level 2 --- Rule-derived

Example:

``` text
Operation window changed
+
Force availability window does not overlap
+
Force is allocated to Operation
=
Potential execution mismatch
```

The rule must be explicit and versioned.

### Level 3 --- AI-assisted synthesis

Used where multiple facts/context require semantic synthesis into
concise operational meaning.

AI-assisted output must pass the Evidence Gate and retain traceability
to source facts.

### Guardrail

AI may synthesize meaning; it may not silently convert unsupported
inference into domain truth.

------------------------------------------------------------------------

## 8. Evidence Gate

Before a Candidate Signal becomes material, the system evaluates whether
the statement is sufficiently grounded.

The gate considers:

-   evidence presence;
-   source traceability;
-   temporal relevance;
-   source completeness;
-   required relationships;
-   conflicts;
-   inference class;
-   rule/model version;
-   whether the conclusion exceeds what the evidence supports.

There is no arbitrary `AI confidence = 83%`.

If uncertainty is represented, its semantics must be explicitly defined.

------------------------------------------------------------------------

## 9. Conflict Handling

Default policy:

> **Preserve conflict; do not resolve truth unless an authoritative rule
> exists.**

### With authoritative rule

If domain ownership says:

``` text
Force availability → Force Source authoritative
```

the conflict may be deterministically resolved according to that
contract.

### Without authoritative rule

Represent both claims:

``` yaml
Conflict:
  conflict_id: string
  subject_ref: string
  claim_a:
    value: ...
    source: ...
    observed_at: ...
  claim_b:
    value: ...
    source: ...
    observed_at: ...
  resolution: unresolved
```

An unresolved conflict may itself create an Operational Signal.

Example:

> Conflicting status for Force Z prevents a reliable assessment of its
> alignment with the operation window.

------------------------------------------------------------------------

## 10. Materiality vs Commander Priority

Context & Meaning may provide impact/materiality attributes:

``` yaml
impact:
  affected_subjects: []
  scope: operation | multi_operation | other
  time_sensitivity: immediate | near_term | informational
  decision_dependency: true | false
  change_magnitude: optional_defined_semantics
```

It does **not** own:

``` yaml
show_on_homepage: true
commander_priority: 1
```

Commander Experience owns role-aware attention prioritization.

> Context & Meaning asks: **What matters operationally?**\
> Commander Experience asks: **What matters to this commander now?**

------------------------------------------------------------------------

## 11. Operating Modes

### 11.1 Event-driven backbone

Continuous synthesis discovers new meaning when domain state changes.

``` text
Domain Event
    ↓
Event Routing
    ↓
Affected Context Resolution
    ↓
Relationship Evaluation
    ↓
Candidate Signal
    ↓
Evidence Gate
    ↓
Material Signal / no material signal
```

Not every event invokes an LLM. Deterministic routing and evaluation
should narrow the candidate scope first.

### 11.2 On-demand investigation

Used for questions and drill-down:

``` text
Question
    ↓
Intent / decomposition
    ├── Operations
    ├── Geography
    └── other approved domains
    ↓
Evidence Assembly
    ↓
Synthesis
    ↓
Answer + Evidence
```

Principle:

> **Continuous synthesis discovers meaning. On-demand synthesis
> investigates meaning.**

------------------------------------------------------------------------

## 12. Context Resolution

Before synthesis, the system must identify the relevant context:

-   Operation / Activity / subject;
-   related entities;
-   explicit dependencies;
-   temporal window;
-   spatial context when required;
-   current vs historical state;
-   source ownership.

Context resolution must use known identifiers/relationships/contracts.
It must not invent relationships solely because two entities appear
semantically similar.

------------------------------------------------------------------------

## 13. Geography Orchestration

For multi-domain natural-language questions, Context & Meaning is the
orchestrator.

Example:

``` text
"Which forces available tonight are within 5 km of Operation X?"
       ↓
Context & Meaning
       ├── Operations / Force: availability
       └── Geography: within 5 km
       ↓
combine factual results
       ↓
answer / Signal with evidence
```

Geography owns the spatial computation. Context & Meaning owns the
cross-domain combination.

------------------------------------------------------------------------

## 14. Reference Scenarios

### RS-01 --- Schedule × Force Availability

Operation X moves by four hours. Force Z remains allocated but its
authoritative availability no longer overlaps the new execution window.

**Signal:** schedule change created an execution-window mismatch with
Force Z.

Evidence includes operation timeline, allocation relationship and
availability source.

### RS-02 --- Schedule × Geography

Operation timing changes. A spatial restriction is valid during the new
window and intersects the relevant route/area.

Geography returns the spatial fact. Context & Meaning connects the
timing change and spatial result.

### RS-03 --- Dependency Impact

Activity A is delayed. Activity B has an explicit `DEPENDS_ON`
relationship to A.

A rule-derived Signal may state that B's planned execution is
affected/potentially affected according to the dependency semantics.

### RS-04 --- Source Conflict

Two sources report incompatible factual states and no authoritative
resolution rule exists.

The conflict is preserved and may become a Signal rather than being
silently resolved.

### RS-05 --- On-demand Investigation

Commander asks: "Why is this operation affected?"

Context & Meaning retrieves the Signal, evidence, related facts and
changes and returns an evidence-backed explanation.

### RS-06 --- Resolved Signal

Underlying conditions return to a non-impacting state. The Signal is
re-evaluated and becomes `resolved`, preserving its history.

------------------------------------------------------------------------

## 15. Functional Requirements

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  CM-FR-01                            Consume versioned domain
                                      events/facts through approved
                                      contracts

  CM-FR-02                            Resolve affected context and
                                      relationships

  CM-FR-03                            Assemble evidence with
                                      provenance/time

  CM-FR-04                            Detect and preserve conflicts

  CM-FR-05                            Support deterministic, rule-derived
                                      and AI-assisted synthesis

  CM-FR-06                            Apply Evidence Gate before material
                                      Signal creation

  CM-FR-07                            Persist material Operational
                                      Signals with lifecycle

  CM-FR-08                            Re-evaluate Signals when relevant
                                      facts change

  CM-FR-09                            Support event-driven discovery

  CM-FR-10                            Support on-demand investigation

  CM-FR-11                            Expose evidence and
                                      uncertainty/conflict

  CM-FR-12                            Provide materiality attributes
                                      without commander-specific priority

  CM-FR-13                            Publish Signal lifecycle events

  CM-FR-14                            Preserve rule/model/prompt version
                                      required for traceability
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 16. Non-Functional Requirements

### Explainability

Every material Signal must be traceable to evidence and synthesis class.

### Reproducibility

Deterministic/rule-derived Signals must be reproducible from versioned
facts/rules. AI-assisted Signals must retain the evidence and relevant
model/prompt/config version needed for auditability.

### Latency

Event-driven detection SLOs must be defined by Signal class. On-demand
response SLOs are separate.

### Resilience

Source/domain unavailability must produce degraded/unknown semantics,
not fabricated meaning.

### Security

Context & Meaning must respect source classification and access
constraints. Synthesis can increase sensitivity and requires explicit
handling.

### Observability

Track event lag, candidate count, gate rejection, Signal
creation/update/resolution, conflicts, source failures and AI-assisted
failure/grounding metrics.

------------------------------------------------------------------------

## 17. Success Metrics

Initial metrics should prove trust and operational value:

-   \% material Signals with complete evidence trace.
-   Signal precision/relevance as validated by users/review process.
-   false/unsupported Signal rate.
-   median time from relevant domain change to material Signal.
-   \% Signals re-evaluated after relevant fact change.
-   duplicate Signal rate.
-   unresolved conflict visibility.
-   number of consumers using the common Signal contract.
-   reduction in duplicated synthesis logic across consumers.

Avoid optimizing for number of Signals generated.

------------------------------------------------------------------------

## 18. Non-Goals

Context & Meaning v0.x is not:

-   a new Source of Truth for domain facts;
-   Commander Experience;
-   a recommendation/decision engine by default;
-   a general autonomous agent;
-   a replacement for Geography spatial computation;
-   a replacement for Operations;
-   a generic enterprise knowledge graph;
-   a system that resolves conflicting truth without ownership rules;
-   an AI confidence-score generator.

------------------------------------------------------------------------

## 19. Product Guardrails

1.  Domain facts remain domain-owned.
2.  Meaning must be evidence-backed.
3.  Preserve conflict unless an authoritative rule resolves it.
4.  No arbitrary confidence percentage.
5.  Not every event becomes a Signal.
6.  Not every candidate is persisted.
7.  Material Signals have lifecycle.
8.  Commander-specific prioritization stays in Commander Experience.
9.  Cross-domain orchestration belongs here; domain computation stays in
    its domain.
10. AI-assisted synthesis must not invent unsupported facts.
11. Prefer explicit unknown/partial/conflict over false certainty.
12. New Signal types require a real use case and evaluation criteria.

------------------------------------------------------------------------

## 20. Open Decisions

The implementation team must close:

-   first domain inputs / Must-Connect contracts;
-   first Signal taxonomy;
-   exact materiality rules for Phase 1;
-   Evidence Gate policy by inference class;
-   conflict schema and authoritative-rule registry;
-   Signal deduplication/supersession rules;
-   event delivery semantics;
-   historical evidence retention;
-   AI model/prompt/config governance;
-   security/midour rules for synthesized outputs;
-   evaluation dataset and human validation process;
-   event-driven SLO and on-demand SLO.
