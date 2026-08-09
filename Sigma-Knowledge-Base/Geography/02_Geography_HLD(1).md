# Geography --- High Level Design

**Status:** v0.2 --- Company Brain / Handoff\
**Style:** Federated Spatial Intelligence Layer\
**Authoritative persistence:** None by default

## 1. Architectural Intent

Target:

``` text
Sources → Adapters → Canonical Spatial Contract → Spatial Engine → SpatialResult
```

not:

``` text
Sources → ETL → New Geography Source of Truth
```

## 2. Target Architecture

``` text
                  AUTHORITATIVE GEO SOURCES
        GIS A        GIS B        Layers / Other Sources
          \            |             /
           +-----------+------------+
                       ↓
              SOURCE ADAPTERS
 auth | query translation | CRS | temporal mapping | provenance
                       ↓
             CANONICAL SPATIAL CONTRACT
          GeoEntity | SpatialQuery | SpatialResult
                       ↓
              SPATIAL INTELLIGENCE
 Query Planner | Geometry Ops | Temporal-Spatial | Synthesis
          Aggregation/Heatmaps | Spatial Intent
                       ↓
             +---------+---------+
             ↓                   ↓
       SpatialResult        Optional Cache
             ↓              rebuildable only
       +-----+-------------------+
       ↓                         ↓
Context & Meaning          Direct Geo Consumers
       ↓
Commander Experience
```

## 3. Components

  -----------------------------------------------------------------------
  Component               Responsibility          Out of scope
  ----------------------- ----------------------- -----------------------
  Source Adapter          auth, source query,     source business
                          mapping,                ownership
                          CRS/time/provenance     

  Query Planner           determine               multi-domain business
                          sources/operations      orchestration

  Canonical Contract      normalized spatial      canonical data copy
                          semantics               

  Geometry Engine         deterministic spatial   LLM reasoning
                          computation             

  Temporal-Spatial        time filtering/validity automatic archive
  Service                                         

  Layer Synthesis         ephemeral composition   persistent synthetic
                                                  layer

  Heatmap/Aggregation     density/aggregation     operational meaning

  Spatial Intent          validate constrained    general chatbot
                          geo intent              

  Cache                   performance             source truth

  API                     stable query surface    decision UX
  -----------------------------------------------------------------------

## 4. Ownership

Source owns entity, geometry, attributes, lifecycle and history.
Geography owns adapters, query/result semantics, algorithms and cache
lifecycle. Consumer owns business context and downstream use.

## 5. Core Models

``` yaml
GeoEntity:
  entity_ref: string
  entity_type: string
  geometry: geometry
  source: string
  source_entity_id: string
  source_updated_at: datetime
  valid_from: datetime?
  valid_to: datetime?
  attributes: object

SpatialQuery:
  operation: enum
  subjects: []
  reference_geometry: ref_or_geometry?
  parameters: object
  time_context: object?
  filters: object?

SpatialResult:
  query_id: string
  result_type: string
  entities: []
  geometry: geometry?
  metrics: object?
  calculated_at: datetime
  source_refs: []
  source_versions: []
  time_context: object?
  completeness:
    status: complete | partial
    unavailable_sources: []
  warnings: []
```

## 6. Spatial Query Flow

``` text
Consumer → API/Auth → Query Planner
                      ├→ Adapter A → Source A
                      └→ Adapter B → Source B
                             ↓
                       Normalize
                             ↓
                   Deterministic Engine
                             ↓
SpatialResult + source/time/completeness/evidence → Consumer
```

## 7. Text → Map

``` text
Commander → Commander Experience → Context & Meaning
                                      ↓ decomposition
                         ┌────────────┴───────────┐
                         ↓                        ↓
                  Other Domains              Geography
                                          Spatial Intent
                                                ↓
                                       Validated Query
                                                ↓
                                      Deterministic Engine
                                                ↓
                                          SpatialResult
                         └────────────┬───────────┘
                                      ↓
                              Context & Meaning
                                      ↓
                              Commander Experience
```

LLM/orchestrator may identify/parse spatial intent. Spatial fact must
come from deterministic Geography execution.

## 8. Map → Text

Map selection/geometry → Geography query → structured SpatialResult.
Factual geo explanation may be rendered directly; operational
interpretation routes through Context & Meaning.

## 9. Temporal Flow

``` text
Query(time=T) → Adapter
                ├→ source has history → retrieve T
                └→ no history → explicit unavailable
                       ↓
                  Spatial Engine
                       ↓
              complete/partial result
```

No automatic historical persistence.

## 10. Layer Synthesis / Heatmap

Both are computed products. Persistent `SyntheticLayer` or
`SpatialInsight` requires a new ADR covering ownership, lifecycle,
update policy, consumers and why recomputation is insufficient.

## 11. Cache

Allowed: source response, normalized representation, query result, tile,
heatmap, expensive compute.

Invariant:

> **A cache can be deleted and rebuilt without changing domain truth.**

Cache keys should include relevant query params, source/version/time
context and algorithm version.

## 12. Source Adapter Contract

``` yaml
source_name: string
supported_entity_types: []
supported_operations: []
supported_time_queries: boolean
source_crs: string
auth_model: string
freshness_metadata: boolean
history_capability: none | current_and_history
```

Adapter handles auth propagation, query translation, geometry parsing,
CRS normalization, temporal mapping, source error mapping and
provenance.

## 13. Initial API Surface

``` text
POST /v1/spatial/query
POST /v1/spatial/entities/search
POST /v1/spatial/layers/synthesize
POST /v1/spatial/heatmap
POST /v1/spatial/intent/validate
```

`intent/validate` accepts constrained spatial intent from an approved
orchestrator. Missing business context returns ambiguity/error; it is
not invented.

## 14. Initial Operations

`INTERSECTS`, `CONTAINS`, `WITHIN`, `DISTANCE`, `NEAREST`, `OVERLAP`,
`AGGREGATE_BY_AREA`, `DENSITY`.

## 15. Consistency

Federated sources are not assumed to share a transactional snapshot.
Result metadata must expose source times, calculation time, unavailable
sources and completeness.

## 16. Failure Semantics

  Condition                      Behavior
  ------------------------------ -----------------------------------------------
  Optional source unavailable    partial result + unavailable source
  Required source unavailable    explicit failure
  Timeout                        operation policy: partial/fail
  Invalid geometry               exclude/fail affected entity + warning/metric
  Historical query unsupported   `history_unavailable`
  Stale source                   explicit freshness warning where permitted
  CRS conversion failure         fail affected data; never guess
  Ambiguous intent               ambiguity/error; no invented query
  Cache unavailable              recompute
  Cache stale                    recompute by source/version policy

## 17. Security

Federation must preserve source authorization/classification.
Cross-source synthesis may itself increase sensitivity and requires
aggregation controls where applicable. Sensitive query auditing should
be supported.

## 18. Observability

Query: total/planner/compute latency, cache hit, completeness.\
Source: latency, availability, adapter/auth errors, stale rate.\
Quality: invalid geometry, missing CRS/timestamps, normalization
failures.

## 19. Domain Contracts

### Operations

Operations holds `area_ref` / `geo_entity_ref`; Geography resolves
geometry and relationships.

### Context & Meaning

Sends a spatial question with resolved context; receives facts/evidence;
owns cross-domain interpretation.

### Commander Experience

May directly consume geo-only rendering/drill-down. Multi-domain
questions go through Context & Meaning.

## 20. Evolution

**Phase 1:** contract, first adapters, core deterministic operations,
provenance/completeness, query API, real consumer.\
**Phase 2:** multi-source federation, synthesis, temporal, heatmaps,
cache/observability.\
**Phase 3:** constrained Text→Map, structured Map→Text, richer
temporal-spatial change.

Progression follows proven vertical slices and source feasibility.

## 21. Architecture Guardrails

No authoritative copy by default; no speculative persistence; no
business entity from query result without ADR; no spatial logic in
Commander Experience; no duplicate GIS logic in Context & Meaning; no
cross-domain orchestration in Geography; no LLM-created facts; no
historical claims beyond source capability; cache is non-authoritative;
provenance/completeness required.

## 22. First Vertical Slice DoD

-   ≥1 real authoritative source through adapter.
-   ≥1 real consumer uses Geography contract rather than source
    directly.
-   ≥3 deterministic operations end-to-end.
-   source/time metadata returned.
-   explicit failure/partial behavior demonstrated.
-   no authoritative Geography DB required.
-   cache can be rebuilt.
-   ownership boundaries demonstrated.
