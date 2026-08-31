---
id: OM-001
title: Sigma Operating Model
version: 2.0
status: Draft
classification: Foundational
owner: Sigma
last_updated: 2026-08-30
---

# Sigma Operating Model

The Sigma Operating Model explains **how Sigma turns a business/operational need into a coherent cross-domain capability and a real user outcome.** Where the [Sigma Doctrine](../DOC/DOC-001%20Sigma%20Doctrine.md) says *why* Sigma exists and what must remain true, this document says *how Sigma operates* to build it — how work enters, how a problem becomes a Vertical Slice, how responsibility is divided, and how contracts, evidence and gates connect.

It is an **operating model**, not an org chart, RACI, architecture specification, delivery methodology, roadmap, portfolio catalog, or team-topology proposal. It does not invent teams, roles, committees, or cadences; where the repository is silent on organizational structure, the model stays principle-based. It is governed by the Doctrine — its principles (Doctrine §5) are the reasoning behind the behaviors below.

---

## 1. Start from the business problem

Sigma work should **not** begin from "which team needs features?", "which platform component should we build?", or "which system should own this screen?". It begins from a concrete **operational/business outcome.** The primary execution unit is the **business Vertical Slice.**

```text
Business Problem / Outcome
        ↓
Vertical Slice
        ↓
Domain + Shared Capability Contributions
        ↓
Contracts / Dependencies
        ↓
Integrated E2E
        ↓
Evidence against DoD / Gate
        ↓
Reusable Capability retained for future slices
```

Teams contribute to the slice **through their domain ownership**, but the slice is evaluated **end-to-end**, on the user/business outcome — not on whether each team finished its own backlog. A domain roadmap by itself is **not** the organizing unit of Sigma execution; it provides direction that execution then converges into integrated slices (§9).

---

## 2. Responsibility model

The approved system model translated into operating responsibility.

**Professional systems / source owners.** Own their professional objects and authoritative source behavior. Sigma must **not** silently absorb professional ownership merely because information is consumed elsewhere (Doctrine §5.5, §5.9).

**Domain capabilities** (e.g. **Operations Store**, **Geography / Spatial Intelligence**). Own reusable **domain truth and computation** within their boundary and expose **stable, consumable contracts** to the rest of Sigma. A domain capability is **not** merely a backend implementation for one UI feature — it serves multiple consumers through its contract.

**Context & Meaning.** Owns **cross-domain synthesis when synthesis is genuinely required.** It consumes trusted facts/evidence from domains and produces **evidence-backed meaning** such as **Operational Signals** (an Operational Signal is not a raw event — [D-19](../05-DECISIONS/DECISION-LOG.md)). C&M is **not** inserted into every request by default; direct factual consumption from a domain is valid.

**Zira.** Owns **product / experience composition for the user's task** — how relevant capabilities and information are presented and acted upon. Zira does **not** take over domain truth or recreate cross-domain synthesis in the UI. Current modules include **Commander Space** and **Operations Management**. *(Sigma is the ecosystem; Zira is its experience layer — [D-17](../05-DECISIONS/DECISION-LOG.md).)*

---

## 3. Product ownership vs information ownership

These are different, and conflating them is a recurring, expensive mistake.

A product/module may own **workflow, interaction, prioritization, composition, user experience, and task completion.** That does **not** necessarily mean it owns the **underlying information.**

- **Operations Management** (a Zira module) may own the *workflow* for creating and managing an operation, while the **canonical organizational representation** of that operation belongs to **Operations Store**.
- **Commander Space** may *surface* an Operational Signal without owning the **evidence or domain facts** behind it.

The operating model exists in part to prevent the fallacy: *"the place where a user sees or edits something must own the underlying truth."* Presentation and editing are experience responsibilities; ownership stays with the domain/source that is authoritative for that information (Doctrine §5.5).

---

## 4. Vertical Slice operating flow

A practical, non-ceremonial flow. Not every step needs every detail finalized — only enough to avoid incompatible implementations.

**4.1 Frame the user/business outcome.** Define the real user/problem and a **measurable outcome** — not a feature list.

**4.2 Identify required truths and capabilities.** Ask: *Which domain owns each fact? Is spatial computation required? Is cross-domain synthesis actually required? What experience/workflow is needed? Which professional system remains source of truth?*

**4.3 Close foundational boundaries early.** Before teams build independently, resolve only the **foundational** decisions that would otherwise cause incompatible implementations: ownership, the minimal data model, core contracts, required IDs, planned-vs-actual semantics, provenance, and integration direction. Do **not** require every detail to be finalized first.

**4.4 Build the integrated slice.** Each domain builds its **bounded** contribution. Avoid "parallel delivery" where every team completes isolated components but **no real end-to-end exists.**

**4.5 Demonstrate with real information.** Demonstrate the integrated slice with realistic/real operational information where permitted. Synthetic mocks help during development but are **not** sufficient evidence of product integration.

**4.6 Evaluate evidence.** Use the relevant Golden-E2E / DoD / gate evidence. The point is not ceremony — it is proving the **business outcome and the required system contracts together.**

**4.7 Retain reusable capability.** After the slice, identify what should remain reusable. Do **not** generalize prematurely; a reusable capability should emerge because a **demonstrated need is likely to repeat** (Doctrine §5.6).

---

## 5. Contracts as team boundaries

Contracts let teams/domains move **independently** without each inventing its own interpretation of shared semantics. They are the seams of the operating model. Examples: **API contracts, event contracts, canonical schemas, evidence/provenance expectations, IDs, and lifecycle/state semantics.**

A contract should be **strong enough to prevent semantic divergence** (so two teams cannot quietly mean different things by "operation", "status", "planned", or "signal"), but should **not** attempt to centrally specify every implementation detail behind it. The Operations Store canonical schema/API and event contracts, and the Geography and Context & Meaning contracts, are examples of this seam — this document references them, it does not restate their designs.

---

## 6. Dependency model

Not every cross-team dependency is equal. Classifying them prevents both premature blocking and late surprises.

- **Foundational dependency** — defines ownership or shared semantics, and so must be resolved **before independent implementation of a slice that depends on it.** Examples: who owns Operation identity; planned vs actual; the Geography ↔ Operations boundary; the definition of Operational Signal. It is resolved early **for the slices that depend on it** (§4.3) — not turned into a standing global prerequisite.
- **Integrative dependency** — teams can develop separately but must **connect before the slice is considered successful.** Examples: a UI consumes a domain API; C&M consumes Geography evidence; an event propagates into the experience.
- **Future / candidate dependency** — related to a future direction and **must not block current delivery.** A candidate/future capability must never become a **hidden prerequisite** of the current slice (Doctrine §5.10).

**Blocking is scoped, not global.** An unresolved foundational dependency blocks a Vertical Slice **only when that slice depends on the unresolved ownership, semantic, contract, or authority decision.** The mere existence of an open question does not make it a global Sigma blocker. **Open questions should be resolved at the latest before the first Vertical Slice that materially depends on them — not made global prerequisites merely because they exist.**

### Currently open foundational questions (conditional blocking scope)

These are genuine open foundational questions; each is resolved before the first slice that materially depends on it, and blocks **only** the slices that actually depend on it (none is resolved here):

- **Operations Store ↔ Operations Repository (CAT-010) semantic reconciliation** — blocks slices that depend on the **unresolved semantic boundary** between the two; a slice that does not touch that boundary is not blocked.
- **Operations Management permissions / authority / approval workflow** — blocks slices that **require those create/edit/approval authorities**; it does **not** necessarily block a simpler slice outside that scope.
- **Must-Connect sources + ownership/authorization model** — blocks **integrations or slices that depend on those specific sources or access rules**; a slice that does not use them is not blocked.

---

## 7. Decision and escalation model

This defines decision **behavior**, not committees or approval hierarchies (none are invented here).

When a cross-domain decision is needed:

1. **Classify it** — is it product behavior, domain ownership, a shared semantic/contract, experience composition, or an architecture constraint? The class tells you who is accountable and how durable the decision must be.
2. **Record durable decisions** in the Decision Log / an ADR where appropriate.
3. **Prefer a clear temporary working decision** over parallel incompatible implementations — a documented provisional choice is better than two teams silently diverging.
4. **Keep reversible decisions lightweight.**
5. **Give foundational, irreversible/high-cost decisions stronger evidence** before committing.
6. An **unresolved decision must not silently become an implementation assumption** — surface it, don't bake it in.

> **Documentation is the memory of a decision; it is not the decision-making authority itself.** A document records that a decision was made and why; it does not, by existing, make or replace the decision.

---

## 8. Capability reuse model

A defining Sigma behavior:

```text
Use Case
   ↓
Vertical Slice
   ↓
Repeated Need Identified
   ↓
Reusable Capability
   ↓
Consumed by future slices
```

This sequencing prevents two opposite failures:

- **Feature duplication** — each experience/team rebuilds the same underlying logic, so shared semantics fork and cost is paid repeatedly.
- **Platform-first over-generalization** — a team builds a generalized platform **before** proving that more than one meaningful consumer exists.

Reuse is earned by **repeated, demonstrated need**, not asserted up front. Conceptually, Geography is intended to evolve into a **reusable Spatial Intelligence** capability that many products consume rather than each building spatial logic of their own — reuse emerging from a need that recurs across slices.

---

## 9. Relationship between roadmap and execution

The approved hierarchy is preserved:

```text
Business Roadmap → Vertical Slice → Domain Capabilities → Reusable Capability
```

Portfolio/domain roadmaps provide **direction**; **execution still converges around integrated user/business outcomes** (the slice), not around each domain finishing its own list. Priority semantics (from the execution handoff):

- **P0** — current annual priority (build this year).
- **P1** — after foundation/evidence (and a gate).
- **P2 / NOT YET** — direction, **not** a delivery commitment.

This document does not set quarterly plans; see [`EXECUTION-MODEL.md`](../07-EXECUTION/EXECUTION-MODEL.md) and its source artifact for slice targets and gate timing.

---

## 10. Delivery gates

A gate exists to answer **"do we have enough evidence to continue?"** — **not** "did each team complete its assigned tasks?". Evidence a gate may weigh includes: a functioning end-to-end; real data/integration; stable contracts; the intended user outcome; provenance/trust; and domain boundaries working as intended.

This section explains the **role** of gates only; the detailed gate/DoD mechanics and the specific gates live in [`EXECUTION-MODEL.md`](../07-EXECUTION/EXECUTION-MODEL.md). No new gates are introduced here.

---

## 11. Greenfield operating implication

The current delivery baseline remains **GREENFIELD / SETUP REQUIRED** ([D-20](../05-DECISIONS/DECISION-LOG.md); [`CURRENT-STATE.md`](../CURRENT-STATE.md)). The early operating model therefore prioritizes:

- closing **core ownership boundaries**,
- **proving contracts**,
- building **first vertical slices**,
- and **validating reusable capabilities through actual use.**

Do **not** optimize prematurely for scaling a mature platform organization that does not yet exist, and do **not** claim current team maturity or implementation status. The model describes how to operate a system being set up from zero, not one already running.

---

## 12. What is intentionally decentralized

Sigma should **not** centrally dictate every implementation decision. Coherence, not control, is the goal.

**Kept decentralized within bounded ownership:** internal domain implementation; local technical choices that do not break shared contracts; professional-system internals; UX implementation details within approved product behavior; reversible team-level decisions.

**Central alignment is needed only when a decision affects:** cross-domain semantics; ownership; shared contracts; the experience/domain boundary; the evidence/trust model; or the Vertical Slice end-to-end.

> The goal is **coherence without unnecessary centralization** — align on the seams, decentralize behind them.

---

## 13. Anti-patterns

Operating failures to watch for:

- **Team roadmap replaces business outcome** — execution organizes around backlogs instead of a proven user outcome.
- **UI becomes accidental source of truth** — the place something is shown/edited quietly starts owning the truth.
- **C&M becomes mandatory middleware** — synthesis is inserted into every request, including simple factual access that needs none.
- **Each team invents its own shared entity semantics** — "operation", "status", "signal" come to mean different things, and integration breaks.
- **"Platform" is built before repeat need exists** — generalized capability with no proven second consumer.
- **Every integration becomes a central database copy** — objects centralized merely because it is possible, recreating sync/ownership problems.
- **Feature considered done before E2E works** — components complete in isolation but no integrated outcome exists.
- **Future capability silently becomes a current dependency** — a NOT-YET item becomes a hidden prerequisite.
- **Documentation existence treated as delivery evidence** — a PRD/ADR/schema mistaken for a working capability.
- **Cross-domain decision left ambiguous** — an unresolved decision is then resolved independently (and incompatibly) by multiple teams.

---

## 14. Operating Model test

For any new Vertical Slice, ask:

1. What **user/business outcome** are we proving?
2. Which **truths** are required?
3. **Who owns** each truth?
4. Which **capability computes** what?
5. Is **synthesis actually required**, or can trusted facts be consumed directly?
6. What belongs in **Zira** vs a **domain capability**?
7. Which **dependencies are foundational** (vs integrative vs future)?
8. Which **contract must be stable** before parallel work?
9. What **evidence proves the integrated outcome**?
10. What becomes **reusable** after this slice?
11. Are we building this because a **repeated need exists**, or because it **looks like a platform**?
12. Which **future/candidate scope must NOT block** this slice?

This is **not** a delivery checklist; it is a test of whether the work **follows the Sigma Operating Model.** Where it also touches doctrine, apply the Doctrine decision test (DOC-001 §10).

---

## References

- [`DOC-001 Sigma Doctrine`](../DOC/DOC-001%20Sigma%20Doctrine.md) — the governing foundation this model operationalizes.
- [`CURRENT-STATE.md`](../CURRENT-STATE.md) — current product/system model and GREENFIELD baseline.
- [`07-EXECUTION/EXECUTION-MODEL.md`](../07-EXECUTION/EXECUTION-MODEL.md) — slices, priorities, gate/DoD mechanics.
- [`05-DECISIONS/DECISION-LOG.md`](../05-DECISIONS/DECISION-LOG.md) — the owner decisions referenced above.
- [`GLOSSARY.md`](../GLOSSARY.md) — Sigma/Zira, Operational Signal/Meaning, Geography capabilities.
- Domain and product material: Operations Store package; Geography / Spatial Intelligence; Context & Meaning; Commander Space and Operations Management (Zira).
