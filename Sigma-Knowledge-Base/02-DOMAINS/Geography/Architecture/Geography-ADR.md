# Geography --- Architecture Decision Record

**Status:** Accepted baseline decisions\
**Purpose:** Preserve the reasoning behind Geography v0.x so future
teams do not reopen or silently reverse architectural choices without
evidence.

## ADR-01 --- Federation over Canonical Geo Store

**Decision:** Geography is a Federated Spatial Intelligence Layer, not a
new authoritative copy of all geo data.

**Why:** Existing professional systems remain owners of their entities
and lifecycle. Copying everything would create synchronization,
ownership and freshness problems before reuse is proven.

**Consequence:** Geography requires robust adapters, source availability
handling and explicit completeness metadata.

**Revisit when:** a specific dataset has a business lifecycle that
cannot be served through federation.

------------------------------------------------------------------------

## ADR-02 --- Query Results are ephemeral by default

**Decision:** Intersection, synthesis, heatmap and other derived outputs
are Query Results, not persistent business entities.

**Principle:** **Compute first. Persist only when a business lifecycle
requires it.**

**Revisit when:** a derived product has clear owner, lifecycle, update
policy, repeated consumers and retention need.

------------------------------------------------------------------------

## ADR-03 --- Canonical Spatial Contract without Canonical Data Store

**Decision:** Sources own data; Geography owns the canonical spatial
language.

**Canonical objects:** `GeoEntity`, `SpatialQuery`, `SpatialResult`.

**Consequence:** consumers are decoupled from source formats while
source ownership is preserved.

------------------------------------------------------------------------

## ADR-04 --- Spatial Reasoning belongs to Geography

**Decision:** deterministic operations such as distance, intersection,
containment, proximity, density and aggregation live in Geography.

**Not allowed:** duplicating this logic in Context & Meaning or
Commander Experience.

------------------------------------------------------------------------

## ADR-05 --- Context & Meaning orchestrates multi-domain questions

**Decision:** Geography does not own conversational orchestration.

Example:

``` text
Question → Context & Meaning
          ├→ Operations / Force facts
          └→ Geography spatial facts
          ↓
       combined meaning
```

**Consequence:** Geography can expose Spatial Intent validation but
remains a spatial domain service.

------------------------------------------------------------------------

## ADR-06 --- Temporal contract without automatic historical archive

**Decision:** Geography supports temporal query semantics but relies on
source history by default.

If a source cannot answer historical state, the result must explicitly
say so.

**Revisit:** targeted historical materialization requires its own ADR.

------------------------------------------------------------------------

## ADR-07 --- Cache is non-authoritative

**Decision:** technical caches are allowed for performance/resilience.

**Invariant:** cache is rebuildable, disposable and non-authoritative.

Deleting cache must not delete domain truth.

------------------------------------------------------------------------

## ADR-08 --- Deterministic execution behind Text → Map

**Decision:** LLM/intent parsing may translate natural language into a
constrained spatial query. The spatial fact itself must be produced by
deterministic Geography computation.

**Reason:** traceability, reproducibility and trust.

------------------------------------------------------------------------

## ADR-09 --- Explicit partial truth

**Decision:** federated queries expose completeness and
unavailable/stale sources.

Geography must not make an incomplete multi-source result appear
complete.

------------------------------------------------------------------------

## ADR-10 --- Persistence requires a gate

Before persisting any derived geo product, answer:

1.  What business entity is this?
2.  Who owns it?
3.  What is its lifecycle?
4.  Who updates/deletes it?
5.  What retention is required?
6.  Which consumers reuse it?
7.  Why is recomputation/cache insufficient?
8.  What security implications arise?

If these are not answered, do not persist it.

------------------------------------------------------------------------

## Decision Summary

  Decision              Baseline
  --------------------- ----------------------
  Data architecture     Federation
  Canonical layer       Spatial contract
  Spatial compute       Geography
  Derived results       Ephemeral
  Historical state      Source-owned
  Cache                 Non-authoritative
  Chat orchestration    Context & Meaning
  Text→Map compute      Deterministic
  Operational meaning   Context & Meaning
  Commander UX          Commander Experience
