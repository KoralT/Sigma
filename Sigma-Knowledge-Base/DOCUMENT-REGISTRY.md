# Document Registry (V2)

> **Authoritative map of what exists in this repository, where it physically is, and what it is.**
>
> This registry describes the repository **as it actually exists after Batch 2A** of the knowledge-base refactor. Every `Current Path` below is the **real physical path**. Documents that have been moved to their V2 location no longer carry a "planned" path; items still pending a later batch are listed separately.
>
> - Document **IDs are stable** traceability identifiers. Newer domain documents were authored without IDs and are listed by title.
> - **`ARC-001` has been removed as a required document.** It was never created; its entry-architecture role is served by [START-HERE.md](START-HERE.md), the Platform Architecture document (`01-FOUNDATIONS/Platform-Architecture.md`), and this registry.
> - **Sigma vs Zira:** `Sigma` is the wider capability ecosystem; **Zira** is Sigma's product/experience layer, containing user-facing modules such as **Commander Space** and **Operations Management**. Operations Store, Geography / Spatial Intelligence and Context & Meaning are **Sigma capabilities, not Zira modules** (see [DECISION-LOG D-17](05-DECISIONS/DECISION-LOG.md)).
> - **Knowledge status ≠ delivery status.** Delivery is tracked only in [CURRENT-STATE.md](CURRENT-STATE.md); the current delivery baseline is **GREENFIELD / SETUP REQUIRED** ([D-20](05-DECISIONS/DECISION-LOG.md)) — documentation, contracts, ADRs, schemas and Golden-E2E definitions are **not** implementation evidence. "Foundational" classification does **not** imply completeness or canonical authority.
> - The **Operations Store DOCX package has NOT been converted** — it remains under `Operations-Store/` pending Batch 2B.
> - Unresolved canonical conflicts are listed openly in the final section rather than hidden.

Knowledge-status values: **VALIDATED** (accepted baseline decision), **WORKING** (substantive draft), **SHELL** (placeholder/skeleton — no authority yet), **LEGACY** (older governance document with a planned replacement; not yet superseded), **HISTORICAL** (retained for traceability/evidence; not current guidance).

Each migrated domain has a `README.md` describing what it owns, does not own, and its boundaries.

---

## Control plane

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Start Here | START-HERE.md | Navigation / entry | WORKING | Entry point |
| — | Current State | CURRENT-STATE.md | Knowledge↔delivery bridge | WORKING | Current-state bridge |
| — | Document Registry (V2) | DOCUMENT-REGISTRY.md | Governance | WORKING | Registry (V2) |
| — | Glossary | GLOSSARY.md | Vocabulary | WORKING | Glossary (V2) |
| — | Decision Log | 05-DECISIONS/DECISION-LOG.md | Decisions | WORKING | Decision log |

## Legacy governance (planned replacement — still physically present; supersession pending approval)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Sigma Document Registry v1.1 | DOCUMENT_REGISTRY.md | Governance | LEGACY | Replacement introduced (DOCUMENT-REGISTRY.md); supersession pending approval |
| KB-000 | Knowledge Base Guide | KB/KB-000 – Knowledge Base Guide.md | Governance | LEGACY | Replacement introduced (START-HERE.md); supersession pending approval |
| KB-001 | Sigma Glossary | KB/KB-001 – Sigma Glossary.md | Vocabulary | LEGACY | Source for GLOSSARY.md; supersession pending approval |
| — | README | README.md | Repo front door | LEGACY | Legacy navigation artifact; to be rebuilt |

## 01 — Foundations

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| PA-001 | Platform Architecture | 01-FOUNDATIONS/Platform-Architecture.md | Platform architecture | WORKING | Candidate (contains a duplicated block still to clean) |
| OM-009 | One Delivery | 01-FOUNDATIONS/One-Delivery.md | Cross-Sigma delivery principle | WORKING | Candidate |
| DOC-001 | Sigma Doctrine | DOC/DOC-001 Sigma Doctrine.md | Doctrine | SHELL | None until written *(not moved this batch)* |
| OM-001 | Sigma Operating Model | OM/OM-001 Sigma Operating Model.md | Operating model | SHELL | None until written *(not moved this batch)* |
| PR-001 | Sigma Product Portfolio | PR/PR-001 Sigma Product Portfolio.md | Product portfolio | SHELL | None until written *(not moved this batch)* |

## 02 — Domains › Operations — see canonical conflict #1

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Operations domain README | 02-DOMAINS/Operations/README.md | Operations | WORKING | Navigation |
| — | Operations Management | 02-DOMAINS/Operations/Product/Operations-Management.md | Operations Management (Zira module) | WORKING | Current product direction — module inside Zira; uses Operations Store as backbone; distinct from the Store and from Commander Space (D-18) |
| — | Operations Store — OpenAPI starter | 02-DOMAINS/Operations/Contracts/operations-store-openapi-starter-v0.1.yaml | Ops Store REST contract | WORKING | Candidate |
| — | Operations Store — AsyncAPI starter | 02-DOMAINS/Operations/Contracts/operations-store-asyncapi-starter-v0.1.yaml | Ops Store event contract | WORKING | Candidate |
| CAT-010 | Operations Repository | 02-DOMAINS/Operations/Knowledge/Operations-Repository.md | Operations knowledge model | WORKING | **Broader/earlier model; not canonical**; does not override Operations Store contracts |

> **Operations Store package (still `Operations-Store/*.docx`, pending Batch 2B conversion):** PRD (01), HLD (02), ADR & Contracts (03), Canonical Schema v0.1 (04), API/Event Contract v0.1 (06), Golden E2E/Phase-1 DoD (07). Owner-designated role: **Operations Store = operational domain capability / system of record for Sigma's canonical Operation representation and relevant operational state** (contents pending conversion/verification; not yet reviewable as text).

## 02 — Domains › Geography / Spatial Intelligence

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Geography domain README | 02-DOMAINS/Geography/README.md | Geography | WORKING | Navigation |
| — | Geography — PRD | 02-DOMAINS/Geography/Product/Geography-PRD.md | Geography (product) | WORKING | Candidate |
| — | Geography — HLD | 02-DOMAINS/Geography/Architecture/Geography-HLD.md | Geography (arch) | WORKING | Candidate |
| — | Geography — ADR | 02-DOMAINS/Geography/Architecture/Geography-ADR.md | Geography decisions | VALIDATED | Accepted baseline decisions |
| — | Geography — Source Mapping | 02-DOMAINS/Geography/Contracts/Geography-Source-Mapping.md | Geography source contract | WORKING | Candidate |
| — | Geography — Golden E2E / Phase-1 | 02-DOMAINS/Geography/Delivery/Geography-Golden-E2E-Phase1.md | Domain acceptance contract | WORKING | Candidate |
| — | Spatial Intelligence (Vision/Strategy) | 02-DOMAINS/Geography/Strategy/Spatial-Intelligence.md | Spatial Intelligence strategy | WORKING | Candidate (dirty formatting; cleanup pending) |

## 02 — Domains › Context & Meaning — see distinction #4

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Context & Meaning domain README | 02-DOMAINS/Context-and-Meaning/README.md | C&M | WORKING | Navigation |
| — | Context & Meaning — PRD | 02-DOMAINS/Context-and-Meaning/Product/Context-and-Meaning-PRD.md | C&M (product) | WORKING | Candidate |
| — | Context & Meaning — HLD | 02-DOMAINS/Context-and-Meaning/Architecture/Context-and-Meaning-HLD.md | C&M (arch) | WORKING | Candidate |
| — | Context & Meaning — ADR | 02-DOMAINS/Context-and-Meaning/Architecture/Context-and-Meaning-ADR.md | C&M decisions | VALIDATED | Accepted baseline decisions |
| — | Context & Meaning — Input & Source Contract | 02-DOMAINS/Context-and-Meaning/Contracts/Context-and-Meaning-Input-Source-Contract.md | C&M input contract | WORKING | Candidate |
| — | Operational Signal Schema v0.1 | 02-DOMAINS/Context-and-Meaning/Contracts/Operational-Signal-Schema-v0.1.md | **Operational Signal** (contract) | WORKING | Candidate — current authoritative *Operational Signal* definition (D-19); *not* Operational Meaning |
| — | Context & Meaning — Golden E2E / Phase-1 | 02-DOMAINS/Context-and-Meaning/Delivery/Context-and-Meaning-Golden-E2E-Phase1.md | Domain acceptance contract | WORKING | Candidate |

## 03 — Zira (experience layer) › Commander Space (module inside Zira)

> **Zira** is Sigma's product/experience layer; **Commander Space** is a module inside it (Operations Management is another). Commander Space is **not** the whole experience layer (D-17). It is **Zira's role-based personal operational workspace** (serving commanders and other operational roles); **My Space is absorbed** into it and **Headquarters Workspace is not a current canonical module** ([D-22](05-DECISIONS/DECISION-LOG.md)). Current product truth is the **README**; PR-014/015/016 are legacy conceptual exploration, retained as history. *(Folder is `03-EXPERIENCE/` from the earlier migration; not renamed.)*

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Commander Space README | 03-EXPERIENCE/Commander-Space/README.md | Commander Space | WORKING | **Current Commander Space product truth** (D-22) |
| PR-014 | Commander Space *(legacy conceptual)* | 03-EXPERIENCE/Commander-Space/Commander-Space.md | Commander Space | HISTORICAL | Legacy conceptual exploration; current truth in README. "Commander Space" remains the canonical **name** (D-01) |
| PR-015 | Headquarters Workspace *(legacy)* | 03-EXPERIENCE/Commander-Space/Headquarters/Headquarters-Workspace.md | Headquarters Workspace | HISTORICAL | Not a current canonical module; Operational Awareness learning retained as a reusable pattern (D-22) |
| PR-016 | My Space *(legacy; former: Personal Workspace)* | 03-EXPERIENCE/Commander-Space/My-Space/My-Space.md | My Space | HISTORICAL | My Space **absorbed** into Commander Space; not a current separate module (D-22); `former_name: Personal Workspace` retained |

## 04 — Shared Capabilities

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| OM-004 | Operational Meaning | 04-SHARED-CAPABILITIES/Operational-Meaning/Operational-Meaning.md | **Operational Meaning** (capability) | WORKING | Candidate — *not* Operational Signal |
| OM-005 | Operational Assets | 04-SHARED-CAPABILITIES/Knowledge/Operational-Assets.md | Operational Assets | WORKING | Candidate |
| OM-006 | Trusted Context | 04-SHARED-CAPABILITIES/Trusted-Context/Trusted-Context.md | Trusted Context | WORKING | Candidate |
| OM-007 | Actionable Experience | 04-SHARED-CAPABILITIES/Actionable-Experience/Actionable-Experience.md | Actionable Experience (shared principle/capability) | WORKING | Candidate — Commander Space consumes it |
| OM-008 | Trust Framework | 04-SHARED-CAPABILITIES/Trust/Trust-Framework.md | Trust | WORKING | Candidate |
| DM-001 | Decision Model | 04-SHARED-CAPABILITIES/Decision-Model/Decision-Model.md | Decision Model | WORKING | Candidate |
| PA-010 | Entity Model | 04-SHARED-CAPABILITIES/Knowledge/Entity-Model.md | Entity Model (cross-cutting semantics) | WORKING | Candidate — **not** canonical for Operations entities |
| PA-011 | AI Foundation | 04-SHARED-CAPABILITIES/AI/AI-Foundation.md | AI Foundation | WORKING | Candidate |

## 06 — Discovery / Evidence

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| CAT-001 | Legacy Repository Catalog | 06-DISCOVERY/Evidence/Legacy-Repository-Catalog.md | Repository taxonomy (legacy) | HISTORICAL | Evidence only — not V2 navigation |
| — | KB Accuracy Review (2026-08-30) | Sigma_KB_Accuracy_Review.md *(repo root)* | Prior audit evidence | HISTORICAL | Evidence only *(not moved this batch)* |
| RS-001 | Sigma Discovery & Research | RS/RS-001 Sigma Discovery & Research.md | Discovery/research | SHELL | None until written *(not moved this batch)* |
| RS-003 | Discovery Findings | RS/RS-003 Discovery Findings.md | Discovery findings | SHELL | None until written *(not moved this batch)* |

## 07 — Execution / handoff

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| — | Execution Model | 07-EXECUTION/EXECUTION-MODEL.md | Execution model | WORKING | Canonical human-readable execution model (summary of the handoff XLSX) |
| — | Operational Data Foundation (annual initiative) | 07-EXECUTION/Annual-Plans/Operational-Data-Foundation.md | Cross-domain annual plan (Ops+Geo) | WORKING | Candidate (dirty formatting; cleanup pending) |
| — | Final Execution Handoff 2026–2027 | 07-EXECUTION/Handoffs/SIGMA-FINAL-EXECUTION-HANDOFF-2026-2027.xlsx | Execution handoff | WORKING | Candidate (binary, unreviewed) |

## 99 — Archive › Historical

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Role |
|--|--|--|--|--|--|
| PR-017 | Operational Repositories | 99-ARCHIVE/Historical/Product-Concepts/PR-017-Operational-Repositories.md | Product concept (legacy) | HISTORICAL | Historical product framing; not current architecture |
| PA-007 | Context Engine | 99-ARCHIVE/Historical/Architecture-Skeletons/PA-007-Context-Engine.md | Architecture skeleton | HISTORICAL | Archived skeleton — capability not rejected |
| PA-008 | Knowledge Graph | 99-ARCHIVE/Historical/Architecture-Skeletons/PA-008-Knowledge-Graph.md | Architecture skeleton | HISTORICAL | Archived skeleton — capability not rejected |
| PA-009 | Repository Architecture | 99-ARCHIVE/Historical/Architecture-Skeletons/PA-009-Repository-Architecture.md | Architecture skeleton | HISTORICAL | Archived skeleton — capability not rejected |

---

## Unresolved canonical conflicts (exposed, not resolved)

1. **Operations Store vs Operations Repository (CAT-010) vs Operational Repositories (PR-017)** — kept **separate**. Owner direction: Operations Store is the operational system of record (canonical role, contents pending DOCX conversion); CAT-010 is a broader/earlier operations knowledge model (WORKING, not canonical, does not override Store contracts); PR-017 is archived historical product framing. Full semantic reconciliation between Operations Store and CAT-010 is still pending.
2. **Commander Space vs "Commander Experience"** — the same commander-facing **module inside Zira**; **Commander Space is canonical**; "Commander Experience" is legacy drift in the Context & Meaning and Geography packs. Commander Space is not the whole experience layer (that is Zira — D-17). Historical documents are not rewritten.
3. **Personal Workspace vs My Space** — **My Space** is the current name; PR-016 remains the stable ID (`former_name: Personal Workspace` recorded).
4. **Operational Meaning (OM-004) vs Operational Signal (C&M schema)** — **distinct** (broader capability vs concrete evidence-backed C&M output); not merged. **RESOLVED (D-19):** the *Operational Signal* definition conflict is settled — the C&M evidence-backed statement is authoritative; the legacy **KB-001** raw-data definition is **stale/superseded** (see GLOSSARY). Retained here for traceability.
5. **Entity Model (PA-010) vs Operations Store schema** — PA-010 provides cross-cutting conceptual entity semantics; Operations Store owns its own canonical operational schema. Any conflict is to be exposed, not silently reconciled.
6. **Foundational shells** — DOC-001, OM-001, PR-001, RS-001, RS-003 remain placeholders with **no canonical authority** despite classification (not moved this batch).
7. **ARC-001** — **does not exist and will not be created.** Active-document references were removed in Batch 2A: DM-001, PA-010, and PA-011 now reference `01-FOUNDATIONS/Platform-Architecture.md` in their References sections instead. Remaining ARC-001 mentions live only in the legacy `DOCUMENT_REGISTRY.md` and the historical `Legacy-Repository-Catalog.md` (CAT-001), retained for traceability and clearly historical. No active document depends on ARC-001.
