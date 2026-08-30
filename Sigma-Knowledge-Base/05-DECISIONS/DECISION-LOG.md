# Decision Log

> Owner decisions taken during the Sigma Knowledge Base refactor. This log records **governance and terminology decisions**; full Architecture Decision Records (ADRs) are created only when a real architectural/product decision was made, and live with their domain.
>
> Rationale captured here is limited to what is evidenced by the migration review — no historical rationale is invented.

All decisions dated **2026-08-30** (knowledge-base refactor, Phase 1 → Batch 1).

---

### D-01 — Commander Space is the canonical experience/product name
- **Decision:** "Commander Space" is canonical. "Commander Experience" is terminology drift referring to the same experience layer, not a separate product or domain.
- **Rationale:** Two names for one layer were found across the repository (PR-014 uses "Commander Space"; the newer Context & Meaning and Geography packs use "Commander Experience"), with no explicit rename recorded.
- **Implications:** Navigation and newly authored text use "Commander Space." Historical documents are **not** rewritten yet; the alias is recorded in the glossary and registry.
- **Affected:** Commander Space concept; PR-014/015/016/017; Context & Meaning 01/02/03/05/06; Geography 01/02/03.

### D-02 — "My Space" is current; "Personal Workspace" retained for traceability
- **Decision:** The current experience name is **My Space**. PR-016 remains the stable document ID. The former term "Personal Workspace" is retained for traceability.
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

## Architecture Decision Records

Full ADRs live with their domain and are indexed here as they are created:

- **Context & Meaning ADR** — `Context-and-Meaning/03_Context_and_Meaning_ADR.md` (accepted baseline decisions).
- **Geography ADR** — `Geography/03_Geography_ADR.md` (accepted baseline decisions, incl. federation over a canonical geo store).
- **Operations Store ADR & Contracts** — `Operations-Store/03_Operations_Store_ADR_and_Contracts_KB.docx` (pending DOCX conversion/verification).

*(Terminology and governance cleanups above are intentionally recorded as decision-log entries, not ADRs.)*
