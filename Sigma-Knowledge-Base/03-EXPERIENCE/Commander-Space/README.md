# Commander Space

**Current product truth for Commander Space.** This document is the current source for what Commander Space is. The other files in this folder (`Commander-Space.md` / PR-014, `Headquarters/…` / PR-015, `My-Space/…` / PR-016) are **historical conceptual exploration**, retained for traceability — see *Legacy artifacts* below. *(Owner decision: [DECISION-LOG D-22](../../05-DECISIONS/DECISION-LOG.md).)*

> **Source authority:** current Owner-approved truth (this document, [CURRENT-STATE.md](../../CURRENT-STATE.md), the [Decision Log](../../05-DECISIONS/DECISION-LOG.md)) is canonical. An external prior prototype exists and was reviewed as **design evidence** (to avoid losing sound prior thinking) — it is **not** a source of current product truth and its specific UX (exact interaction contracts, screen names, widget catalogs, decision taxonomies, personas) is **not** promoted here. The next prototype should be generated *from* this Company Brain, not the reverse. *(Owner decision: [DECISION-LOG D-23](../../05-DECISIONS/DECISION-LOG.md).)*

## Problem — why this experience exists

Operational information is distributed across systems, domains and owners. Without Commander Space, a user must reconstruct — by hand, across tools — what needs their attention, why it matters to *them*, and what they can do about it. Commander Space exists to bring forward, for each user, **what requires their attention, understanding, decision, or action now** — without turning into a dashboard of everything.

## Users

**Commanders and other operational roles.** The word "Commander" describes the **decision-oriented** nature of the experience, not an exclusive user population. Users have role-specific responsibilities and operational context. *(This is the population at the right level; there is no detailed persona/RBAC model here — that is not decided.)*

## Core job

**Key business question: "What requires my attention?"** — this is the organizing question of Commander Space. Commander Space determines what from the operational world **materially requires this user**, based on `Role × Responsibility × Operational Context`, then helps them move through it.

It should answer questions such as: *What requires me now? What changed that is relevant to my responsibility? Why does it matter to me? What do I need to understand? Is a decision or approval required from me? What can or should I do now? What evidence supports this? What happened as a result?* — and it should **not** answer them by becoming a generic dashboard that contains everything.

## Experience model

```text
Attention → Understand → Decide / Approve → Act → Follow-up / Remember
```

This is a **conceptual product/experience model, not mandatory IA** — not required screens, routes, workflow stages, or sub-products. A user may **enter at the level relevant to the current need** (e.g. straight to an action, or to the evidence behind something), and drill between levels.

## Business capabilities (current)

The following are **current business capabilities/directions**, confirmed by the Owner. Each states the business question it answers; **exact UX, component names, and interaction mechanics are not locked** — where prior design work (a reviewed prototype) explored a mechanism, it is noted as *design evidence*, not canonical.

- **Attention** — *What requires me now? What changed? Why is this relevant to me? What is urgent? What requires action?* Ranks/surfaces items materially relevant to this user. **Ranking is not Recommendation** — not every important item requires or gets a recommendation.
- **Notifications / Alerts** *(supports Attention)* — a notification/alert means *something happened or changed*; **Attention** means *this change materially requires this specific user*. Not every notification should become an Attention item — the product should **reduce noise**, not reproduce every source-system notification.
- **Situation Assessment** — helps the user build/understand the relevant operational picture for their current role, responsibility and business question. *(Design evidence: a prior prototype explored context-scoped, native-widget composition for this — useful evidence of feasibility, not a locked board/catalog design.)*
- **Native / Domain Capability Composition** — Commander Space should be able to **compose relevant native/domain capabilities** according to role, responsibility, operational context, and the current business question. Potential capabilities may include map/spatial context, operations, timeline, Gantt/planning context, approvals, alerts, directives, dependencies, evidence/trust and operational status — **illustrative, not a locked widget catalog.** Commander Space is not a fixed dashboard, not a generic widget wall, and not a replacement for professional systems.
- **Decision Support** — provide enough situation, meaning/impact, evidence and context for the user to make the required decision. Do **not** force a decision where none exists, a recommendation where none is justified, or alternatives where none are meaningful. The human remains the decision owner. *(Design evidence: a prior prototype explored a specific recommendation-contract structure — useful evidence, not a canonical contract.)*
- **Approvals** — *What requires my approval? What is currently waiting for my approval?* Direction includes: aggregation of approvals relevant to this user; context to understand the approval; evidence and relevant dependencies; indication when required conditions/information are missing; completing the approval from Zira where authority/integration permits; follow-up/status after the approval. *(The concept is current; a literal name like "Approval Hub," exact screen design, and integration mechanics are not locked.)*
- **Directives / Follow-up** — the user should be able to understand which instructions/directives are relevant, what resulted from a decision, who/what is affected, whether acknowledgement/follow-up is required, and what happened after the instruction/decision. *(Exact directive mechanics from prior design work are not promoted as canonical.)*
- **Knowledge Continuity** — *What happened since I was last here? What decisions were made? What happened because of them? What remains unresolved? What previous knowledge is relevant now?* The product should preserve continuity across time and handoffs. *(Exact Timeline/"Executive Brief"-style implementations remain design choices, not canonical.)*
- **Evidence & Trust** — a cross-Sigma principle and a Commander Space experience requirement: users should understand the basis of important information, meaning, or decision context. *(Prior drawer/component implementations are design evidence, not canonical UX.)*

## Commander Space boundary

**Commander Space does not own every workflow that generates attention.** It owns the experience of determining what requires the user, providing enough context to understand it, and enabling the appropriate decision, approval, or action. Therefore: **Planning** can generate something requiring attention; **Control / Event Management** can generate something requiring attention; **Operations Store** can expose factual operational change; **Geography** can provide relevant Spatial Evidence; **Context & Meaning** can provide cross-domain meaning/signals. Commander Space can **surface** these without absorbing their underlying workflows or information ownership.

## Personalization

```text
Role × Responsibility × Operational Context → relevant Attention / Context / Actions
```

Personalization changes **attention, context, prioritization and available actions** — it does **not** change the underlying facts. The **same operational fact may be surfaced differently to different roles without creating different versions of truth.** Underlying domain truth remains **shared and source-owned.** *(This is a product intent, not a technical personalization architecture or rules engine — no such implementation is decided here.)*

## Inputs (responsibility level)

Commander Space consumes, as needed:

- **Operations factual state** (from Operations Store),
- **Spatial Evidence / spatial context** (from Geography),
- **Operational Signals / cross-domain meaning** (from Context & Meaning) **when synthesis is required**,
- other trusted Sigma capabilities when applicable.

*(No technical interfaces are specified here.)*

## Boundaries — what Commander Space is NOT

- **Not a dashboard of everything.**
- **Not a source of truth** (it presents/acts; it does not own domain truth).
- **Not Operations Management** — a separate Zira module owns creating/managing operations (the **Planning** territory).
- **Not the Control / Event Management world** — that territory owns the operational-event lifecycle (initial report → accumulating information → decisions/directives/actors → handling → closure); Commander Space may surface an event-derived attention item without owning that workflow.
- **Not a GIS product** — it may consume Spatial Evidence but does not compute geography.
- **Not Context & Meaning** — it does not recreate cross-domain synthesis; C&M remains optional.
- **Not restricted to commanders.**
- **Does not own professional-system data.**

## Relationship to My Space

**My Space is no longer a separate current product concept.** Its personalized-workspace intent is **absorbed into Commander Space** (Commander Space *is* the role-based personal workspace). PR-016 and its history are preserved for traceability; current truth does **not** require a separate My Space sub-product.

## Relationship to Headquarters Workspace

**Headquarters Workspace is not a current canonical module or required sub-workspace.** Its validated product **learnings remain reusable experience capabilities/patterns** — particularly **Operational Awareness** and the question *"what changed in the operational picture?"* (change → meaning → ownership → action where appropriate). These may be **composed into Commander Space or other Zira modules when relevant**, but the old workspace structure is not automatically preserved. PR-015 and its history are retained as evidence.

## Relationship to other Sigma responsibilities

- **Zira** is Sigma's product/experience layer; Commander Space is **one module inside Zira** (Commander Space ≠ Zira).
- **Operations Management** is a separate Zira module (part of the **Planning** territory — see below); a user may move from something requiring attention in Commander Space into the relevant Operations Management context/action when appropriate. *(No detailed navigation is defined here.)*
- **Planning** — *what are we planning, and how do we prepare/manage it?* A business territory being brought into Zira (operations, operational plans, activities, timelines, dependencies, preparation, Gantt/planning experiences). Operations Management / GANTTIT provides important prior learning for this territory. Commander Space may surface attention generated by Planning without owning the planning workflow.
- **Control** — *what is happening now, and how do we manage/respond to it?* Exists today inside the Zira world through the current **Event / Combat Management** capability. Commander Space may surface attention generated by Control without owning the event-management workflow. *(See [`CURRENT-STATE.md`](../../CURRENT-STATE.md) for the full Control-territory description.)*
- **Operations Store** owns operational domain truth; Commander Space consumes facts, it does not own or recreate them.
- **Geography** owns spatial computation and Spatial Evidence; Commander Space consumes spatial context.
- **Context & Meaning** provides evidence-backed meaning / Operational Signals when synthesis is required; Commander Space may consume trusted domain facts **directly** when synthesis is not required.

**The final product packaging of Planning and Control (separate modules, one module with modes, or another composition) is intentionally not decided.** The business territories are clear; their packaging is not (see [DECISION-LOG D-24](../../05-DECISIONS/DECISION-LOG.md)).

## Current delivery reality

**GREENFIELD / SETUP REQUIRED.** This is current product direction, not implementation. Do not infer that any of it is built from prototypes or older conceptual documents.

## Open questions (genuinely unresolved)

- Detailed personalization model (how role/responsibility/context resolve to surfaced attention/actions) — intentionally not a rules-engine spec yet.
- Which reusable experience patterns (e.g. Operational Awareness) are composed first, and the first meaningful Commander Space product validation.
- Detailed navigation between Commander Space and Operations Management (Planning) and between Commander Space and Control / Event Management.
- Exact mechanics for each business capability above (Attention ranking, Situation Assessment composition, Decision Support contract, Approvals aggregation/completion, Directives, Knowledge Continuity, Evidence & Trust) — the **capabilities are current direction; their UX is not locked.**
- Final packaging of Planning and Control (separate modules / one module with modes / other composition).

*(The composition decision itself — role-based personal workspace, My Space absorbed, Headquarters not a current module — is **resolved** and is not an open question.)*

## Legacy artifacts (historical — retained for traceability)

- `Commander-Space.md` (PR-014), `Headquarters/Headquarters-Workspace.md` (PR-015), `My-Space/My-Space.md` (PR-016) are **earlier conceptual exploration**. They record *what was explored then*; **this README is what is true now.** They are preserved, not rewritten.

## Where to go next

- [`CURRENT-STATE.md`](../../CURRENT-STATE.md) and [`DOCUMENT-REGISTRY.md`](../../DOCUMENT-REGISTRY.md).
