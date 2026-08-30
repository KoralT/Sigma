# CURRENT STATE — Sigma

> The fastest reliable orientation to Sigma for a new Product Lead, Engineering Lead, or Architect. Read this before anything else.
>
> **Two things to hold at once:**
> 1. Sigma has **substantial, decided product and architecture direction** (domain contracts, accepted ADRs, an execution plan).
> 2. **None of it is implemented yet.** The current delivery baseline is **GREENFIELD / SETUP REQUIRED**.
>
> **Current product/architecture truth ≠ current implementation.** A PRD, HLD, ADR, schema, contract, Golden-E2E definition, prototype, or strategy doc is **not** evidence that a capability is operational, deployed, pilot-ready, or live. Use a more specific delivery status **only** where explicit implementation evidence exists (today, there is none in the repository).

---

## 1. What Sigma is, and the problem it solves

Sigma exists to **reduce the distance between Information → Understanding → Decision → Execution** for operational organizations.

Today, operational information is scattered across professional systems; understanding an operation, what it means, and what needs attention requires manual cross-referencing and verbal handoff. Sigma turns fragmented information into shared, trusted understanding and brings it to the point of human decision and action.

Sigma is **not one application**, and it **does not replace professional/source systems** — those remain the owners of their own data.

## 2. Current product / system model

```text
Professional Systems
        ↓
Domain Capabilities            (Operations, Geography, …)
        ↓
   ┌───────────────┐
   │               │
   ↓               ↓
Context & Meaning → Zira  (Sigma's experience layer)
                       ↓
                 Human Decision & Action
```

**Context & Meaning is NOT mandatory middleware.** The experience layer may consume trusted domain facts **directly** when no cross-domain synthesis is required:

```text
Operations Store → Zira            (factual operational state, no synthesis needed)
```

When cross-domain interpretation **is** required, it goes through Context & Meaning, which owns synthesis and meaning:

```text
Operations + Geography → Context & Meaning → Zira
```

The experience layer must **not** recreate cross-domain synthesis itself. **Human authority remains responsible for operational decisions.**

## 3. Sigma vs Zira (product/module view)

**Sigma is the wider system / capability ecosystem** — the domain and shared capabilities that establish trusted facts, computation, synthesis and reusable organizational capabilities. **Zira is Sigma's product / experience layer** for users; it contains the user-facing modules. Commander Space is **not** the container of every Sigma capability — it is one module **inside Zira**. Operations Management is **also** a module inside Zira (Commander Space does **not** contain Operations Management).

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

Operations Store, Geography / Spatial Intelligence, and Context & Meaning are **Sigma domain/shared capabilities, not Zira modules.**

*(This is a product/module view, not a strict technical deployment hierarchy.)*

## 4. Domain boundaries

| Domain / module | Question it answers | Owns | Does NOT own |
|--|--|--|--|
| **Professional systems** | — | their source-of-record objects | anything in Sigma |
| **Operations Store** | *what is planned/executing?* | canonical Operation + relevant factual state, plan, activities, dependencies, projections, snapshots/audit | UX, cross-domain meaning, GIS, readiness score |
| **Operations Management** | *how do I create/manage operations?* | the user-facing create/edit/manage experience (Flat, Gantt, Operation Page) | the canonical data (that's the Store) |
| **Geography** | *what is happening in space?* | spatial computation, spatial relations, **Spatial Evidence** | operational "so what" |
| **Context & Meaning** | *what does it mean together?* | cross-domain synthesis, impact, **Operational Signal** | domain truth, commander priority |
| **Commander Space** | *what must the commander understand & do?* | awareness, attention, investigation, decision, action, approvals, continuity | domain truth, synthesis, source-of-truth |

## 5. The domains and modules today

**Operations Store** — the **canonical operational backbone**: the canonical Sigma representation of an Operation (the Context Anchor) plus relevant factual state (plan, activities, milestones, dependencies, relationships, projections of external professional state), with provenance/freshness, planned-vs-actual separation, decision snapshots and audit. It exposes factual status, **not** a machine readiness score. *(Contract-backed: PRD/HLD/8 ADRs/Canonical Schema v0.1/API+Event v0.1/Golden-E2E — still `.docx` under `Operations-Store/`.)*

**Operations Management** — the **module inside Zira** for creating, editing and managing Operations, Activities and the operational lifecycle. It **uses Operations Store as its canonical backbone**. Current direction is intentionally simpler than the former standalone GANTTIT: **Flat as the default view, basic Gantt, Operation Page, create/edit Operations & Activities.** See [`02-DOMAINS/Operations/Product/Operations-Management.md`](02-DOMAINS/Operations/Product/Operations-Management.md). *(Distinct from Operations Store; not part of Commander Space.)*

**Geography / Spatial Intelligence** — a **Federated Spatial Intelligence Layer**: sources own the data; Geography owns the spatial language and computation and returns **Spatial Evidence** with provenance/time/completeness. The current **product capability model** is **Spatialize · Resolve · Relate · Reconstruct · Qualify** (product-level capabilities). The technical contract exposes a spatial operation set and returns a **SpatialResult** — this is the **contract/technical representation** of the same thing; **product capabilities and API operations are different abstraction levels and need no 1:1 mapping.** Default is federate + compute; persist only by explicit ADR. *(PRD/HLD/10 accepted ADRs.)*

**Context & Meaning (C&M)** — owns **cross-domain synthesis and operational meaning**. Its canonical output is the **Operational Signal**: *an evidence-backed statement of operational meaning produced by C&M.* It is **not** a raw event, a raw observation, or an uninterpreted data point (raw source events remain distinct factual inputs). C&M synthesizes over an Evidence Gate, preserves conflicts, and does **not** set commander priority. *(PRD/HLD/13 accepted ADRs.)*

**Commander Space** — the personal/commander experience for **awareness, attention, investigation, decision, action, relevant approvals, and knowledge continuity**. Current direction is **decision-first, not dashboard-first**:
- **Headquarters** awareness leads with *"מה השתנה בתמונה המבצעית?" (what changed in the operational picture?)*, distinguishing **what changed · operational meaning · ownership/responsibility · action only where a real action exists.** Ownership attribution ≠ a call-to-action, and the experience must not imply exhaustive awareness where evidence does not support it.
- **My Space** similarly opens on *what requires this user's attention now*, not a generic dashboard.
*(These are current product/UX directions, not evidence of implementation.)*

## 6. Execution model (summary)

Delivery runs on **Business Problem → Vertical Slice → Required Domain Capabilities → Reusable Capabilities → End-to-End Evidence**, starting from a business slice (not team roadmaps). A capability is not "done" because it exists; a quarterly **Gate** must prove the business outcome, the DoD, end-to-end behavior, and reuse. Priorities are tiered **P0 (build this year) / P1 (after Foundation + Gate) / P2 = NOT YET (direction, not commitment)**. Full detail: [`07-EXECUTION/EXECUTION-MODEL.md`](07-EXECUTION/EXECUTION-MODEL.md) (human-readable) and the source planning artifact `07-EXECUTION/Handoffs/SIGMA-FINAL-EXECUTION-HANDOFF-2026-2027.xlsx`.

## 7. Current delivery baseline — **GREENFIELD / SETUP REQUIRED**

All major current Sigma capability areas **require setup from zero**: Operations Store, Operations Management, Geography / Spatial Intelligence, Context & Meaning, and Zira and its product modules (Commander Space, Operations Management). No code, test, deployment, pilot, or live evidence exists in the repository. Treat every capability as not-yet-built until implementation evidence appears.

## 8. What is Established vs Direction vs NOT YET

- **Established (decided product/architecture, not built):** the layered model and boundaries; Operations Store contract + 8 ADRs; Geography federation + 10 ADRs; the 5-capability Geography product model; C&M Operational-Signal model + 13 ADRs; the execution model, P0/P1/NOT-YET tiers, five vertical slices, and quarterly gates; the GANTTIT → Operations Management decision.
- **Direction (current product/UX intent):** Commander Space decision-first framing (HQ "what changed", My Space attention-first); Operations Management simpler experience (Flat/Gantt/Operation Page); Geography Text↔Map (P1).
- **NOT YET (kept as direction, explicitly not committed):** Digital Twin / simulation, broad What-if, Multimodal Geo production, counterfactual reasoning, autonomous recommendations.

## 9. Major unresolved decisions

1. **Operations Store ↔ Operations Repository (CAT-010)** — kept distinct; full semantic reconciliation still open. (And both distinct from the archived **Operational Repositories** product concept, PR-017.)
2. **Operations Management** lifecycle/workflow specifics (approval workflow, exact role model, when Map/Dependency layers appear) — not yet defined.
3. Many domain **v0.1 "open decisions"** (status vocabularies, Must-Connect sources, snapshot triggers, retention, authorization/compartmentalization, CRS strategy, first Text→Map intents).
4. **Named-but-undefined terms** in engineering material: Evidence Gate, Trust Contract, Capability Mesh.
5. Foundational doctrine (DOC-001/OM-001/PR-001/RS-001) remains **unwritten (shells)**.

> **Note for maintainers:** the control-plane docs (`GLOSSARY.md`, `DOCUMENT-REGISTRY.md`, `05-DECISIONS/DECISION-LOG.md`) still describe the pre-3B product hierarchy and the (now-resolved) Operational Signal conflict. They should be updated in a following pass to match this Owner Truth (Sigma-as-ecosystem with Zira as its product/experience layer, Operational Signal resolution, GANTTIT → Operations Management, GREENFIELD baseline). That update was intentionally out of scope for this content-hardening batch.
