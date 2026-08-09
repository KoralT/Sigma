# Context & Meaning --- Input & Source Contract

**Status:** v0.1 execution template

## 1. Purpose

Defines what C&M requires from every producing domain before that domain
can participate in synthesis.

C&M must not depend on undocumented source semantics.

------------------------------------------------------------------------

## 2. Producer Envelope

Suggested event/fact envelope:

``` yaml
event_id: string
event_type: string
domain: string
entity_type: string
entity_id: string
operation_id: string?
occurred_at: datetime
source_updated_at: datetime?
version: string?
schema_version: string
change:
  changed_fields: []
  before: object?
  after: object?
provenance:
  source_system: string
  source_entity_id: string
```

Events should contain enough information to route/re-evaluate but do not
need to carry an uncontrolled copy of the entire domain aggregate.

------------------------------------------------------------------------

## 3. Producer Requirements

Every producer must define:

-   domain/business owner;
-   entity IDs;
-   stable linking keys;
-   event vocabulary;
-   field/status semantics;
-   event time vs source update time;
-   version/order semantics;
-   source of truth;
-   authoritative facts;
-   freshness expectations;
-   read API for evidence retrieval;
-   authorization/classification;
-   correction/retraction behavior.

------------------------------------------------------------------------

## 4. Initial Producer Matrix

  -------------------------------------------------------------------------------------------------------
  Domain         Facts/Events                                Authority      Evidence       Phase
                                                                            retrieval      
  -------------- ------------------------------------------- -------------- -------------- --------------
  Operations     Operation/Activity/plan/dependency/status   Operations for Operations     Phase 1
                 changes                                     owned state    APIs           

  Geography      SpatialResult / deterministic spatial facts Geography for  Geography      Phase 1/2 by
                 when requested; future relevant change      computation;   query API      scenario
                 events if contract exists                   sources for                   
                                                             underlying geo                
                                                             data                          

  Other          TBD                                         explicit       TBD            only when real
  professional                                               domain                        Signal
  domain                                                     contract                      requires it
                                                             required                      
  -------------------------------------------------------------------------------------------------------

Do not invent a Must-Connect source solely to make architecture look
complete.

------------------------------------------------------------------------

## 5. Relationship Contract

C&M relies on explicit relationships where possible:

``` yaml
relationship:
  type: string
  from_ref: string
  to_ref: string
  valid_from: datetime?
  valid_to: datetime?
  source: string
```

Examples may include allocation, dependency or contextual linkage where
defined by the owning domain.

Semantic similarity alone is not an authoritative relationship.

------------------------------------------------------------------------

## 6. Authoritative Rule Registry

For facts that may appear in multiple sources:

  -----------------------------------------------------------------------
  Fact Type         Authoritative     Fallback          Conflict behavior
                    Domain                              
  ----------------- ----------------- ----------------- -----------------
  Operation planned Operations        none unless       preserve conflict
  timeline                            defined           

  Spatial relation  Geography         none              recompute/query
                    computation                         

  Other facts       TBD               TBD               unresolved until
                                                        contract exists
  -----------------------------------------------------------------------

The registry must be explicit and versioned.

------------------------------------------------------------------------

## 7. Evidence Retrieval Contract

Given a reference/version, C&M must be able to obtain enough factual
context for synthesis.

Evidence should expose:

``` yaml
fact_ref:
domain:
entity_ref:
field_or_fact_type:
value:
observed_at:
source_updated_at:
version:
source:
classification:
```

------------------------------------------------------------------------

## 8. Input Quality States

Inputs may be:

-   available/current;
-   stale;
-   unavailable;
-   conflicting;
-   invalid;
-   unsupported version.

C&M must not normalize these into "available" merely to complete
synthesis.

------------------------------------------------------------------------

## 9. Producer Onboarding Checklist

-   [ ] Business owner.
-   [ ] Technical owner.
-   [ ] Event schema/version.
-   [ ] Read/evidence API.
-   [ ] Stable IDs/linking.
-   [ ] Status vocabulary.
-   [ ] Time semantics.
-   [ ] Ordering/idempotency.
-   [ ] Authority rules.
-   [ ] Freshness.
-   [ ] Correction behavior.
-   [ ] Auth/classification.
-   [ ] Test fixtures.
-   [ ] At least one Signal/use case proving the integration is needed.

------------------------------------------------------------------------

## 10. Producer Failure Policy

  -----------------------------------------------------------------------
  Condition                           C&M behavior
  ----------------------------------- -----------------------------------
  Duplicate event                     idempotent no duplicate business
                                      effect

  Out-of-order event                  version/time-aware re-evaluation

  Unsupported schema                  reject/quarantine + alert

  Evidence API unavailable            Gate sees unavailable evidence

  Stale fact                          preserve staleness metadata

  Source correction                   re-evaluate affected Signals

  Unknown entity/link                 no invented relationship

  Authorization denied                no bypass; degraded/denied
                                      according to consumer context
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 11. Must-Connect Gate

A producer enters Phase 1 only if:

1.  a chosen Golden E2E Signal requires it;
2.  ownership is clear;
3.  stable identifiers exist;
4.  evidence can be retrieved;
5.  event/fact semantics are understood;
6.  security is approved;
7.  test data exists.

The goal is the smallest credible cross-domain slice, not maximum source
coverage.
