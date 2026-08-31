# Operations Management

**Status:** v0.1 — Company Brain / Owner Truth (2026-08-30)
**Type:** Product definition (module inside Zira — Sigma's product/experience layer)
**Delivery baseline:** GREENFIELD / SETUP REQUIRED — this document defines product direction, not implemented capability.

> Operations Management is the **user-facing module for creating, editing and managing Operations, Activities and the operational lifecycle**. It uses **Operations Store** as its canonical operational backbone. It is a module inside **Zira** (Sigma's product/experience layer) — distinct from Operations Store (a Sigma domain capability) and **not** part of Commander Space.

---

## 1. Problem

Operational management artifacts and state have historically been spread across systems, documents, and parallel tools in different environments, with no single place to create and manage an operation as a coherent unit connected to its plan, activities, dependencies and relevant external state.

The prior direction — a **standalone GANTTIT application** — was evaluated in discovery and found not to be the right target product. Discovery identified major problems, including:

- lack of meaningful adoption,
- a complex workflow/wizard,
- performance friction,
- unclear UX and high operational friction,
- continued reliance on slide-based workarounds,
- and parallel operational-management systems in different environments.

The underlying user/business need remains: operational leaders and planners need a low-friction way to **create and manage operations and activities**, see plan structure and dependencies, and understand relevant operational state — without rebuilding context by hand across tools.

## 2. Product decision

**Standalone GANTTIT → Operations Management, a module inside Zira.**

- Do **not** rebuild GANTTIT as a standalone application.
- Its relevant capability becomes the Operations Management module (מודול ניהול מבצעים) inside Zira.
- The direction is intentionally **simpler** than GANTTIT.

*(This is a material change of direction and should be recorded in Decision History: **Standalone GANTTIT → Operations Management module inside Zira**.)*

## 3. Users

The current product model has **three user layers**:

**Layer 1 — Long-term operational planning.**
Roles such as **רמ"ד מבצעים** and relevant long-term planning functions. Primary concerns:
- longer-term operational planning,
- creating/managing operations,
- operational envelopes,
- approvals where applicable.

**Layer 2 — Short-term operational control.**
Roles such as **קצינות חמ"ל, רמ"די שליטה, מנל"חים** and equivalent control functions. Primary concerns:
- the upcoming 24–48/72 hour operational picture,
- short-term operational updates,
- consuming the integrated operational picture,
- understanding operations together with relevant influencing factors and schedules.

**Layer 3 — Consumers and professional contributors.**
Commanders and relevant staff/professional functions such as intelligence, engineering, legal, UN liaison, logistics and others. These users primarily **consume** the operational picture; some professional functions may also **contribute** relevant thematic operational information.

> **Explicitly open (do not infer from the model above):** exact permissions; create/update authority by role; data stewardship; role-specific approval authority. These are open decisions (§8), not established fact.

## 4. Product boundary

Operations Management is one module among several; keep these responsibilities distinct:

| Concern | Owner | Note |
|--|--|--|
| **Create/edit/manage operations UX** | **Operations Management** | this document |
| **Canonical Operation + factual operational state** | **Operations Store** | the backbone Operations Management writes to / reads from |
| **Awareness / attention / decision / action** | **Commander Space** | a *different* Zira module; Operations Management is not inside it |
| **Cross-domain synthesis & operational meaning** | **Context & Meaning** | Operations Management does not synthesize meaning |
| **Spatial computation & Spatial Evidence** | **Geography** | Operations Management consumes spatial context; it does not compute it |
| **Source-of-record professional objects** | **Professional systems** | remain owned by their source systems |

Explicitly: **do not collapse Operations Management into Operations Store**, and **do not place Operations Management inside Commander Space.**

## 5. Core experience

The current experience direction is deliberately focused:

- **Flat** — the **default** operational management view.
- **Basic Gantt** — a timeline view of the plan.
- **Operation Page** — the page for a single operation.
- **Create / edit Operations.**
- **Create / edit Activities.**

Later views/layers may include **Map**, **Dependency**, and additional contextual layers. **The underlying relationship model must not force a graph UI onto users** — relationships are modeled underneath, but the default experience stays simple (Flat first).

## 6. Operation as the primary Context Anchor

In the product, the **Operation is the primary operational Context Anchor**. From an operation, a user can connect the relevant:

- Activities,
- milestones,
- dependencies,
- deliverables,
- other Operations,
- force structure,
- HQ schedules,
- and external professional-system state.

**External professional objects remain owned by their source systems**; Operations Management presents them through the Operations Store's projections rather than taking ownership. This document describes the **product implication** of the Context Anchor; it does **not** redefine the Operations Store schema (see the Operations Store Canonical Schema for the data contract).

## 7. Lifecycle

The current product-level lifecycle model is:

```text
Plan → Approval → Execution → Closure
```

Operations Management owns the **experience** across this lifecycle: creating an operation, editing it, adding/editing activities, milestones and dependencies, and working with planned vs. actual state (planned state is not overwritten by observed/actual — an Operations Store invariant).

> **The lifecycle *model* is known; detailed lifecycle *governance* is not yet fully defined.** Keep explicitly open (do not invent workflow rules): entry/exit criteria for each stage; exact responsibility per stage; approval chain by operation type; required professional endorsements; transition permissions; exception/rejection/reopen behavior. Note also that approvals currently exist as a *factual projected status* in the Operations Store (`not required / pending / approved / rejected`), which is distinct from a designed approval workflow. These remain open decisions (§8).

## 8. Phasing / delivery

Operations Management is the user-facing surface for the operational-state capabilities the execution plan places early (see [`../../../07-EXECUTION/EXECUTION-MODEL.md`](../../../07-EXECUTION/EXECUTION-MODEL.md)):

- **Unified Operation** (canonical model, registry, stable IDs, time/status/owner) — P0.
- **Connected Plan** (hierarchy, milestones, dependencies, planned vs actual) — P0.

The simpler Flat/Gantt/Operation-Page experience is the intended first management surface over that operational state. **Delivery baseline is GREENFIELD / SETUP REQUIRED** — nothing here is implemented; the phasing describes intended sequence, not current status, and advances only through the execution Gates.

## 9. Open decisions

Genuine unresolved product decisions (do not treat as settled):

1. Detailed **role model / permissions** for Operations Management.
2. **Approval workflow** and any state-transition/lifecycle rules (beyond the Store's factual status).
3. Exact scope and behavior of **Flat vs Gantt vs Operation Page** (fields, editing model, defaults).
4. **When** Map / Dependency / other contextual layers are introduced, and their interaction model (without forcing a graph UI).
5. How **force structure, HQ schedules and deliverables** are surfaced and edited vs. merely referenced.
6. The boundary between **native owned fields** and **external projections** in the create/edit experience.
7. Relationship to the Operations Store's own open decisions (status vocabularies, Must-Connect systems, snapshot triggers).

---

## Next Product Step — Validate the First Vertical Slice

> **The first Operations Management Vertical Slice is NOT defined yet, and must not be locked before targeted workflow discovery.** The repository contains strong target-state / product-direction material but **insufficient observed evidence** of the lived current workflow.

### Current hypothesis (not validated truth)

- **Leading candidate user population — HYPOTHESIS:** the short-term operational-control layer — **קצינות חמ"ל, רמ"די שליטה, מנל"חים**, and equivalent operational-control roles.
- **Candidate operating horizon — HYPOTHESIS:** **24–72 hours.**
- **Candidate JTBD — HYPOTHESIS:** *Maintain a current, shared operational picture for the next 24–72 hours: understand relevant operations, absorb changes, update operational state, and ensure the picture used by the headquarters reflects the current situation.*

This is a **product hypothesis, not validated workflow truth.** Do **not** convert it into fact, and do **not** lock the first Vertical Slice before the discovery below is completed.

### Discovery TODO (for the incoming Product Lead)

Conduct **~2–3 focused workflow sessions** with representative short-term operational-control users — prefer **one קצינת חמ"ל, one רמ"ד שליטה, and optionally one מנל"ח** if the workflow materially differs. Use a **real recent operation** and ask users to **show the actual workflow and tools**, not describe desired features. Establish:

1. **Entry** — how an operation enters the 24–72h control horizon, from whom, and in which artifact/system.
2. **Current toolchain** — the actual systems, files, presentations and communication channels used to maintain the picture.
3. **Change workflow** — how a real operational change is received, validated, updated and propagated.
4. **Write ownership** — who may update which information.
5. **Planned vs Actual** — whether/how planned state and current/actual state are distinguished today.
6. **Minimum trusted picture** — the minimum information the user must see *together* to perform the job.
7. **Presentation role** — whether slides are the working copy, integration layer, briefing artifact, communication artifact, or a combination.
8. **Escalation boundary** — what can be updated directly vs what requires coordination, escalation, decision or approval.
9. **Exit** — when the operation leaves short-term-control responsibility and what must be handed over/preserved.
10. **Success evidence** — what observed behavior would prove the first slice has replaced a meaningful part of the current workflow.

### Discovery method

Do **not** lead with proposed solutions (Flat, Gantt, Operation Page, alerts, approvals). For each session walk a real case:

```text
Real Operation → Entry → Understand → Maintain → Change → Coordinate/Escalate → Exit
```

Whenever possible, ask **"Show me."** Record each finding as **Observed**, **User-stated**, or **Inferred**.

**Key validation question:** *If the presentation disappeared tomorrow, what could the user no longer do?* Do **not** assume the goal is to eliminate PowerPoint. Determine whether the presentation is a **working copy**, a **manual integration layer**, a **communication/briefing artifact**, or a **combination** — this finding may materially change the first slice.

### Exit criteria for this TODO

Complete **only** when the Product Lead can evidence, without assumption:

```text
Operation enters → responsibility/handoff → information consumed → updates performed →
changes propagated → escalation/decision boundary → exit/handoff
```

and can answer: **Who is the first user? What is the first JTBD? What is the slice entry? What is the slice exit? What information must be available? What can the user update? What current workaround/artifact is being replaced or materially reduced? What observed evidence constitutes GO?**

Only then should the first Operations Management Vertical Slice be locked.

### Explicitly NOT decided yet (do not treat as locked for Slice 1)

Until this TODO is completed, none of these are validated first-slice requirements — they remain **possible product responses**, not requirements:

- Create Operation as the center of the slice
- Flat as the center of the slice
- Gantt as the center of the slice
- Operation Page as the center of the slice
- eliminating PowerPoint
- full approval flow
- detailed RBAC / permissions
- Map
- dependency graph
- Commander Space integration

---

*Sources: Owner Truth (2026-08-30); Operations Store PRD/HLD/ADR ownership boundaries; execution handoff (Operations capabilities); repository references to the operations-management module (Zira / מודול ניהול מבצעים); the 24–72h workflow reconstruction (found insufficient observed evidence to define the first slice). This is a product definition at GREENFIELD baseline; no implementation is implied, and the first Vertical Slice is an open hypothesis pending discovery.*
