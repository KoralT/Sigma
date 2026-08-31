# Sigma Company Brain — Guide

The canonical user manual for working with the Sigma Company Brain: shared orientation (Part I) plus role-specific usage guidance (Part II).

*(A Hebrew RTL companion for easy distribution exists at [`COMPANY-BRAIN-GUIDE-HE.html`](COMPANY-BRAIN-GUIDE-HE.html). This Markdown file remains the canonical, maintainable source; the HTML is a human-friendly companion, not a second source of Product Truth.)*

---

# Part I — Working Guide

## Purpose

The Sigma Company Brain is the shared product-knowledge system for Sigma.

Its purpose is not only to preserve documentation. It should allow anyone working on Sigma to understand:

- what Sigma is trying to achieve,
- what is true today,
- what each product/domain responsibility owns,
- how the different parts of Sigma relate,
- what has already been decided,
- what remains open,
- what is hypothesis vs. established direction,
- and what the responsible next action is.

The Company Brain should be used **before** relying on historical documents, old prototypes, personal memory, or verbal handoff.

---

## 1. Where should I work?

**Official baseline.** The official Company Brain lives on `main`. The first formally approved baseline is `company-brain-v1.0`.

Do not use old working branches as the source of current Product Truth. `kb-refactor/batch-1` is retained as historical implementation history of the Company Brain refactor. It is **not** the working source going forward.

**Default rule.**
- Read from `main`.
- For historical comparison: use Git history or the `company-brain-v1.0` tag.
- For new work: create a new branch from the latest `main`.
- Do not modify the `company-brain-v1.0` baseline.

---

## 2. Where should I start?

Do not begin by searching random documents. Use the Brain in this order.

**Step 1 — Current Truth.** Start with [`CURRENT-STATE.md`](CURRENT-STATE.md). Use it to understand what Sigma looks like today, current product/domain responsibilities, current delivery maturity, what is established, and what remains open.

**Step 2 — Product principles.** Read [`DOC/DOC-001 Sigma Doctrine.md`](DOC/DOC-001%20Sigma%20Doctrine.md). Use it to understand why Sigma exists, durable product principles, what Sigma should and should not become, and how facts, context, meaning, attention, decisions, actions and memory relate.

**Step 3 — How Sigma works.** Read [`OM/OM-001 Sigma Operating Model.md`](OM/OM-001%20Sigma%20Operating%20Model.md). Use it to understand how business needs become capabilities, how Vertical Slices are used, how dependencies/contracts are handled, how gates and DoD work, and when an unresolved question should block work — and when it should not.

**Step 4 — Product landscape.** Read [`PR/PR-001 Sigma Product Portfolio.md`](PR/PR-001%20Sigma%20Product%20Portfolio.md). Use it to understand what Sigma is responsible for, the current product/domain landscape, the distinction between Sigma and Zira, and the relationship between domain capabilities and user-facing experiences.

**Step 5 — Decisions.** Use [`05-DECISIONS/DECISION-LOG.md`](05-DECISIONS/DECISION-LOG.md) **before** reopening an architectural or product question. Ask: *Has this already been decided? Was a previous direction intentionally reversed? Is this actually open, or am I about to reopen a settled decision?*

**Step 6 — Go into the relevant domain.** Only after understanding the system-level context, go into the relevant area: Operations, Geography / Spatial Intelligence, Context & Meaning, Commander Space, Planning / Operations Management, Control / Event Management, Shared Capabilities, Execution.

---

## 3. How should I ask questions of the Company Brain?

The Company Brain is most useful when questions are asked as **business/product questions**, not only document-search questions.

Avoid: *"What documents exist about Operations?"*

Prefer: *"What business problem does Operations Store solve, what does it own, what does it explicitly not own, and what should happen next?"*

---

## 4. The best questions to ask

**Understand a product/domain.** Why does this capability exist? What business question does it answer? Who needs it and in what context? What does it own? What does it explicitly not own? What are its upstream and downstream dependencies? Which other Sigma capabilities does it interact with? What is established Product Truth? What is still a hypothesis? What is intentionally undecided? What is historical? What is the current delivery state? What evidence supports the current direction? What is the next responsible product action?

**Before designing a solution.** What user/business problem are we solving? Which business territory owns the workflow? Which domain owns the underlying information? Does an existing Sigma capability already provide part of this? Are we duplicating a professional system? Are we accidentally putting domain logic inside Zira? Does this require cross-domain meaning, or can the experience consume trusted domain facts directly? What prior product thinking should we preserve without automatically treating its implementation as current truth? What decision has already been made that constrains this solution? What is the smallest Vertical Slice that can validate the important assumption?

**Before changing architecture.** Which domain should own this truth? Is this factual domain state, spatial evidence, cross-domain meaning, or experience behavior? Is there already an explicit boundary decision? Which contract should exist between the responsible components? Does this architectural decision support a real Vertical Slice, or are we designing infrastructure without a demonstrated need?

**Before building a prototype.** What Product Truth must the prototype express? Which capabilities are current direction versus candidates? Which questions are we trying to validate? What must NOT be implied as decided by the prototype? Which historical prototype behaviors are useful design evidence but not current truth? What would we need to learn from users before promoting this design into Product Truth?

**Before starting development.** What business outcome does this slice need to prove? What is the current DoD? Which contracts/dependencies must be closed for this slice? Which open decisions actually block this slice? What can remain unresolved? What evidence will allow us to pass the Gate? Are we demonstrating this end-to-end on real information?

---

## 5. Important Sigma questions

These questions are useful for orienting any new contributor.

- **Sigma** — What problem does Sigma solve that individual professional systems cannot solve alone?
- **Zira** — Which part of this problem belongs in the product/experience layer?
- **Operations Store** — What is the trusted operational truth we need to represent?
- **Geography** — What spatial question needs to be answered without requiring the consuming product to become a GIS product?
- **Context & Meaning** — Is cross-domain synthesis actually required here?
- **Planning** — What are we planning, and how do we prepare/manage it?
- **Control** — What is happening now, what changed, and how do we manage/respond?
- **Commander Space** — What from the operational world requires this user's attention, understanding, decision, approval or action?

These questions describe **different responsibilities**. Do not collapse them into one product simply because they interact.

---

## 6. How do I know what to trust?

Not every document has the same authority. Use the following order.

1. **Current Owner-approved Product Truth** — explicitly approved current product decisions have the highest authority. They should be represented in the current Company Brain.
2. **Current Company Brain** — current documents on `main` represent the canonical working knowledge of Sigma.
3. **Working / discovery material** — useful evidence and active thinking. It may influence a decision but should not automatically be treated as Product Truth.
4. **Previous prototypes** — Product Design Evidence. Use them to avoid losing meaningful prior thinking. Do not assume *"it exists in the prototype, therefore it is the product."* The Company Brain should drive the next prototype — not the previous prototype drive the Company Brain.
5. **Historical / superseded documents** — use these to understand why decisions were made, what was tried, what was reversed, what evidence existed. Do not use them as current truth unless a current document explicitly restores that direction.

---

## 7. Knowledge Status vs Delivery Status

These are different. A document can describe a mature product decision while the capability itself has not yet been built.

**Knowledge status** examples: CANONICAL, VALIDATED, WORKING, HYPOTHESIS, SUPERSEDED, HISTORICAL.

**Delivery status** examples: NOT_STARTED, DISCOVERY, BUILDING, PILOT, LIVE.

**Never infer delivery state from documentation maturity.** A detailed PRD, HLD, ADR, schema or prototype does not prove that the capability exists operationally.

---

## 8. How should I use AI with the Company Brain?

When using an AI assistant against the repository, give it the Company Brain as the **primary source of truth**. Do not ask only *"Summarize this repository."* Give it a role and a decision question.

**Product question:** *Using the Sigma Company Brain as the primary source of truth, explain [AREA]. Separate current Product Truth, historical knowledge, hypotheses and open decisions. Then identify the next responsible product action. Do not fill gaps with assumptions.*

**Challenge question:** *Challenge this proposal against the Sigma Company Brain. Identify contradictions with existing decisions, ownership boundaries, product principles and current hypotheses. Distinguish real conflicts from intentionally open questions.*

**Design question:** *Evaluate this proposed experience against the Sigma Company Brain. Identify which business question it answers, which workflow owns it, which domain owns the information, which Sigma capabilities it should consume, and whether the proposal duplicates another responsibility.*

**Continuation question:** *Assume I am the new Product Lead and have no verbal handoff. Based only on the Company Brain, tell me what is settled, what is open, what evidence exists, and what I should do next for [AREA].*

*(See Part II for a longer, role-specific version of this prompt.)*

---

## 9. What should I NOT do?

Do not:

- treat every document as equally authoritative,
- start from an old prototype and infer current Product Truth,
- treat historical IA as current architecture,
- infer implementation from documentation,
- create a new capability before checking whether another Sigma responsibility already owns it,
- move domain logic into Zira because it is convenient for the UI,
- use C&M as mandatory middleware when no synthesis is required,
- turn Commander Space into a generic dashboard,
- confuse Notification with Attention,
- confuse Planning with Control,
- equate Planning with GANTTIT / Operations Management,
- equate Commander Space with Zira,
- treat Operations Store as the user workflow,
- reopen settled decisions without new evidence,
- resolve intentionally-open questions before a real product need requires the decision,
- add documentation merely to make the repository look complete.

---

## 10. How should new knowledge enter the Brain?

The Company Brain is not frozen after v1.0. **The v1.0 baseline is frozen.** Future knowledge should evolve through new commits.

Use this flow:

```text
Discovery / Prototype / Delivery Evidence
        ↓
    Learning
        ↓
Product Decision
        ↓
Company Brain Update
        ↓
Next Product / Prototype / Delivery Iteration
```

Do not rewrite history to make previous decisions look as if they never existed. If direction changes:

1. preserve the previous decision/history,
2. record the new evidence,
3. record the new decision,
4. mark the old direction appropriately,
5. update current-state material.

---

## 11. When should I update the Company Brain?

Update it when something changes that would materially affect how another person continues the product. Examples: a hypothesis is validated or rejected; a Product Truth changes; a new domain/product responsibility is introduced; an ownership boundary changes; a meaningful architectural decision is made; a first Vertical Slice is locked; a Gate is passed or failed; a prototype validation materially changes product direction; delivery status materially changes; a previous decision is superseded.

Do **not** update it for every meeting, design tweak, implementation detail or brainstorm.

---

## 12. Before adding a new document

Ask:

- Does this information already have a natural owner/document?
- Is this Product Truth, evidence, execution material, or historical context?
- Will a future Product Lead need this to make or continue a decision?
- Am I creating a document because knowledge genuinely needs a home — or because creating a document feels productive?

Prefer strengthening an existing canonical document over creating another document when the knowledge belongs there.

---

## 13. Definition of Done for a meaningful Company Brain update

Before merging a meaningful knowledge change into `main`, verify:

- **Truth** — Is it clear what is fact, direction, hypothesis, open question and history?
- **Ownership** — Is it clear which product/domain responsibility owns the capability or information?
- **Relationships** — Are dependencies and boundaries with other Sigma areas understandable?
- **Decision continuity** — If a previous direction changed, can a future reader understand what changed and why?
- **Delivery** — Did we avoid implying implementation maturity that has not been proven?
- **Continuability** — Can the next person identify the responsible next action?

The Company Brain is successful when it makes the next responsible decision easier — not when it contains the most documents.

---

## 14. Quick Start for a New Contributor

If you have only 30 minutes:

1. Read [`CURRENT-STATE.md`](CURRENT-STATE.md).
2. Read [`DOC/DOC-001 Sigma Doctrine.md`](DOC/DOC-001%20Sigma%20Doctrine.md).
3. Read [`PR/PR-001 Sigma Product Portfolio.md`](PR/PR-001%20Sigma%20Product%20Portfolio.md).
4. Check [`05-DECISIONS/DECISION-LOG.md`](05-DECISIONS/DECISION-LOG.md).
5. Read the README/product material for your domain.
6. Ask: *What problem am I responsible for? What is already decided? What is still open? Who owns the underlying truth? Which other Sigma capabilities do I depend on? What is the next responsible action?*

If you can answer those questions without verbal handoff, the Company Brain is doing its job.

*(Continue to Part II for guidance specific to your role.)*

---

# Part II — Role-Based Guide

Different roles should interrogate the Company Brain differently.

Do not try to read the entire repository. Start from the shared system context above (Part I), then follow the questions relevant to the decision you are responsible for.

| Role | Start Here | Primary Questions | Go Deeper Into |
|--|--|--|--|
| **Product Manager / Product Lead** | `CURRENT-STATE.md` → Product Portfolio → Decision Log | What problem are we solving? What is settled vs open? Who owns the workflow? Who owns the information? What evidence exists? What is the next responsible product action? | Relevant Product/Domain docs, Execution Model, discovery evidence |
| **UX / Product Designer** | Current State → relevant Product/Experience doc → Decision Log | What business question must the experience answer? What does the user need to understand/decide/do? What is Product Truth vs previous design? Which interactions are open for exploration? | Commander Space, Planning/Control territory, historical prototypes as design evidence |
| **Architect** | Doctrine → Operating Model → Current State → relevant Architecture/ADR | Which domain owns this truth? What are the boundaries? What contracts are required? Is synthesis needed? Are we duplicating another capability? | ADRs, HLDs, contracts, shared capabilities |
| **Tech Lead / Developer** | Current State → relevant domain README → Vertical Slice / DoD | What outcome are we implementing? Which contracts are authoritative? What is owned locally vs externally? Which open decisions actually block this slice? | API/schema/contracts, HLD, Golden E2E, relevant ADRs |
| **Data Engineer / Data Product** | Current State → relevant domain → Trust / Evidence / Entity material | Who owns the source data? What is factual vs derived? What provenance/freshness is required? Where should transformation or synthesis occur? | Operations Store, Geography, C&M, Trusted Context, Entity Model |
| **QA / Validation** | Current State → Execution Model → relevant Product/Domain doc | What business outcome must be proven? What is the DoD? What evidence is required at the Gate? Which failure/boundary cases matter? | Golden E2E, contracts, acceptance criteria, ADRs |
| **Operational / Domain Expert** | Current State → Product Portfolio → relevant experience/product territory | Does this reflect the real operational workflow? What information is actually needed? Who creates/updates/approves it? Where does the current process break? | Planning, Control/Event Management, Commander Space, relevant discovery material |
| **New Product Lead / Incoming Owner** | `CURRENT-STATE.md` → Doctrine → Portfolio → Decision Log → relevant domain | What is Sigma? What is true today? What must I not reopen? What is hypothesis? What is the next responsible action? | Operating Model, Execution Model, relevant domain/product material |

---

## Product Manager / Product Lead

Your job is not to find the most detailed document. Your job is to understand the current Product Truth and determine the next responsible product action.

### Ask
- What business problem are we solving?
- What business question does this territory answer?
- What is already established?
- What is hypothesis?
- What remains intentionally undecided?
- What evidence led us here?
- Which decisions should not be reopened without new evidence?
- Who owns the workflow?
- Who owns the underlying information?
- Which other Sigma capabilities are required?
- What is the smallest meaningful Vertical Slice?
- What must we learn before committing?
- What is the next responsible action?

### Watch for
Do not confuse a mature document with a mature product. Do not turn open discovery into premature scope. Do not solve a dependency until a real slice depends on it.

---

## UX / Product Designer

Use the Company Brain to understand **what the experience must accomplish**, not to discover a frozen screen specification. Historical prototypes are design evidence — not automatically current UX.

### Ask
- What business question is the user trying to answer?
- What does the user need to understand?
- What requires attention?
- What requires a decision, approval or action?
- What context/evidence is necessary?
- What should the user be able to do from this experience?
- Which underlying workflow owns the action?
- Which domain owns the information shown?
- Which existing capability can be composed instead of redesigned?
- What previous prototype thinking is still useful?
- Which parts of that prototype were explicitly superseded?
- What assumptions should this prototype validate?

### For Commander Space specifically

Always begin with: **What requires this user?**

Then ask: Why does it require them? What changed? What do they need to understand? Is there actually a decision? Is there actually a recommendation? Is approval required? What evidence supports the information? What should happen after the action?

Remember:
- **Notification ≠ Attention.**
- **Ranking ≠ Recommendation.**
- **Commander Space ≠ fixed dashboard.**

---

## Architect

Use the Brain to protect responsibility boundaries and enable product slices — not to maximize architectural completeness.

### Ask
- Which domain owns this truth?
- Is this factual domain state? Spatial computation/evidence? Cross-domain meaning? Experience behavior?
- Which system is the Source of Truth?
- Which information should be referenced rather than copied?
- Which contract connects the responsibilities?
- Does C&M actually need to participate?
- Can Zira consume trusted domain facts directly?
- Are we putting domain logic into the experience layer?
- Are we designing infrastructure because a real Vertical Slice requires it?

### Watch for
Architecture should support product boundaries. It should not create new product boundaries accidentally.

---

## Tech Lead / Developer

Start from the business outcome before reading the API.

### Ask
- What Vertical Slice am I implementing?
- What user/business outcome must work end-to-end?
- What does my component own? What must it not own?
- Which contract is authoritative?
- What are the real producers/consumers?
- Which identifiers must remain stable?
- What provenance/freshness/audit behavior is required?
- What failure states matter?
- Which open decision actually blocks this implementation?
- What evidence demonstrates completion?

### Watch for
Do not implement an assumption merely because the product question has not yet been answered. Escalate the missing product decision instead.

---

## Data Engineer / Data Product

Use the Company Brain to understand the semantics and ownership of data before designing pipelines.

### Ask
- What real-world concept does this data represent?
- Who owns the source object?
- What is the canonical organizational representation?
- What is factual? What is derived? What is cross-domain interpretation?
- What provenance must travel with the information? How fresh must it be?
- Is this Owned, Materialized External, Federated/Reference or Derived factual state?
- Does this belong in Operations Store, Geography, C&M or somewhere else?
- Are planned and actual state being preserved separately?
- What information should remain in the professional source system?

### Watch for
A convenient data model is not automatically the correct ownership model.

---

## QA / Validation

Validate the business outcome and the system boundaries — not only feature behavior.

### Ask
- What must be true for this slice to count as successful?
- What is the business outcome? What is the explicit DoD?
- What evidence is required for the Gate?
- Are we using real information / real producers where required?
- Are planned and actual distinguishable? Is provenance visible?
- Are failures handled honestly? Are stale/missing/conflicting states represented correctly?
- Does the experience accidentally imply meaning or confidence that the underlying data does not support?
- Did the implementation cross a product/domain boundary it should not own?

### Gate mindset
A Gate asks: **Do we have enough evidence to responsibly continue?** Not: **Did we finish all the tasks?**

---

## Operational / Domain Expert

You are one of the most important sources for distinguishing the intended product from the real operational workflow. Do not review only whether terminology "sounds right." Challenge the actual behavior.

### Ask
- Show me where this happens in the real workflow.
- Who starts it? What triggers it?
- What information arrives first? Where does that information come from?
- Who updates it? Who trusts it?
- What happens when it changes? Who needs to know? Who can decide? Who can approve?
- What happens if nobody acts?
- Where are slides, WhatsApp, calls or manual coordination still required?
- What information do you collect manually today?
- What part of the SOP lives in people's heads or external documents?
- When is the workflow considered finished? What needs to survive after it is finished?

### When reviewing a prototype
Do not answer only: *"Do you like this?"*

Instead ask: *"Could you manage the real situation using this?" "What would you still need outside the product?" "What is missing for you to trust this?" "What would prevent you from acting?"*

---

## New Product Lead / Incoming Owner

Your first objective is not to learn every detail. It is to build a reliable mental model of Sigma.

### First 30 minutes

Read:
1. `CURRENT-STATE.md`
2. `DOC/DOC-001 Sigma Doctrine.md`
3. `PR/PR-001 Sigma Product Portfolio.md`
4. `05-DECISIONS/DECISION-LOG.md`

Then ask: What is Sigma? What is Zira? What are the current business/product territories? What does each domain own? What is GREENFIELD? What is established? What is hypothesis? What has been intentionally reversed? What remains intentionally undecided?

### Then choose your territory

For the area you own, determine:
1. **Business question**
2. **User/problem**
3. **Product responsibility**
4. **Information owner**
5. **Dependencies**
6. **Current evidence**
7. **Open questions**
8. **Next responsible action**

If one of these cannot be answered, do not immediately create a solution. First determine whether the gap is: missing knowledge, missing discovery, an intentionally open decision, or a real product dependency.

---

## Universal Prompt — Use This With the Company Brain

For any role, this is a strong starting prompt for an AI assistant:

> Use the current Sigma Company Brain on `main` as the primary source of truth.
>
> I am working as **[ROLE]** on **[AREA / PROBLEM]**.
>
> First establish the relevant current Product Truth and ownership boundaries.
>
> Separate clearly:
> - established direction,
> - current facts,
> - hypotheses,
> - intentionally open decisions,
> - historical/superseded thinking,
> - delivery status.
>
> Then answer:
> 1. What business question am I actually solving?
> 2. Which Sigma responsibility owns the workflow?
> 3. Which domain owns the underlying information?
> 4. Which existing capabilities should I consume or reuse?
> 5. Which decisions already constrain the solution?
> 6. What evidence supports the current direction?
> 7. What do we genuinely not know yet?
> 8. What is the next responsible action?
>
> Do not fill knowledge gaps with assumptions.
> Do not infer implementation from documentation maturity.
> Do not reopen settled decisions without new evidence.
> Do not promote historical prototype behavior into current Product Truth unless the Company Brain explicitly supports it.

---

## Role Guide Principle

Every role should leave the Company Brain with a different output:

- **Product** → the next product decision or learning objective.
- **UX** → the question the experience must answer and the assumptions to validate.
- **Architecture** → the correct responsibility boundary and required contracts.
- **Engineering** → an implementable slice with clear ownership and DoD.
- **Data** → trusted semantics, provenance and ownership.
- **QA** → evidence that the intended business outcome and boundaries actually hold.
- **Domain Expert** → confirmation or correction of the real operational workflow.
- **Incoming Product Lead** → enough understanding to continue without verbal handoff.

That is how the same Company Brain becomes a working product system rather than a documentation repository.

---

## Baseline

- Official branch: `main`
- Approved Company Brain baseline: `company-brain-v1.0`
- Baseline commit: `16f93e589099dbe368ca2eb1e66f9c7b456e1bb6`

The baseline represents the Company Brain state formally approved for handoff. Future discovery, prototype iteration, validation and delivery learnings should evolve through new commits after this baseline.
