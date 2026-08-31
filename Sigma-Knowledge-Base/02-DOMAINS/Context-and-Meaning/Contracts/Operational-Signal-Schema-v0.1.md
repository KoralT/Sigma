# Context & Meaning --- Operational Signal Schema v0.1

**Status:** Canonical business contract proposal

## 1. Purpose

An Operational Signal is a traceable statement of operational meaning
derived from domain facts in context.

It is not a raw event, recommendation or commander-specific
notification.

------------------------------------------------------------------------

## 2. Canonical Schema

``` yaml
OperationalSignal:
  signal_id: string
  signal_type: string
  subject_refs:
    - domain: string
      entity_type: string
      entity_id: string

  statement:
    title: string
    meaning: string

  change:
    summary: string?
    changed_refs: []

  impact:
    affected_subject_refs: []
    scope: operation | multi_operation | other
    time_sensitivity: immediate | near_term | informational
    decision_dependency: boolean?
    attributes: object?

  evidence:
    bundle_id: string
    fact_refs: []
    relationship_refs: []
    source_versions: []
    completeness: complete | partial
    unavailable_inputs: []

  inference:
    class: deterministic | rule_derived | ai_assisted
    rule_id: string?
    rule_version: string?
    model_ref: string?
    prompt_or_config_version: string?

  uncertainty:
    state: none | incomplete | conflicting | inferred
    details: string?

  conflict_refs: []

  lifecycle:
    status: active | changed | resolved | superseded
    first_detected_at: datetime
    last_evaluated_at: datetime
    resolved_at: datetime?
    superseded_by: string?

  audit:
    created_by: system/component
    created_at: datetime
    version: string
```

------------------------------------------------------------------------

## 3. Required Semantics

A material Signal must answer:

-   **What changed / what condition exists?**
-   **What does it affect?**
-   **Why does it matter?**
-   **What evidence supports it?**
-   **What is uncertain/conflicting?**
-   **When was it last evaluated?**

------------------------------------------------------------------------

## 4. Signal vs Fact vs Recommendation

### Fact

> Operation X planned start changed from 20:00 to 00:00.

Owned by Operations.

### Signal

> The new execution window no longer overlaps Force Z availability.

Owned by Context & Meaning, supported by facts.

### Recommendation

> Move the operation window or allocate another force.

Not part of the canonical Signal v0.1. Recommendation ownership requires
a separate product decision.

------------------------------------------------------------------------

## 5. Inference Classes

### deterministic

Direct consequence of exact state/operation.

### rule_derived

Derived through an explicit versioned business rule.

### ai_assisted

Semantic synthesis over an EvidenceBundle.

Inference class must always be visible internally and available for
audit/explanation.

------------------------------------------------------------------------

## 6. Uncertainty

Do not use arbitrary numeric confidence.

Use explicit states:

-   `none`
-   `incomplete`
-   `conflicting`
-   `inferred`

Additional future confidence semantics require a defined measurement
model.

------------------------------------------------------------------------

## 7. Materiality Attributes

Allowed:

-   affected subjects;
-   scope;
-   time sensitivity;
-   decision dependency;
-   explicitly defined impact attributes.

Not allowed in Signal core:

``` yaml
commander_priority: 1
homepage_rank: 2
show_to_role_x: true
```

These belong to Commander Experience / role-aware policy.

------------------------------------------------------------------------

## 8. Lifecycle Rules

### active

Condition currently holds.

### changed

Signal remains relevant but its meaning/impact/evidence materially
changed.

### resolved

Underlying condition no longer holds.

### superseded

A newer Signal replaces this one as the meaningful representation.

Never delete a material Signal solely because it resolved if
continuity/audit requires history.

------------------------------------------------------------------------

## 9. Deduplication Identity

Exact implementation remains open, but should consider:

``` text
signal_type
+ primary subject(s)
+ relevant relationship/context
+ material condition
```

Do not deduplicate only by generated text.

------------------------------------------------------------------------

## 10. Evidence Rules

Every fact reference should be resolvable or captured sufficiently for
later explanation.

AI-assisted text without evidence references cannot become a material
Signal.

If evidence becomes corrected, affected Signals must be re-evaluated.

------------------------------------------------------------------------

## 11. Conflict Schema

``` yaml
Conflict:
  conflict_id: string
  subject_ref: object
  fact_type: string
  claims:
    - source: string
      value: object
      observed_at: datetime?
      source_updated_at: datetime?
      version: string?
  authoritative_rule:
    rule_id: string?
    resolved_source: string?
  status: unresolved | resolved
  detected_at: datetime
  resolved_at: datetime?
```

------------------------------------------------------------------------

## 12. Example

``` yaml
signal_id: SIG-123
signal_type: EXECUTION_WINDOW_MISMATCH
subject_refs:
  - domain: operations
    entity_type: operation
    entity_id: OP-17

statement:
  title: "Execution window mismatch"
  meaning: "The updated operation window no longer overlaps the availability of Force Z."

impact:
  affected_subject_refs:
    - entity_id: FORCE-Z
  scope: operation
  time_sensitivity: near_term
  decision_dependency: true

evidence:
  bundle_id: EV-88
  fact_refs:
    - OP-17.PLANNED_WINDOW@v12
    - FORCE-Z.AVAILABILITY@v7
  relationship_refs:
    - OP-17_ALLOCATED_FORCE-Z
  completeness: complete
  unavailable_inputs: []

inference:
  class: rule_derived
  rule_id: WINDOW_OVERLAP_RULE
  rule_version: "1.0"

uncertainty:
  state: none

lifecycle:
  status: active
  first_detected_at: 2026-08-09T10:15:00+03:00
  last_evaluated_at: 2026-08-09T10:15:00+03:00
```
