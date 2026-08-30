---
id: DOC-001
title: Sigma Doctrine
version: 2.0
status: Draft
classification: Foundational
owner: Sigma
last_updated: 2026-08-30
---

# Sigma Doctrine

The Sigma Doctrine is the most durable document in the Sigma Knowledge Base. It states **why Sigma exists, what Sigma is and is not, and the principles that should govern product and architecture decisions** — the beliefs that should remain true even as individual products, technologies and organizational structures change.

This is a **doctrine**, not a roadmap, PRD, architecture specification, or portfolio catalog. It should be stable enough that a future initiative can be **tested against it** (see §10). It does not describe implementation status; for the current build reality see [`CURRENT-STATE.md`](../CURRENT-STATE.md), and for the vocabulary it uses see [`GLOSSARY.md`](../GLOSSARY.md).

---

## 1. Mission

**Sigma's mission:**

> **התכנסות בזמן לתמונת החלטה אמינה, עדכנית ומותאמת תפקיד.**
> *(Timely convergence on a decision picture that is reliable, current, and role-relevant.)*

Sigma exists to **reduce the distance** between:

```text
distributed operational reality → trusted understanding → decision → action
```

The problem is **not merely a lack of data**. Operational knowledge is **distributed** across professional systems, domains, representations and owners. Today, arriving at a decision-ready picture forces people to do the integration work by hand:

- navigating many systems,
- manually joining information across them,
- rebuilding context in slides,
- interpreting conflicting representations,
- and repeatedly reconstructing *what changed* and *why it matters*.

Sigma should let the organization **converge on a trusted, current, role-relevant picture** — in time for the decision — **while preserving source ownership and evidence.** Convergence is the goal; centralization is not. The picture must remain traceable back to the facts and the systems that own them.

---

## 2. Sigma system model

```text
Professional Sources
        ↓
Domain & Shared Capabilities
        ↓
Context / Synthesis  (when required)
        ↓
Zira — Product / Experience Layer
        ↓
Human Decision & Action
```

This is a model of responsibility, **not a mandatory linear middleware chain.** In particular, **Context & Meaning is optional.**

- **Direct factual consumption is valid** when no cross-domain interpretation is required:
  `Operations Store → Zira`
- **Cross-domain synthesis is used when required:**
  `Operations + Geography → Context & Meaning → Zira`

The experience layer **must not independently recreate cross-domain synthesis** that belongs to Context & Meaning, and it must not reproduce domain truth for its own convenience. Where meaning is synthesized, it belongs in C&M and must stay traceable to evidence.

---

## 3. Sigma vs Zira

`Sigma` and `Zira` are **not synonyms.**

- **Sigma** — the wider **system / capability ecosystem**: domain capabilities, shared capabilities, contracts, semantics, evidence, synthesis, and experience.
- **Zira** — Sigma's **product / experience layer** for users; it contains the user-facing modules and experiences. Current examples: **Commander Space** and **Operations Management**.

Operations Store, Geography / Spatial Intelligence, and Context & Meaning are **Sigma capabilities, not Zira modules.** Commander Space and Operations Management are **modules inside Zira**, and Commander Space does not contain Operations Management. *(See [DECISION-LOG D-17](../05-DECISIONS/DECISION-LOG.md).)*

---

## 4. Core domain responsibilities

Stated at doctrine level — responsibilities and boundaries, not implementation.

### Operations
Owns the **canonical organizational representation of operations** and relevant operational state, and provides trusted **factual operational context**. It does **not** own GIS/spatial computation, cross-domain operational meaning, commander prioritization, or machine-generated readiness scoring.

### Geography / Spatial Intelligence
Owns reusable **spatial intelligence** — it lets Sigma products ask questions with a spatial dimension **without every product becoming a GIS product.** Its current product-level capability model is:

- **Spatialize**
- **Resolve**
- **Relate**
- **Reconstruct**
- **Qualify**

Geography produces **Spatial Evidence**. It does **not** own the broader operational "so what." *(Spatial Evidence is the product/business abstraction; the technical contract returns a SpatialResult — different abstraction levels.)*

### Context & Meaning
Owns **cross-domain synthesis when synthesis is required.** It combines trusted evidence/facts from the relevant domains and produces **evidence-backed operational meaning**; a concrete output may be an **Operational Signal**. An Operational Signal is **not** a raw event, observation, or uninterpreted data point. C&M **must not become mandatory middleware** for simple factual access.

### Zira
Owns the **user experience** through which people understand, decide and act, exposing the right context and capability for the user's **role and task**. Zira does **not** become the source of truth for domain data and does not reproduce domain or synthesis logic merely for UI convenience.

---

## 5. Doctrine principles

Durable principles for testing product and architecture decisions. Each states what it means, why Sigma needs it, and the mistake it prevents.

**5.1 Decision-first, not dashboard-first.**
Sigma optimizes for helping a user understand *what requires attention, what changed, what it means, and what action is possible.* A dashboard-first product optimizes for showing data — many widgets, filters and panels — and leaves the user to work out relevance themselves. Sigma needs this because the scarce resource in operations is attention, not information; adding more panels does not reduce the distance to a decision. The mistake it prevents is building density and coverage as a proxy for value, producing a system that displays everything and decides nothing.

**5.2 Domain truth before synthesized meaning.**
Facts and their ownership stay grounded in the domain/source that owns them; meaning may be synthesized *above* those facts but never *instead of* them. Sigma needs this so that a synthesized conclusion always has an owner and an origin, and can be corrected at the source rather than in the interpretation. The mistake it prevents is a plausible cross-domain narrative that no domain actually stands behind — meaning that floats free of the truth it claims to summarize.

**5.3 Evidence before assertion.**
Any important operational conclusion must carry its **provenance, freshness, and supporting evidence**, and that evidence must stay **inspectable** — a user can always ask "on what basis?" and get an answer. Sigma needs this because operational trust is earned by being checkable, not by sounding confident. The mistake it prevents is a system that emits authoritative-looking conclusions while hiding (or having lost) what they were based on.

**5.4 Planned ≠ Actual.**
Planned state and observed/actual state are kept **distinguishable**; actual/observed values do not silently overwrite the plan. Sigma needs this because the gap between plan and reality is itself decision-relevant information, and because plans and observations have different owners and lifecycles. The mistake it prevents is collapsing both into one mutable field, which destroys the ability to see divergence, reason about it, or reconstruct what was planned.

**5.5 Ownership ≠ presentation.**
Displaying a piece of information inside Zira does **not** transfer ownership of that information to Zira; the experience layer can *host* context without *becoming* its source of truth. Sigma needs this so that professional systems and domains remain the authorities on their own objects even as those objects appear in a shared experience. The mistake it prevents is ownership drifting into the UI — the place something is shown quietly becoming the place it is defined, forking truth away from its real owner.

**5.6 Reusable capability over one-off feature.**
When several use cases reveal the same underlying need, Sigma prefers a **reusable domain/shared capability** to repeated bespoke implementations. Crucially, reuse should **emerge from repeated, demonstrated needs** — not from abstract platform-building for its own sake. Sigma needs this to avoid both extremes: a pile of one-off features that duplicate logic, and a speculative platform built ahead of any real consumer. The mistake it prevents is paying platform cost with no proven second consumer, or paying integration cost forever because nothing was ever generalized.

**5.7 Human-in-the-loop.**
Sigma **supports** human operational judgment; it may assist, surface options, and recommend. What it must not do is silently convert uncertainty, evidence, or a recommendation into **automatic blocking or autonomous command authority.** Sigma needs this because operational accountability rests with people, and assistance only helps if the human retains the decision. The mistake it prevents is a system that quietly starts *deciding* — turning a suggestion into an unreviewable action — not the mere existence of recommendations, which are welcome.

**5.8 Context is role-dependent.**
The *relevant* operational picture depends on role, task, time horizon, and decision context; there is no single universally correct view to render for everyone. This does **not** mean each role gets its own separate truth — the underlying facts are shared and single-sourced; only their **selection, framing, and emphasis** are role-specific. Sigma needs this so a long-term planner and a shift controller can each get a useful view of the same reality. The mistake it prevents is either a one-size-fits-all screen that serves no role well, or fragmenting the facts themselves into per-role versions that then disagree.

**5.9 Federation where ownership matters.**
Where a professional system is the rightful owner of an object, it **keeps** that ownership; Sigma **integrates, references, materializes, or projects** the information according to the product behavior actually required. Federation is an **ownership principle, not a blanket prohibition on materialization** — copying/materializing is legitimate when latency, resilience, or a real business lifecycle requires it, provided ownership and provenance are preserved. The mistake it prevents is centralizing every object merely because it is technically possible, creating synchronization and ownership problems before any reuse is proven.

**5.10 Discovery before commitment.**
Product direction can be stated explicitly without pretending future scope is already committed. Sigma keeps four states distinct — **current capability · validated direction · candidate scope · future / NOT YET.** Sigma needs this so leadership can align on direction without that direction hardening into a delivery promise. The mistake it prevents is a hypothesis or an architectural aspiration quietly becoming a roadmap commitment that teams are then held to.

---

## 6. Product behavior

The desired progression of value is:

```text
Facts → Context → Meaning → Attention → Decision → Action → Memory
```

Each transition adds something:

- **Facts** — trusted, owned domain data (what is true).
- **→ Context** — those facts placed in their relevant setting (related entities, time, space, plan).
- **→ Meaning** — cross-domain synthesis of what the context implies (impact, change, an Operational Signal).
- **→ Attention** — surfacing the meaning that a specific role/task should notice now.
- **→ Decision** — a human choice made with that understanding.
- **→ Action** — the decision carried into execution.
- **→ Memory** — preserving what was known, decided and done so it can be understood later (§7).

**This is a conceptual progression, not a mandatory processing pipeline.** An interaction does **not** have to traverse every stage, and a user may **enter directly at the level appropriate to the task**:

- a **factual question** → a direct trusted domain answer (no synthesis required),
- a **spatial question** → Geography,
- a **cross-domain impact question** → Context & Meaning synthesis,
- a **commander attention/decision task** → the Zira experience.

At every level the system must preserve the ability to **drill back from higher-level meaning to the underlying evidence.** Meaning that cannot be traced back to its facts is not trustworthy meaning.

---

## 7. Knowledge continuity

Sigma should not only help make the **current** decision; it should preserve enough context to understand, later:

- what was known,
- what changed,
- what evidence supported the picture,
- what decision was made,
- and, where relevant, what action followed.

This is a **system principle**, not an implementation design: understanding should remain **reconstructable over time**, so a decision can be explained after the fact and organizational learning is possible.

---

## 8. What Sigma is NOT

Sigma is **not**:

- **One giant operational database.** Sigma converges understanding; it does not seek to copy every object into one central store. Truth stays distributed and owned, connected through contracts and references (§5.9). Treating Sigma as the database-of-everything recreates the synchronization, ownership and freshness problems it exists to avoid.
- **A replacement for every professional system.** Professional/source systems remain the authorities on their objects. Sigma integrates, references and projects their information; it does not absorb their responsibilities. Positioning Sigma as a wholesale replacement breaks source ownership and provenance.
- **A dashboard factory.** Sigma is decision-first, not widget-first (§5.1). Its purpose is not to manufacture panels and charts on demand but to help a user understand what needs attention and why. Measuring Sigma by how many dashboards it can produce optimizes the wrong thing.
- **A GIS application.** Geography provides reusable spatial intelligence and Spatial Evidence so that other products can ask spatially-aware questions — it does not turn Sigma into a map-editing/GIS product, and spatial computation stays inside Geography rather than leaking into every experience.
- **An LLM wrapper.** Language models may help parse intent or assist interaction, but they do **not** produce operational facts or spatial results on their own; facts come from deterministic domain computation with evidence. A thin conversational layer over ungrounded generation is the opposite of evidence-before-assertion (§5.3).
- **An autonomous commander.** Sigma supports human judgment; it does not hold operational decision authority. It may surface options and recommendations, but decisions and their accountability remain with people (§5.7). A system that silently acts or blocks on its own crosses this line.
- **A system that hides provenance behind generated conclusions** — every important conclusion must remain inspectable back to its evidence.
- **A reason to centralize every object merely because it can** — technical possibility is not a justification for taking ownership.
- **A commitment to Digital Twin / broad simulation / autonomous recommendations.**

Those future areas remain **NOT YET** unless separately validated and approved. *(See the execution NOT-YET guardrails in [`EXECUTION-MODEL.md`](../07-EXECUTION/EXECUTION-MODEL.md).)*

---

## 9. Greenfield reality

The doctrine defines the intended **governing model**; it does not describe delivery progress. The current delivery baseline for the major Sigma capability areas is:

> **GREENFIELD / SETUP REQUIRED**

Existing PRDs, HLDs, ADRs, contracts, schemas, Golden-E2E definitions, prototypes and strategy documents represent **product/architecture knowledge — not proof that a capability is operational, deployed, pilot-ready, or live.** The doctrine governs how Sigma should be built regardless of that greenfield state; it does not imply any of it is built. *(See [DECISION-LOG D-20](../05-DECISIONS/DECISION-LOG.md) and [`CURRENT-STATE.md`](../CURRENT-STATE.md).)*

---

## 10. Doctrine test

Use this to challenge a proposed Sigma initiative. It is a **decision test**, not a Definition of Done — the questions probe whether the initiative *belongs in Sigma and follows its doctrine*, not whether it is ready to ship.

**Problem & ownership**
1. What user **decision or problem** does this improve? *(§5.1)*
2. Which **domain owns** the underlying truth? *(§5.2)*
3. Are we **preserving source ownership**, or moving it into Sigma without cause? *(§5.9)*

**Meaning & evidence**
4. Does this genuinely require **synthesis**, or can trusted facts be consumed **directly**? *(§2, §5.2)*
5. If synthesis exists, can the user **inspect the evidence** behind it? *(§5.3)*
6. Are **planned and actual** state kept distinguishable? *(§5.4)*

**Design discipline**
7. Are we creating a **reusable capability** driven by repeated need, or another one-off? *(§5.6)*
8. Is the value **role/task-specific** without fragmenting the underlying truth? *(§5.8)*
9. Are we accidentally **moving professional ownership into the experience layer**? *(§5.5)*

**Honesty about maturity**
10. Are we claiming **delivery maturity** that has not been demonstrated? *(§9)*
11. Is this **current scope, candidate scope, or NOT YET**? *(§5.10)*

An initiative that cannot answer these well is not yet ready for Sigma — regardless of how attractive the feature looks.

---

## References

- [`CURRENT-STATE.md`](../CURRENT-STATE.md) — current product/system model and delivery baseline.
- [`GLOSSARY.md`](../GLOSSARY.md) — Sigma/Zira, Operational Signal/Meaning, Geography capabilities.
- [`05-DECISIONS/DECISION-LOG.md`](../05-DECISIONS/DECISION-LOG.md) — the owner decisions this doctrine reflects.
- [`07-EXECUTION/EXECUTION-MODEL.md`](../07-EXECUTION/EXECUTION-MODEL.md) — how initiatives are sequenced and gated.
- Domain material: Operations Store package, Geography / Spatial Intelligence, Context & Meaning, and the Commander Space / Operations Management (Zira) product docs.
- OM-001 Sigma Operating Model *(currently an authoring shell — will detail the operating model this doctrine implies).*
