# Sigma Execution Model

**Status:** Canonical (human-readable) — derived from the execution handoff.
**Detailed planning artifact:** [`Handoffs/SIGMA-FINAL-EXECUTION-HANDOFF-2026-2027.xlsx`](Handoffs/SIGMA-FINAL-EXECUTION-HANDOFF-2026-2027.xlsx) — the spreadsheet remains the detailed, cell-level source of truth. This document captures the organizational knowledge a new Product Lead must have **without opening the spreadsheet**; it does not replace it.

> **Delivery baseline: GREENFIELD / SETUP REQUIRED.** Everything below is planning and direction. Slices, priorities, and targets describe intended sequence and are **not** evidence of implemented capability.

---

## 1. The core chain

```text
Business Problem
   → Vertical Slice
      → Required Domain Capabilities
         → Reusable Capabilities
            → End-to-End Evidence (on real data)
```

- **Business Problem** — a real operational/user problem of the organization, not a team's internal roadmap item.
- **Vertical Slice** — an end-to-end scenario that proves user value across the whole chain (Source → Domain truth → Signal/Context → Commander Space).
- **Domain Capabilities** — what Operations, Geography, Context & Meaning and the experience modules each build for that slice.
- **Reusable Capability** — what remains after the initiative and serves the next one.
- **End-to-End Evidence** — the slice demonstrated on real data with a real consumer.

## 2. Annual planning logic

- **Start from the next business Vertical Slice, not from isolated team roadmaps.**
- Decompose the slice into deliverables by domain; agree shared backlog + ownership.
- **Close dependencies and contracts before parallel development.**
- Demonstrate end-to-end on real data.
- Pass a **Gate** only if the DoD **and** the business outcome are proven → Continue / Adjust / Stop.

**Test before admitting any initiative:** (1) which user/operational problem does it solve? (2) which slice proves it end-to-end? (3) what is reusable in each domain? (4) who consumes it again?

## 3. Priority tiers — P0 / P1 / P2 (NOT YET)

- **P0 = build this year.** Foundation capabilities that everything else depends on.
- **P1 = only after Foundation + a Gate.** Valuable, but sequenced behind P0 proof.
- **P2 / NOT YET = architectural direction, *not* a delivery commitment.**

| Tier | Examples (current) |
|--|--|
| **P0** | Operations state/change + dependencies · Temporal Geo + Spatial Synthesis · Evidence & Assurance · Operational Signal · Attention → Investigation |
| **P1** | Text ↔ Map · typed dependency/causal relations · Decision → Execution → Continuity |
| **NOT YET** | Digital Twin / simulation · broad What-if · Multimodal Geo production · counterfactual reasoning · autonomous recommendations |

**P2 / NOT YET must not be turned into committed roadmap items** (see §8).

## 4. The current five Vertical Slices (summary)

*(Summarized from handoff Sheet 2. The slices use the experience-layer name "Commander Experience"; the canonical product name is **Commander Space**.)*

| # | User problem → outcome | Reusable capability | Target |
|--|--|--|--|
| **01** | A commander needs to know, in time, when an operational change requires attention → a significant change reaches the commander in time, with explanation and the ability to investigate. | Change/version contract + reusable Signal pattern | **Q1** |
| **02** | A commander needs to understand how a change in space affects the plan → spatial impact on the plan is identified and explained. | Spatial synthesis + cross-domain impact pattern | **Q2** |
| **03** | A commander needs to see a readiness gap before a decision point → a significant gap is surfaced before the relevant decision. | Dependency/readiness reasoning + impact pattern | **Q2–Q3** |
| **04** | A commander needs a spatial question answered without assembling a map by hand → answered quickly with map, explanation and follow-up. | Reusable Text↔Map / spatial query interface | **Q3** |
| **05** | A commander needs to close the loop from understanding to decision and execution → decision moves to execution with context, rationale and status preserved. | Reusable Decision → Execution → Continuity pattern | **Q3–Q4** |

Each slice has agreed per-domain deliverables, a DoD, and cross-team dependencies in the spreadsheet.

## 5. Gate logic

Work does **not** advance automatically. There are quarterly gates; each decides **Continue / Adjust / Stop (or Merge)**:

| Gate | Timing | Reviews | Continue if… |
|--|--|--|--|
| **Gate 1** | end Nov 2026 | Slice 01 + Foundations | E2E works on real data and there is a real consumer |
| **Gate 2** | end Feb 2027 | Slices 02–03 + reuse | the same capabilities serve more than one initiative |
| **Gate 3** | end May 2027 | Decision value + Geo/C&M maturity | there is a clear improvement in speed/quality of understanding and decision |
| **Gate 4** | Aug 2027 | Next-year topology | there is a 12-month pipeline ahead with consumers and reuse (team-shape decision) |

*Adjust* when value exists but contracts/ownership or one-off solutions need rework; *Stop/Merge* when there is no real consumer/use case or the layer does not justify separate ownership.

## 6. DoD philosophy — what "done" means

A capability is **not "done" because it exists.** "Done" for a slice means the **business outcome and the DoD are proven end-to-end on real data**, with:

- a real problem solved for a real user,
- the smallest slice that proves the outcome,
- domain contracts/owners/readiness closed before parallel build,
- **each team building a reusable capability, not one-off logic**,
- at least one additional consumer/use-case identified (reuse),
- and a recorded Continue/Adjust/Stop decision with rationale and metrics.

## 7. Why dates do not automatically advance work

Reaching a date is not a reason to start or continue a capability. Two rules from the plan:

- **"Do not start a capability just because its date arrived"** — build it from an active business slice and expand only when reuse is proven.
- **"Do not continue automatically by date"** — a Gate must prove value first.

## 8. Cross-domain dependency principle & NOT-YET guardrails

- **Cross-domain dependency principle:** close cross-team **contracts** (schemas, IDs, versioning, provenance/freshness, error boundaries) **before** parallel development. When the experience layer needs cross-domain meaning, it goes through **Context & Meaning** rather than joining domain stores and re-deriving synthesis. (C&M is not mandatory for purely factual, single-domain state.)
- **Guardrails (when *not* to build):** no clear problem/user → return to discovery; no vertical slice → reduce scope until one demo exists; no second consumer/reuse → build minimally inside the slice, don't open a platform; experience layer joining stores and synthesizing → stop and define a Signal/Context contract; a domain producing consumer-specific UI/meaning → return the boundary to the domain contract.
- **NOT-YET guardrails:** Digital Twin/simulation, broad What-if, Multimodal Geo production, counterfactual reasoning, and autonomous recommendations are **kept as direction, not committed** — reconsidered only when their explicit prerequisites and a bounded, validated use case exist.

---

*This document summarizes the execution handoff for orientation. For per-slice deliverables, per-domain START-HERE priorities, the cross-team contract table, the PM runbook, the priority/feasibility matrix, and the Future/Not-Yet register, open the spreadsheet referenced at the top.*
