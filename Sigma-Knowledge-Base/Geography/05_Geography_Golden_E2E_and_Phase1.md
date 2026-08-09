# Geography --- Golden E2E, Phase 1 DoD & Runbook

**Status:** v0.1 execution baseline

## 1. Goal

Prove that Geography creates reusable spatial value without becoming a
new GIS Source of Truth.

Use **one real consumer + one real authoritative source** first. Add
sources only when the vertical slice requires them.

## 2. Golden E2E

Reference question:

> **אילו ישויות מסוג X נמצאות עד N ק"מ ממרחב Y בזמן T?**

``` text
Consumer
   ↓
SpatialQuery
   ↓
Geography API / Authorization
   ↓
Query Planner
   ↓
Source Adapter
   ↓
Authoritative Source
   ↓
Normalize geometry / CRS / time / provenance
   ↓
Deterministic WITHIN / DISTANCE
   ↓
SpatialResult
   ├─ matching entity refs
   ├─ geometry/metrics as needed
   ├─ source refs
   ├─ source timestamps
   ├─ calculated_at
   └─ completeness/warnings
   ↓
Consumer
```

## 3. Golden E2E Acceptance

The demo must prove:

1.  Consumer does not call the source directly.
2.  Source remains authoritative.
3.  Geography normalizes source representation.
4.  Spatial calculation is deterministic.
5.  Result contains provenance and time.
6.  Failure/staleness is explicit.
7.  No authoritative Geography DB is needed.
8.  Same contract can plausibly serve another consumer/query.

## 4. Phase 1 Scope

### In

-   Canonical `GeoEntity`, `SpatialQuery`, `SpatialResult`.
-   First real Source Adapter.
-   API/auth path.
-   At least 3 deterministic operations:
    -   `WITHIN` or `CONTAINS`
    -   `DISTANCE`
    -   `INTERSECTS`
-   provenance and completeness.
-   current-state temporal metadata.
-   explicit partial/failure semantics.
-   observability.
-   optional rebuildable cache only if needed.
-   one real consumer.

### Out

-   Digital Twin.
-   general-purpose chat.
-   permanent SyntheticLayer.
-   permanent SpatialInsight.
-   automatic historical archive.
-   broad source catalog.
-   advanced route optimization unless required by the chosen slice.
-   operational recommendations.
-   predictive spatial intelligence.

## 5. Phase 1 Definition of Done

-   [ ] Real source owner identified.
-   [ ] Real consumer/use case identified.
-   [ ] Source Mapping entry complete.
-   [ ] Adapter implemented and tested.
-   [ ] CRS/geometry strategy tested with known fixtures.
-   [ ] Canonical contracts versioned.
-   [ ] ≥3 spatial operations work end-to-end.
-   [ ] Provenance returned for every result.
-   [ ] Source time + calculated time returned.
-   [ ] Required vs optional source semantics defined.
-   [ ] Source unavailable behavior tested.
-   [ ] Invalid geometry behavior tested.
-   [ ] Stale source behavior tested.
-   [ ] Authorization/classification approved.
-   [ ] Query latency observable.
-   [ ] No authoritative Geography copy required.
-   [ ] Cache, if present, is rebuildable.
-   [ ] Consumer removed/avoided direct spatial integration for this
    flow.

## 6. Exception Runbook

  -----------------------------------------------------------------------
  Condition               Geography behavior      Never do
  ----------------------- ----------------------- -----------------------
  Required source         fail explicitly         return empty set as if
  unavailable                                     factual

  Optional source         partial result +        claim completeness
  unavailable             unavailable source      

  Source timeout          partial/fail per query  silently omit
                          semantics               

  Stale source            return with freshness   present as current
                          warning if policy       
                          permits                 

  Invalid geometry        exclude/fail affected   repair by guessing
                          item + observable error 

  Missing/unknown CRS     explicit failure for    assume CRS
                          affected data           

  CRS conversion failure  fail affected result    use raw coordinates
                                                  blindly

  Historical query        `history_unavailable`   invent historical state
  unsupported                                     

  Ambiguous spatial       return ambiguity        invent parameters
  intent                                          

  Cache unavailable       recompute if feasible   fail solely because
                                                  cache is down

  Cache stale             recompute by policy     treat cache as
                                                  authoritative

  Source schema changed   adapter                 silently reinterpret
                          failure/compatibility   fields
                          alert                   

  Authorization denied    deny/filter according   bypass source
                          to contract             permissions
  -----------------------------------------------------------------------

## 7. Partial Result Semantics

Suggested structure:

``` yaml
completeness:
  status: partial
  unavailable_sources:
    - SOURCE_B
warnings:
  - "SOURCE_B unavailable at query time"
```

A partial result is valid only when the query still has meaningful
semantics without the missing source. Otherwise fail.

## 8. Testing Strategy

### Known spatial fixtures

Maintain small deterministic test fixtures for:

-   point inside/outside polygon;
-   intersecting/non-intersecting polygons;
-   known distances;
-   CRS conversion;
-   boundary conditions;
-   invalid geometry;
-   time-valid/time-invalid entities.

### Contract tests

Every adapter must pass common Geography contract tests.

### Failure tests

Test source timeout, auth failure, malformed geometry, missing
timestamps and unsupported temporal query.

## 9. Phase 1 Review Questions

### Product

Does this answer a real spatial question that otherwise requires
source-specific work?

### Architecture

Did we preserve source ownership and avoid speculative persistence?

### Data/Geo

Are CRS, geometry and temporal semantics explicit?

### Consumer

Did the consumer use the common contract rather than rebuild spatial
logic?

### Trust

Can a user/system trace the result to source and time?

### Reuse

Is there evidence the contract/operation can serve more than one screen
or initiative?

## 10. What Comes After Phase 1

Only after the foundation proves itself:

1.  onboard second source;
2.  prove multi-source federation;
3.  add layer synthesis;
4.  add temporal queries where sources support them;
5.  add heatmap/aggregation;
6.  strengthen caching and SLOs;
7.  introduce constrained Text → Map through Context & Meaning;
8.  introduce structured Map → Text.

Do not progress because a roadmap date arrived. Progress when the prior
capability has a real consumer and reliable contract.
