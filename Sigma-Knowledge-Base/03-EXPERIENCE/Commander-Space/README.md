# Commander Space

**Current product truth for Commander Space.** This document is the current source for what Commander Space is. The other files in this folder (`Commander-Space.md` / PR-014, `Headquarters/…` / PR-015, `My-Space/…` / PR-016) are **historical conceptual exploration**, retained for traceability — see *Legacy artifacts* below. *(Owner decision: [DECISION-LOG D-22](../../05-DECISIONS/DECISION-LOG.md).)*

## Problem — why this experience exists

Operational information is distributed across systems, domains and owners. Without Commander Space, a user must reconstruct — by hand, across tools — what needs their attention, why it matters to *them*, and what they can do about it. Commander Space exists to bring forward, for each user, **what requires their attention, understanding, decision, or action now** — without turning into a dashboard of everything.

## Users

**Commanders and other operational roles.** The word "Commander" describes the **decision-oriented** nature of the experience, not an exclusive user population. Users have role-specific responsibilities and operational context. *(This is the population at the right level; there is no detailed persona/RBAC model here — that is not decided.)*

## Core job

Bring forward **what requires this user's attention, understanding, decision or action now**, according to their role, responsibility and operational context.

It should answer questions such as: *What requires me now? What changed that is relevant to my responsibility? Why does it matter to me? What do I need to understand? Is a decision required from me? What can or should I do now? What evidence supports this?* — and it should **not** answer them by becoming a generic dashboard that contains everything.

## Experience model

```text
Attention → Understand → Decide → Act
```

This is a **product/experience model, not a mandatory UI flow** — not four required screens, routes, workflow stages, or sub-products. A user may **enter at the level relevant to the current need** (e.g. straight to an action, or to the evidence behind something), and drill between levels.

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
- **Not Operations Management** — a separate Zira module owns creating/managing operations.
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
- **Operations Management** is a separate Zira module; a user may move from something requiring attention in Commander Space into the relevant Operations Management context/action when appropriate. *(No detailed navigation is defined here.)*
- **Operations Store** owns operational domain truth; Commander Space consumes facts, it does not own or recreate them.
- **Geography** owns spatial computation and Spatial Evidence; Commander Space consumes spatial context.
- **Context & Meaning** provides evidence-backed meaning / Operational Signals when synthesis is required; Commander Space may consume trusted domain facts **directly** when synthesis is not required.

## Current delivery reality

**GREENFIELD / SETUP REQUIRED.** This is current product direction, not implementation. Do not infer that any of it is built from prototypes or older conceptual documents.

## Open questions (genuinely unresolved)

- Detailed personalization model (how role/responsibility/context resolve to surfaced attention/actions) — intentionally not a rules-engine spec yet.
- Which reusable experience patterns (e.g. Operational Awareness) are composed first, and the first meaningful Commander Space product validation.
- Detailed navigation between Commander Space and Operations Management.

*(The composition decision itself — role-based personal workspace, My Space absorbed, Headquarters not a current module — is **resolved** and is not an open question.)*

## Legacy artifacts (historical — retained for traceability)

- `Commander-Space.md` (PR-014), `Headquarters/Headquarters-Workspace.md` (PR-015), `My-Space/My-Space.md` (PR-016) are **earlier conceptual exploration**. They record *what was explored then*; **this README is what is true now.** They are preserved, not rewritten.

## Where to go next

- [`CURRENT-STATE.md`](../../CURRENT-STATE.md) and [`DOCUMENT-REGISTRY.md`](../../DOCUMENT-REGISTRY.md).
