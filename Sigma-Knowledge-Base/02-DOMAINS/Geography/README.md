# Geography / Spatial Intelligence Domain

## What this domain owns
Shared organizational **spatial information, computation, relationships, and spatial evidence**. Per the Geography pack, its architectural stance is a **Federated Spatial Intelligence Layer** that computes over existing authoritative sources and **does not** create a new authoritative geo store by default.

## What this domain does NOT own
- operational state / the canonical Operation representation → **Operations**
- cross-domain operational meaning → **Context & Meaning**
- Commander attention / prioritization → **Commander Space**
- the source-of-record geographic systems themselves (Geography federates over them)

## Key documents in this folder
- `Product/Geography-PRD.md` — product requirements (v0.2).
- `Architecture/Geography-HLD.md` — high-level design (v0.2).
- `Architecture/Geography-ADR.md` — **accepted baseline decisions** (incl. federation over a canonical geo store).
- `Contracts/Geography-Source-Mapping.md` — source onboarding contract/template.
- `Delivery/Geography-Golden-E2E-Phase1.md` — domain acceptance contract (Phase-1 DoD).
- `Strategy/Spatial-Intelligence.md` — vision/strategy (candidate; contains legacy DOCX-conversion formatting to be cleaned later).

## Boundaries with neighboring domains
- Geography supplies spatial computation and evidence that **Operations** and **Context & Meaning** consume; it does not assign operational meaning or commander priority.
- Some documents in this pack use the legacy term "Commander Experience"; the canonical name is **Commander Space** (see `../../GLOSSARY.md`).

## Where to go next
- [`DOCUMENT-REGISTRY.md`](../../DOCUMENT-REGISTRY.md) and [`CURRENT-STATE.md`](../../CURRENT-STATE.md).
