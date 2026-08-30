# Context & Meaning Domain

## What this domain owns
Interpretation **across trusted information** — meaning, relevance, relationships, change, and impact. Per the pack, its canonical output is the **Operational Signal**, and its boundary is `Facts → Meaning`.

## What this domain does NOT own
- the raw domain facts themselves (owned by **Operations**, **Geography**, and professional source systems)
- commander-specific priority / decision UX → **Commander Space**
- spatial computation → **Geography**
- operational state / the canonical Operation representation → **Operations**

## Key documents in this folder
- `Product/Context-and-Meaning-PRD.md` — product requirements.
- `Architecture/Context-and-Meaning-HLD.md` — high-level design.
- `Architecture/Context-and-Meaning-ADR.md` — **accepted baseline decisions**.
- `Contracts/Context-and-Meaning-Input-Source-Contract.md` — what C&M requires from producing domains.
- `Contracts/Operational-Signal-Schema-v0.1.md` — the **Operational Signal** business-contract proposal.
- `Delivery/Context-and-Meaning-Golden-E2E-Phase1.md` — domain acceptance contract (Phase-1 DoD).

## Boundaries with neighboring domains
- **Operational Signal** (a concrete C&M output/contract) is **distinct** from **Operational Meaning** (the shared capability, `../../04-SHARED-CAPABILITIES/Operational-Meaning/`). They are not synonyms; two conflicting definitions of "Operational Signal" remain unresolved (see `../../GLOSSARY.md`).
- `Facts → Meaning` belongs here; `Meaning → commander-specific priority/decision UX` belongs to **Commander Space**.
- Documents here use the legacy term "Commander Experience"; the canonical name is **Commander Space**.

## Where to go next
- [`DOCUMENT-REGISTRY.md`](../../DOCUMENT-REGISTRY.md) and [`CURRENT-STATE.md`](../../CURRENT-STATE.md).
