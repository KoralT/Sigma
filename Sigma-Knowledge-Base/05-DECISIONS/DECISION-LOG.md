# Decision Log

> Owner decisions taken during the Sigma Knowledge Base refactor. This log records **governance and terminology decisions**; full Architecture Decision Records (ADRs) are created only when a real architectural/product decision was made, and live with their domain.
>
> Rationale captured here is limited to what is evidenced by the migration review — no historical rationale is invented.

All decisions dated **2026-08-30** (knowledge-base refactor, Phase 1 → Batch 1).

---

### D-01 — Commander Space is the canonical experience/product name
- **Decision:** "Commander Space" is canonical. "Commander Experience" is terminology drift referring to the same commander-facing module, not a separate product or domain. *(Commander Space is a module inside Zira, not the whole experience layer — refined by D-17.)*
- **Rationale:** Two names for one layer were found across the repository (PR-014 uses "Commander Space"; the newer Context & Meaning and Geography packs use "Commander Experience"), with no explicit rename recorded.
- **Implications:** Navigation and newly authored text use "Commander Space." Historical documents are **not** rewritten yet; the alias is recorded in the glossary and registry.
- **Affected:** Commander Space concept; PR-014/015/016/017; Context & Meaning 01/02/03/05/06; Geography 01/02/03.

### D-02 — "My Space" is current; "Personal Workspace" retained for traceability
- **Decision:** The current experience name is **My Space**. PR-016 remains the stable document ID. The former term "Personal Workspace" is retained for traceability. *(Superseded by D-22: "My Space" is no longer a separate product concept — its intent is absorbed into Commander Space. PR-016 is retained as history.)*
- **Rationale:** Product-name drift between PR-016's title ("Personal Workspace") and the current experience name.
- **Implications:** Planned V2 location is `03-EXPERIENCE/Commander-Space/My-Space/`. A front-matter alias will be added later; traceability to "Personal Workspace" is preserved.
- **Affected:** PR-016 and inbound references.

### D-03 — Operations Store / Operations Repository / Operational Repositories are NOT auto-merged
- **Decision:** These three concepts are kept **separate** pending semantic reconciliation. No automatic rename or merge is authorized.
- **Rationale:** Overlapping names may represent different abstraction levels — Operations Store (operational state / canonical operational representation), Operations Repository (broader operations knowledge model, CAT-010), Operational Repositories (product, PR-017).
- **Implications:** Each keeps its own registry entry and (planned) location; reconciliation is a prerequisite before their migration is finalized.
- **Affected:** `Operations-Store/` package; CAT-010; PR-017.

### D-04 — ARC-001 will not be created
- **Decision:** ARC-001 ("Sigma Reference Architecture") is no longer required and will **not** be authored. Its entry-architecture role is served by START-HERE.md, Platform Architecture (PA-001), and DOCUMENT-REGISTRY.md.
- **Rationale:** ARC-001 is referenced as a conceptual entry point but no file exists; a replacement entry mechanism is now in place.
- **Implications:** ARC-001 references in **active** documents (DM-001, PA-010, PA-011) were removed in Batch 2A and repointed to `01-FOUNDATIONS/Platform-Architecture.md`; legacy/historical documents retain references for traceability. No replacement content is fabricated.
- **Affected:** DOCUMENT_REGISTRY (legacy), CAT-001, DM-001, PA-010, PA-011.

### D-05 — Layer A and Layer B coexist with unequal authority
- **Decision:** The older conceptual layer (Doctrine/Operating Model/Platform/Product/Research) and the newer domain/engineering layer (Operations, Geography, Context & Meaning, current contracts) **coexist**. Current approved domain decisions take precedence where the content supports them; Layer-A **placeholder/skeleton** documents hold **no** canonical authority merely because they are classified "Foundational."
- **Rationale:** Four of five foundational documents are authoring shells; the newer layer contains more recent, implementation-oriented product, architecture, contract, schema, and delivery artifacts, while Layer A contains conceptual foundations and historical framing.
- **Implications:** No blanket supersession. Substantive Layer-A concepts remain valid where they do not conflict with newer approved decisions.
- **Affected:** DOC-001, OM-001, PR-001, RS-001 (shells); all Layer B domain packs.

### D-06 — Operational Meaning and Operational Signal are distinct
- **Decision:** "Operational Meaning" (organizational/platform capability) and "Operational Signal" (a Context & Meaning output / business contract) are **not** synonyms. Both are preserved; their relationship is documented, not merged.
- **Rationale:** OM-004 defines the capability; the C&M Operational Signal Schema defines a concrete traceable output. A conflicting older KB-001 definition of "Operational Signal" (raw data point) is flagged in the glossary.
- **Implications:** Kept in separate homes (Shared Capabilities vs Context & Meaning contracts); the KB-001 discrepancy must be reconciled without inventing a definition.
- **Affected:** OM-004; Context & Meaning schema (05); KB-001.

### D-07 — Domain Golden E2E / DoD stays with its domain
- **Decision:** When a Golden E2E / Phase-1 DoD document defines the **acceptance contract for a domain capability**, it stays with the domain (`02-DOMAINS/<Domain>/Delivery/`). The global `07-EXECUTION` area is reserved for cross-Sigma vertical slices, annual plans, portfolio execution, cross-domain delivery, and handoff material.
- **Rationale:** Acceptance contracts are most useful next to the capability they gate.
- **Implications:** Operations Store, Geography, and Context & Meaning Golden-E2E documents map to their domain `Delivery/` folder; the cross-domain annual initiative maps to `07-EXECUTION/Annual-Plans/`.
- **Affected:** Operations Store 07; Geography 05; Context & Meaning 06; Operational-Data-Foundation.

### D-08 — DOCX originals preserved until Markdown conversion is verified
- **Decision:** A `.docx` original is **not** archived immediately after conversion. Process: convert → semantic comparison → verify no information/table/diagram/contract loss → approve Markdown as canonical → **only then** archive the DOCX.
- **Rationale:** Prevent silent information loss during DOCX→Markdown conversion.
- **Implications:** Both formats coexist until verification succeeds; archived originals land in `99-ARCHIVE/Historical/` only after approval.
- **Affected:** The six Operations Store `.docx` files.

### D-09 — Delivery status is not inferred from a document existing
- **Decision:** Delivery status is **not** derived from the existence of a strategy/PRD/architecture/target-state document. `delivery_status` metadata is not mass-populated. CURRENT-STATE.md is the authoritative knowledge↔delivery bridge; delivery metadata is added only once evidenced.
- **Rationale:** The repository contains no code/test/deployment evidence; asserting delivery would be fabrication.
- **Implications:** CURRENT-STATE explicitly marks areas where delivery reality cannot be established; no `LIVE`/`BUILDING` claims are made.
- **Affected:** All documents; CURRENT-STATE.md.

### D-10 — No empty future-folder scaffolding
- **Decision:** The full V2 directory tree is **not** pre-created with `.gitkeep`. Only directories required by files that actually exist are created. New directories are created later as real knowledge migrates into them.
- **Rationale:** Repository structure should reflect existing knowledge, not hypothetical future content.
- **Implications:** Batch 1 created only `05-DECISIONS/`. Domain/experience/shared-capability folders are created during their migration batches.
- **Affected:** Repository structure.

---

## Batch 2A — semantic-placement decisions (2026-08-30)

### D-11 — Operations trio: placement without merge
- **Decision:** **Operations Store** is the operational domain capability / **system of record** for Sigma's canonical Operation representation and relevant operational state (owner-designated role); its home is `02-DOMAINS/Operations/`. **CAT-010 "Operations Repository"** is treated as an earlier/broader repository model — moved to `02-DOMAINS/Operations/Knowledge/Operations-Repository.md`, knowledge status **WORKING**, **not** canonical, must not override Operations Store contracts. **PR-017 "Operational Repositories"** is an older product concept — moved to `99-ARCHIVE/Historical/Product-Concepts/`, knowledge status **HISTORICAL**.
- **Rationale:** Overlapping names denote different abstraction levels; extends D-03 (no auto-merge).
- **Implications:** Migration notes added to CAT-010 and PR-017 (bodies unchanged). The CAT-010 duplicated "Part IV" block (113 identical lines) was removed and Parts VI–X renumbered V–IX — a deterministic defect fix, no semantic change. Operations Store ↔ CAT-010 reconciliation is still pending. This is a classification decision, not a claim that every concept inside PR-017 is superseded.
- **Affected:** Operations Store `.docx` package; CAT-010; PR-017.

### D-12 — Architecture skeletons archived (capabilities not rejected)
- **Decision:** PA-007 Context Engine, PA-008 Knowledge Graph, PA-009 Repository Architecture are moved to `99-ARCHIVE/Historical/Architecture-Skeletons/`, knowledge status **HISTORICAL**. Not rebuilt in this batch.
- **Rationale:** They are structure-only stubs with no substantive architecture to preserve as current guidance; current C&M / Trusted Context / Operations Store material carries the concrete definitions.
- **Implications:** Archiving the **documents** does not reject the **capabilities**; migration notes state this explicitly.
- **Affected:** PA-007, PA-008, PA-009.

### D-13 — Entity Model is a shared semantic capability
- **Decision:** PA-010 Entity Model → `04-SHARED-CAPABILITIES/Knowledge/Entity-Model.md`. Its role is cross-cutting conceptual entity semantics; it is **not** canonical for Operations entities (Operations Store owns its own canonical operational schema).
- **Rationale:** Entity semantics are consumed across domains.
- **Implications:** Any conflict between PA-010 and a domain schema is exposed, not silently reconciled.
- **Affected:** PA-010; Operations Store schema.

### D-14 — Actionable Experience is a shared experience principle
- **Decision:** OM-007 Actionable Experience → `04-SHARED-CAPABILITIES/Actionable-Experience/`. It is a shared principle/capability that **Commander Space consumes/applies**; it is **not** the Commander Space product and is **not** merged into PR-014.
- **Rationale:** Separates the reusable experience principle from the specific product.
- **Affected:** OM-007; PR-014.

### D-15 — One Delivery is a cross-Sigma foundation principle
- **Decision:** OM-009 One Delivery → `01-FOUNDATIONS/One-Delivery.md`. Not merged into the OM-001 shell in this batch; OM-001 may reference it when the Operating Model is rebuilt.
- **Rationale:** It expresses a cross-Sigma operating/delivery principle.
- **Affected:** OM-009; OM-001 (future).

### D-16 — Repository Catalog retained as evidence
- **Decision:** CAT-001 Repository Catalog → `06-DISCOVERY/Evidence/Legacy-Repository-Catalog.md`, knowledge status **HISTORICAL**. Not merged in this batch.
- **Rationale:** Useful evidence of the previous repository taxonomy; must not define V2 navigation or current architecture.
- **Affected:** CAT-001.

---

## Phase 3B / 3C — Owner Truth decisions (2026-08-30)

### D-17 — Sigma vs Zira: system ecosystem vs product/experience layer
- **Decision:** **Sigma** is the wider system / capability ecosystem (domain and shared capabilities: Operations Store, Geography / Spatial Intelligence, Context & Meaning, shared capabilities). **Zira** is Sigma's **product / experience layer** for users and contains the user-facing modules. **Commander Space** and **Operations Management** are modules inside Zira. **Operations Store, Geography / Spatial Intelligence, and Context & Meaning are Sigma capabilities, not Zira modules.** Commander Space does **not** contain Operations Management. `Zira` and `Sigma` are **not** synonyms — do not use "Zira / Sigma" as an interchangeable label.
- **Rationale:** Earlier drafts conflated Zira and Sigma; the owner clarified the boundary.
- **Implications:** Refines D-01 (Commander Space is a module inside Zira, not the whole experience layer). `CURRENT-STATE.md`, `Operations-Management.md`, GLOSSARY and this registry reflect this boundary.
- **Affected:** CURRENT-STATE; Operations Management; Commander Space; GLOSSARY; DOCUMENT-REGISTRY.

### D-18 — Standalone GANTTIT → Operations Management module inside Zira
- **Decision:** The standalone **GANTTIT** product direction is discontinued; the capability is moving to the **Operations Management** module inside **Zira**. Operations Management remains **distinct from Operations Store** and **from Commander Space**. This is a **product-direction** decision, **not** a claim about the current operational availability or shutdown state of any existing system.
- **Rationale:** Discovery identified low/insufficient adoption, high operational friction, continued reliance on slide-based workarounds, and unnecessary standalone complexity. The current direction is a simpler, integrated Zira module (Flat as default view, basic Gantt, Operation Page, create/edit Operations & Activities).
- **Implications:** New product document `02-DOMAINS/Operations/Product/Operations-Management.md`. No dates or delivery status are implied (see D-20).
- **Affected:** Operations Management; GANTTIT (superseded direction).

### D-19 — Operational Signal definition resolved (KB-001 legacy is stale)
- **Decision:** The current authoritative definition is: **Operational Signal = an evidence-backed statement of operational meaning produced by Context & Meaning.** It is **not** a raw event, a raw observation, or an uninterpreted data point (raw source events/observations remain distinct factual inputs). **Operational Meaning** remains the broader capability/concept; **Operational Signal** is the concrete evidence-backed C&M output. They stay **distinct**.
- **Rationale:** C&M ADR-01 + owner decision. Resolves the open item flagged in D-06.
- **Implications:** The **legacy KB-001 definition** (Operational Signal as raw data point) is **stale / superseded**. GLOSSARY updated accordingly.
- **Affected:** GLOSSARY; OM-004; C&M Operational Signal Schema; KB-001 (legacy).

### D-20 — Current delivery baseline is GREENFIELD / SETUP REQUIRED
- **Decision:** All major current Sigma capability areas require **GREENFIELD / SETUP REQUIRED**: Operations Store, Operations Management, Geography / Spatial Intelligence, Context & Meaning, and Zira / Commander Space (and its product modules). Documentation, prototypes, contracts, ADRs, schemas and Golden-E2E definitions are **not** implementation evidence.
- **Rationale:** No code/test/deployment/pilot evidence exists in the repository (extends D-09).
- **Implications:** Do **not** convert this baseline into LIVE / PILOT / BUILDING; use a more specific delivery status only where explicit implementation evidence exists. `CURRENT-STATE.md` records this baseline.
- **Affected:** All capability areas; CURRENT-STATE.

### D-21 — Geography product-capability model is current (not historical)
- **Decision:** The Geography product-capability model — **Spatialize · Resolve · Relate · Reconstruct · Qualify** — is the **current product-level model** and must **not** be classified as historical merely because the technical contract exposes a lower-level spatial-operation enum. **Spatial Evidence** = product/business abstraction; **SpatialResult** = technical/contract representation. Product capabilities and API operations are different abstraction levels (no required 1:1 mapping).
- **Rationale:** Owner clarification; supersedes the Phase-3A reconciliation report's tentative "historical" reading of these verbs.
- **Implications:** GLOSSARY records the current product model; control-plane docs must not tag these as historical.
- **Affected:** GLOSSARY; Geography material; CURRENT-STATE.

---

## Phase 4 — Commander Space composition (2026-08-30)

### D-22 — Commander Space composition resolved
- **Decision:** **Commander Space is Zira's role-based personal operational workspace.** It serves commanders **and other operational roles** — "Commander" describes the **decision-oriented** nature of the experience, **not** an exclusive user population; it is **not** an all-information dashboard. Its conceptual experience model is **Attention → Understand → Decide → Act** (a product/experience progression, **not** four required screens/routes/stages; a user may enter at the relevant level). **My Space is no longer a separate product concept — its personalized-workspace intent is absorbed into Commander Space.** **Headquarters Workspace is not a current canonical module or required sub-workspace;** its validated learnings — particularly **Operational Awareness** and *"what changed in the operational picture?"* — remain **reusable experience capabilities/patterns** that may be composed into Commander Space or other Zira modules when relevant. **Personalization changes attention, context, prioritization and available actions — not the underlying facts**, which remain shared and source-owned (the same fact may be surfaced differently to different roles without creating different versions of truth).
- **Rationale:** Resolves the previously-open Commander Space internal-composition ambiguity (identified in the continuation test). The legacy PR-014/015/016 workspace model (Commander Space = Headquarters + My Space) was conceptual exploration, not current product truth.
- **Implications:** Refines D-01 (naming) and supersedes the "My Space is current" part of D-02. Current product truth lives in `03-EXPERIENCE/Commander-Space/README.md`; `CURRENT-STATE.md`, `GLOSSARY.md`, `PR-001`, and this registry reflect it. **Boundaries preserved:** Commander Space ≠ Zira; Operations Management stays a separate Zira module; Operations Store owns operational truth; Geography owns spatial computation/Spatial Evidence; C&M remains optional. No personalization architecture/rules-engine and no delivery status are implied (baseline remains GREENFIELD / SETUP REQUIRED).
- **Legacy preservation:** PR-014, PR-015, PR-016 are **not deleted or rewritten** — retained as historical conceptual exploration ("explored then vs true now").
- **Affected:** Commander Space; My Space (PR-016); Headquarters Workspace (PR-015); PR-014; CURRENT-STATE; GLOSSARY; PR-001; DOCUMENT-REGISTRY.

---

## Architecture Decision Records

Full ADRs live with their domain and are indexed here as they are created:

- **Context & Meaning ADR** — `Context-and-Meaning/03_Context_and_Meaning_ADR.md` (accepted baseline decisions).
- **Geography ADR** — `Geography/03_Geography_ADR.md` (accepted baseline decisions, incl. federation over a canonical geo store).
- **Operations Store ADR & Contracts** — `Operations-Store/03_Operations_Store_ADR_and_Contracts_KB.docx` (pending DOCX conversion/verification).

*(Terminology and governance cleanups above are intentionally recorded as decision-log entries, not ADRs.)*
