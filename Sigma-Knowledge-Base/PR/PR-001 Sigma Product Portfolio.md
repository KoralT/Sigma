---
id: PR-001
title: Sigma Product Portfolio
version: 2.0
status: Draft
classification: Foundational
owner: Sigma
last_updated: 2026-08-30
---

# Sigma Product Portfolio

The Product Portfolio answers **what Sigma manages and builds** as a portfolio, **why each part exists**, **who receives value** from it, **what each part owns**, and **how the parts work together without overlapping ownership.**

It complements the other foundations without repeating them:

- The [Sigma Doctrine](../DOC/DOC-001%20Sigma%20Doctrine.md) answers **why** Sigma exists and the principles that govern it.
- The [Operating Model](../OM/OM-001%20Sigma%20Operating%20Model.md) answers **how** Sigma turns a need into a cross-domain capability and outcome.
- **This document answers what** Sigma manages and builds.

This is **not** a roadmap, an architecture document, a feature inventory, an org chart, a list of PR IDs, a delivery-status report, or a restatement of the Doctrine/Operating Model.

---

## 1. Portfolio thesis

Sigma exists because the operational problem **cannot be solved by one application.** Across long-term planning, short-term control and command roles, the same needs recur:

- a shared and trustworthy operational picture,
- connection between planned and actual state,
- spatial context,
- cross-domain meaning when needed,
- role-specific context and attention,
- the ability to act without manually reconstructing context across systems.

These needs do not map to one product — they require **different kinds of ownership** (owning *truth*, owning *spatial computation*, owning *meaning*, owning *experience*). That is why Sigma is a **portfolio** rather than a single system. The portfolio's job is to keep each kind of ownership distinct and composable.

The reasoning always runs:

```text
User Need → Required Capability → Portfolio Responsibility
```

Not `User Need → predetermined feature`. The need and the capability come first; the portfolio responsibility is the *place that owns* the capability.

---

## 2. Discovery evidence vs current portfolio truth

Historical strategy and persona material in the repository is valuable **evidence** of: user pains, recurring questions, the planning/control distinction, information fragmentation, role-specific information needs, and the planned-vs-actual gap. That evidence is used here.

But **old solution packaging is not automatically current portfolio truth.** In particular, this document does **not** recreate the older three-initiative model (`Operations Store / Commander Space / Data & Trust`) as the current portfolio structure, and it does **not** carry forward historical placements such as: Text-to-Map as an Operations Store capability; GIS as generic "Data & Trust"; an "Insights LLM" as an Operations-Store-owned product; Operations Store owning the entire AI layer; or Commander Space as the whole experience layer. Those appear only as historical evidence where relevant. **Current Owner Truth wins.**

---

## 3. Current Sigma portfolio model

```text
SIGMA
│
├── Domain & Shared Capabilities
│   ├── Operations Store
│   ├── Geography / Spatial Intelligence
│   ├── Context & Meaning
│   └── Shared Capabilities
│
└── ZIRA — Product / Experience Layer
    ├── Commander Space
    ├── Operations Management
    └── Additional modules / experiences
```

- **Sigma and Zira are not synonyms.** Sigma is the wider system / capability ecosystem; **Zira is Sigma's product / experience layer.**
- Operations Store, Geography / Spatial Intelligence, and Context & Meaning are **Sigma capabilities, not Zira modules.**
- Commander Space and Operations Management are **modules inside Zira**, and **Commander Space does not contain Operations Management.**

*(See [DECISION-LOG D-17](../05-DECISIONS/DECISION-LOG.md).)*

---

## 4. Portfolio responsibility map

Portfolio-level ownership only — this section does not restate schema, API, or architecture detail.

### Operations Store
- **Role:** operational domain truth.
- **Exists because:** Sigma needs a stable, **canonical organizational representation of an Operation** and relevant operational state across its lifecycle.
- **Owns (portfolio level):** Operation identity/core; the operational plan and relevant factual state; activities/milestones/dependencies where defined; the **planned-vs-actual** distinction; projections/references to external professional objects; provenance/history/audit/snapshots where defined.
- **Does not own:** cross-domain meaning; spatial computation; commander prioritization; professional source-system objects; a machine-generated readiness score.

> **Legacy note (not a portfolio choice):** **Operations Store** is the current Sigma portfolio responsibility for operational domain truth. The older/broader **Operations Repository (CAT-010)** knowledge concept is **not** a competing current portfolio component and does **not** make the existence, role, or portfolio position of Operations Store unresolved. Any remaining reconciliation between CAT-010 and current Operations Store material is a **legacy / domain-knowledge** reconciliation question — **not** an unresolved Product Portfolio decision.

### Geography / Spatial Intelligence
- **Role:** spatial intelligence and **Spatial Evidence.**
- **Exists because:** spatial questions are **reusable organizational capabilities, not map-screen features.**
- **Current product capability model:** **Spatialize · Resolve · Relate · Reconstruct · Qualify** — the current product-level model, **not** historical.
- **Abstraction levels:** **Spatial Evidence** = the product/business abstraction; **SpatialResult** = the technical/contract representation.
- **Owns:** spatial computation, spatial relations, and Spatial Evidence. **Does not own** the broader operational "so what."

### Context & Meaning
- **Role:** cross-domain synthesis **when required.**
- **Exists because:** some user questions cannot be answered from one domain truth alone.
- **Owns:** synthesis across relevant domain evidence; operational meaning; evidence-backed **Operational Signals**.
- **Operational Signal:** an **evidence-backed statement/output of operational meaning produced by C&M** — **not** raw data, event, or observation ([D-19](../05-DECISIONS/DECISION-LOG.md)).
- **Critical boundary — C&M is not mandatory middleware.** `Operations Store → Zira` is valid when factual domain truth is sufficient; `Operations + Geography → C&M → Zira` is used when cross-domain interpretation is required.

### Zira
- **Role:** Sigma's **product / experience layer.**
- **Exists because:** users should interact with Sigma through coherent **task- and role-oriented experiences**, not by manually reconstructing context across capabilities.
- **Does:** compose, present, enable interaction/action, and consume domain truth and synthesized meaning.
- **Does not** become the source of truth merely because information is visible or editable there.

### Commander Space *(module inside Zira)*
- **Role:** a role/context-oriented user-facing module for **attention, understanding, decision and action** — **decision-first, not dashboard-first** — consuming trusted facts and meaning from Sigma capabilities.
- **Boundary:** it is **one module inside Zira, not all of Zira.** It is **Zira's role-based personal operational workspace** — serving commanders **and other operational roles**, decision-first, **not** an all-information dashboard. **My Space** is **absorbed** into Commander Space (not a separate product); **Headquarters Workspace** is **not** a current canonical module (its Operational Awareness learning remains a reusable experience pattern). *(Owner decision [D-22](../05-DECISIONS/DECISION-LOG.md); current truth in `03-EXPERIENCE/Commander-Space/README.md`.)*

### Operations Management *(module inside Zira)*
- **Role:** a user-facing module for **operational planning and management workflow**; current direction evolved from standalone GANTTIT.
- **Current stable scope:** create/edit Operations and Activities; **Flat** as a primary/default management view; basic **Gantt**; **Operation Page**; lifecycle context around **Plan → Approval → Execution → Closure**.
- **Boundary:** Operations Management owns the **workflow/experience**; **Operations Store** owns the canonical Operation representation and domain truth. Open permissions/stewardship/approval-governance questions are **not** silently resolved here (§10).

### Shared Capabilities *(portfolio category, not an invented product list)*
A category of cross-cutting capabilities that other parts of the portfolio consume — for example trust/provenance, semantic/entity foundations, decision-support foundations, AI foundations, and reusable experience principles. These are **portfolio building blocks, not new standalone products**; nothing here is packaged into a product except where current repository truth independently supports it.

---

## 5. User needs → portfolio responsibilities

A compact traceability map (synthesized from discovery/persona evidence — not six reproduced personas). The point is `Need → Portfolio responsibility`, never `Need → predetermined feature`.

| Recurring need | Typical question | Primary responsibility | Also involved when… |
|--|--|--|--|
| Shared operational truth | "What is actually true about Operation X?" | **Operations Store** | — |
| Planned vs actual | "What changed between what we planned and what is happening?" | **Operations Store** (factual distinction/history) | **C&M** when cross-domain interpretation is needed; **Zira** for presentation/action |
| Spatial context | "What is in / near / related to this operational space?" | **Geography** | — |
| Cross-domain impact / meaning | "What does this combination of facts mean for my operation?" | **Context & Meaning** | — |
| Role-specific attention | "What requires me now?" | **Zira / Commander Space** | — |
| Operational management | "How do I create, update, plan and manage the operation?" | **Zira / Operations Management** (backed by **Operations Store**) | — |

---

## 6. Portfolio interaction patterns

Valid patterns — these are **interaction patterns, not one mandatory processing pipeline**:

- **Factual operational question:** `Professional Source → Operations Store → Zira` (no C&M required).
- **Spatial question:** `Relevant Source(s) → Geography → Zira` (no C&M required if Spatial Evidence is sufficient).
- **Cross-domain interpretation:** `Operations Store + Geography + other evidence → Context & Meaning → Zira`.
- **Operational management:** `User → Operations Management → Operations Store`, with external professional systems retaining ownership of their own professional objects.

A user may enter at the pattern appropriate to the task; not every interaction passes through synthesis.

---

## 7. Portfolio boundaries

The boundaries that keep the portfolio coherent:

- **Operations Management ≠ Operations Store** (workflow/experience vs canonical truth).
- **Geography ≠ a map UI** (reusable spatial intelligence/evidence, not a screen).
- **Context & Meaning ≠ mandatory middleware** (used only when synthesis is required).
- **Zira ≠ source of truth** (it presents/acts; it does not own domain truth).
- **Commander Space ≠ Zira** (one module inside the experience layer, not the whole of it).
- **User-facing ownership ≠ information ownership** (seeing/editing something does not own it).
- **A shared capability ≠ automatically a standalone product.**
- **A reusable capability should emerge from demonstrated repeated need, not platform-first abstraction.**

---

## 8. Portfolio maturity

The current delivery baseline for the major Sigma capability areas is **GREENFIELD / SETUP REQUIRED** ([D-20](../05-DECISIONS/DECISION-LOG.md); [`CURRENT-STATE.md`](../CURRENT-STATE.md)).

Existing PRDs, HLDs, ADRs, schemas, contracts, Golden-E2E definitions, strategy artifacts and prototypes are **product/architecture knowledge** — they do **not**, by themselves, prove BUILDING / PILOT / LIVE. This document asserts **no** delivery state and **no** roadmap dates.

---

## 9. Portfolio evolution

The portfolio is expected to evolve. Keep three things distinct:

- **Stable portfolio responsibility** — the kind of ownership a part holds (truth / spatial / meaning / experience). This should be durable.
- **Current product direction** — how a part is currently shaped (e.g. Operations Management's Flat/Gantt/Operation-Page direction). This can change.
- **Candidate / future capability** — direction that is not yet committed.

A product/capability may change shape without arbitrarily moving its **core ownership**. Historical strategy artifacts are evidence of the path taken, not automatically the current product model.

---

## 10. What is intentionally NOT decided in this document

Left open (not invented):

- the exact future **Zira module inventory**,
- **Operations Management role permissions and approval governance**,
- future **standalone/shared capability packaging**,
- delivery **dates**,
- **team ownership / org structure**,
- future **AI productization**.

These remain genuine open questions; this document does not resolve them.

---

## 11. Product Portfolio test

For any proposed product/capability, ask:

1. Which recurring **user/business need** does it serve?
2. Why does this need require a **distinct portfolio responsibility**?
3. Who owns the **underlying truth**?
4. Who owns the **user workflow/experience**?
5. Is **cross-domain synthesis** actually required?
6. Is **spatial computation** actually required?
7. Does the proposal **duplicate** an existing portfolio responsibility?
8. Is this a **repeated need** or a one-off feature?
9. Are we turning a **candidate capability** into a hidden commitment?
10. Can its **boundary** with neighboring capabilities be explained in **one sentence**?

This is a **portfolio decision test**, not a delivery Definition of Done. Where the proposal also touches doctrine or execution, apply the Doctrine test (DOC-001 §10) and the Operating Model test (OM-001 §14).

---

## References

- [`DOC-001 Sigma Doctrine`](../DOC/DOC-001%20Sigma%20Doctrine.md) — why Sigma exists; governing principles.
- [`OM-001 Sigma Operating Model`](../OM/OM-001%20Sigma%20Operating%20Model.md) — how Sigma builds across the portfolio.
- [`CURRENT-STATE.md`](../CURRENT-STATE.md) — current product/system model and GREENFIELD baseline.
- [`GLOSSARY.md`](../GLOSSARY.md) — Sigma/Zira, Operational Signal/Meaning, Geography capabilities.
- [`05-DECISIONS/DECISION-LOG.md`](../05-DECISIONS/DECISION-LOG.md) — the owner decisions referenced above.
- Domain and product material: Operations Store package; Geography / Spatial Intelligence; Context & Meaning; Commander Space and Operations Management (Zira).
