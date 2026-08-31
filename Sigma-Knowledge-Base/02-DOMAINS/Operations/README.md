# Operations Domain

## What this domain owns
The **Operations Store** is the operational domain capability / system of record for Sigma's **canonical Operation representation and relevant operational state**. Per the current Operations Store material, it owns:
- Operation identity / core
- plan, activities, milestones, dependencies
- relevant factual state
- projections / references to external professional objects
- provenance, planned-vs-actual distinction
- snapshots / audit where defined

## What this domain does NOT own
- cross-domain operational meaning → **Context & Meaning**
- Commander attention / prioritization → **Commander Space**
- GIS / spatial computation → **Geography**
- machine-generated readiness scores
- professional-system source objects (owned by the source systems)

## Key documents in this folder
- `Contracts/operations-store-openapi-starter-v0.1.yaml`, `Contracts/operations-store-asyncapi-starter-v0.1.yaml` — starter API/event contracts (candidate).
- `Knowledge/Operations-Repository.md` — **historical/broader** operations knowledge model (formerly CAT-010). Preserved for traceability; **does not** override current Operations Store contracts.
- **Operations Store package (PRD, HLD, ADR & contracts, canonical schema v0.1, API/event contract v0.1, Golden E2E / Phase-1 DoD)** is still authored as `.docx` under `../../Operations-Store/` and is **pending DOCX→Markdown conversion and verification (Batch 2B)**. It has not been converted yet.

## Boundaries with neighboring domains
- Operations provides operational state/representation; **Context & Meaning** interprets across it; **Geography** provides spatial computation; **Commander Space** presents it for human decision.
- Operations Store owns its own canonical operational schema/contracts. The cross-cutting **Entity Model** (`../../04-SHARED-CAPABILITIES/Knowledge/Entity-Model.md`) provides conceptual entity semantics and is **not** canonical for Operations entities.

## Where to go next
- [`DOCUMENT-REGISTRY.md`](../../DOCUMENT-REGISTRY.md) for status of every document.
- [`CURRENT-STATE.md`](../../CURRENT-STATE.md) for what is and is not established today.
