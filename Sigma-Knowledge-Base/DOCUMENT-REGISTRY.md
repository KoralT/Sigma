# Document Registry (V2)

> **Authoritative map of what exists in this repository, where it physically is *today*, and what it is.**
>
> This registry describes the repository **as it actually exists after Batch 1 of the knowledge-base refactor** — the V2 file migration has **not** happened yet. The `Current Path` column is real; the `Planned V2 Path` column is intended and not yet in effect.
>
> - Document **IDs are stable** traceability identifiers. Newer domain documents were authored without IDs and are listed by title.
> - **`ARC-001` has been removed as a required document.** It was never created; its entry-architecture role is served by [START-HERE.md](START-HERE.md), the Platform Architecture document (PA-001), and this registry.
> - **Knowledge status ≠ delivery status.** Delivery is tracked only in [CURRENT-STATE.md](CURRENT-STATE.md). "Foundational" classification does **not** imply completeness or canonical authority.
> - Unresolved canonical conflicts are listed openly in the final section rather than hidden.

Knowledge-status values used: **VALIDATED** (accepted baseline decision), **WORKING** (substantive draft), **SHELL** (placeholder/skeleton — no authority yet), **LEGACY** (older governance document with a planned replacement; not yet superseded), **HISTORICAL** (kept as evidence/governance of record).

---

## Control plane (created in Batch 1)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Start Here | START-HERE.md | Navigation / entry | WORKING | Entry point (Batch 1) | START-HERE.md |
| — | Current State | CURRENT-STATE.md | Knowledge↔delivery bridge | WORKING | Current-state bridge (Batch 1) | CURRENT-STATE.md |
| — | Document Registry (V2) | DOCUMENT-REGISTRY.md | Governance | WORKING | Registry (V2, Batch 1) | DOCUMENT-REGISTRY.md |
| — | Glossary | GLOSSARY.md | Vocabulary | WORKING | Glossary (V2, Batch 1) | GLOSSARY.md |
| — | Decision Log | 05-DECISIONS/DECISION-LOG.md | Decisions | WORKING | Decision log (Batch 1) | 05-DECISIONS/DECISION-LOG.md |

## Legacy governance (planned replacement — still physically present; supersession pending approval)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Sigma Document Registry v1.1 | DOCUMENT_REGISTRY.md | Governance | Legacy | Legacy governance document — replacement introduced in Batch 1 (DOCUMENT-REGISTRY.md); supersession pending approval | Planned replacement: DOCUMENT-REGISTRY.md |
| KB-000 | Knowledge Base Guide | KB/KB-000 – Knowledge Base Guide.md | Governance | Legacy | Legacy governance document — replacement introduced in Batch 1 (START-HERE.md); supersession pending approval | Planned replacement: START-HERE.md |
| KB-001 | Sigma Glossary | KB/KB-001 – Sigma Glossary.md | Vocabulary | WORKING | Source for GLOSSARY.md | GLOSSARY.md |
| CAT-001 | Repository Catalog | CAT/CAT-001 Repository Catalog.md | Repository taxonomy | WORKING | Merge-candidate (registry / repo architecture) | *pending reconciliation* |
| — | README | README.md | Repo front door | SHELL | To be rebuilt | README.md |

## Foundations (Layer A)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| DOC-001 | Sigma Doctrine | DOC/DOC-001 Sigma Doctrine.md | Doctrine | **SHELL** | None until written | 01-FOUNDATIONS/Sigma-Doctrine.md |
| OM-001 | Sigma Operating Model | OM/OM-001 Sigma Operating Model.md | Operating model | **SHELL** | None until written | 01-FOUNDATIONS/Operating-Model.md |
| PR-001 | Sigma Product Portfolio | PR/PR-001 Sigma Product Portfolio.md | Product portfolio | **SHELL** | None until written | 01-FOUNDATIONS/Product-Portfolio.md |
| PA-001 | Sigma Platform Architecture | PA/PA-001 Sigma Platform Architecture.md | Platform architecture | WORKING | **Candidate** (contains a duplicated block to clean) | 01-FOUNDATIONS/Platform-Architecture.md |

## Operations (Layer B) — see canonical conflict #1

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Operations Store — PRD | Operations-Store/01_Operations_Store_PRD_KB.docx | Operations Store (product) | WORKING (.docx, unverified) | Candidate — Operations Store | 02-DOMAINS/Operations/Product/ |
| — | Operations Store — HLD | Operations-Store/02_Operations_Store_HLD_KB.docx | Operations Store (arch) | WORKING (.docx) | Candidate | 02-DOMAINS/Operations/Architecture/ |
| — | Operations Store — ADR & Contracts | Operations-Store/03_Operations_Store_ADR_and_Contracts_KB.docx | Operations Store (decisions) | WORKING (.docx) | Candidate | 02-DOMAINS/Operations/Architecture/ |
| — | Operations Store — Canonical Schema v0.1 | Operations-Store/04_Operations_Store_Canonical_Schema_v0.1.docx | Canonical operational schema | WORKING (.docx) | Candidate | 02-DOMAINS/Operations/Contracts/ |
| — | Operations Store — API/Event Contract v0.1 | Operations-Store/06_Operations_Store_API_Event_Contract_v0.1.docx | Ops Store API/event contract | WORKING (.docx) | Candidate | 02-DOMAINS/Operations/Contracts/ |
| — | Operations Store — Golden E2E / Phase-1 DoD | Operations-Store/07_Operations_Store_Golden_E2E_Phase1_DoD_Runbook.docx | Domain acceptance contract | WORKING (.docx) | Candidate | 02-DOMAINS/Operations/Delivery/ |
| — | Operations Store — OpenAPI starter | Operations-Store/08_operations_store_openapi_starter_v0.1.yaml | Ops Store REST contract | WORKING | Candidate | 02-DOMAINS/Operations/Contracts/ |
| — | Operations Store — AsyncAPI starter | Operations-Store/09_operations_store_asyncapi_starter_v0.1.yaml | Ops Store event contract | WORKING | Candidate | 02-DOMAINS/Operations/Contracts/ |
| CAT-010 | Operations Repository | CAT/CAT-010 Operations Repository.md | Operations knowledge model | WORKING (has duplicated section) | Candidate — distinct from Operations Store | 02-DOMAINS/Operations/Knowledge/ |
| PR-017 | Operational Repositories | PR/PR-017 Operational Repositories.md | Operational Repositories (product) | WORKING | Candidate — distinct from above | *pending reconciliation* |

## Geography / Spatial Intelligence (Layer B)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Geography — PRD | Geography/01_Geography_PRD(1).md | Geography (product) | WORKING | Candidate | 02-DOMAINS/Geography/Product/ |
| — | Geography — HLD | Geography/02_Geography_HLD(1).md | Geography (arch) | WORKING | Candidate | 02-DOMAINS/Geography/Architecture/ |
| — | Geography — ADR | Geography/03_Geography_ADR.md | Geography decisions | **VALIDATED** | Canonical decisions | 02-DOMAINS/Geography/Architecture/ |
| — | Geography — Source Mapping | Geography/04_Geography_Source_Mapping.md | Geography source contract | WORKING | Candidate | 02-DOMAINS/Geography/Contracts/ |
| — | Geography — Golden E2E / Phase-1 | Geography/05_Geography_Golden_E2E_and_Phase1.md | Domain acceptance contract | WORKING | Candidate | 02-DOMAINS/Geography/Delivery/ |
| — | Spatial Intelligence (Vision/Strategy) | Geography/Spatial-Intelligence.md | Spatial Intelligence strategy | WORKING (dirty formatting) | Candidate | 02-DOMAINS/Geography/Strategy/ |

## Context & Meaning (Layer B) — see distinction #6

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Context & Meaning — PRD | Context-and-Meaning/01_Context_and_Meaning_PRD.md | C&M (product) | WORKING | Candidate | 02-DOMAINS/Context-and-Meaning/Product/ |
| — | Context & Meaning — HLD | Context-and-Meaning/02_Context_and_Meaning_HLD.md | C&M (arch) | WORKING | Candidate | 02-DOMAINS/Context-and-Meaning/Architecture/ |
| — | Context & Meaning — ADR | Context-and-Meaning/03_Context_and_Meaning_ADR.md | C&M decisions | **VALIDATED** | Canonical decisions | 02-DOMAINS/Context-and-Meaning/Architecture/ |
| — | Context & Meaning — Input & Source Contract | Context-and-Meaning/04_Context_and_Meaning_Input_Source_Contract.md | C&M input contract | WORKING | Candidate | 02-DOMAINS/Context-and-Meaning/Contracts/ |
| — | Operational Signal Schema v0.1 | Context-and-Meaning/05_Context_and_Meaning_Operational_Signal_Schema.md | **Operational Signal** (contract) | WORKING | Candidate — *not* Operational Meaning | 02-DOMAINS/Context-and-Meaning/Contracts/ |
| — | Context & Meaning — Golden E2E / Phase-1 | Context-and-Meaning/06_Context_and_Meaning_Golden_E2E_and_Phase1.md | Domain acceptance contract | WORKING | Candidate | 02-DOMAINS/Context-and-Meaning/Delivery/ |

## Commander Space (experience layer) — canonical name

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| PR-014 | Commander Space | PR/PR-014 Commander Space.md | Commander Space | WORKING | **Canonical — Commander Space** | 03-EXPERIENCE/Commander-Space/Commander-Space.md |
| PR-015 | Headquarters Workspace | PR/PR-015 Headquarters Workspace.md | Headquarters Workspace | WORKING | Candidate | 03-EXPERIENCE/Commander-Space/Headquarters/ |
| PR-016 | Personal Workspace → **My Space** | PR/PR-016 Personal Workspace.md | My Space (was Personal Workspace) | WORKING | Candidate | 03-EXPERIENCE/Commander-Space/My-Space/ |

## Shared capabilities (Layer A concept papers)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| OM-004 | Operational Meaning | OM/OM-004 Operational Meaning.md | **Operational Meaning** (capability) | WORKING | Candidate — *not* Operational Signal | 04-SHARED-CAPABILITIES/Operational-Meaning/ |
| OM-005 | Operational Assets | OM/OM-005 Operational Assets.md | Operational Assets | WORKING | Candidate | 04-SHARED-CAPABILITIES/Knowledge/ |
| OM-006 | Trusted Context | OM/OM-006 Trusted Context.md | Trusted Context | WORKING | Candidate | 04-SHARED-CAPABILITIES/Trusted-Context/ |
| OM-007 | Actionable Experience | OM/OM-007 Actionable Experience.md | Actionable Experience | WORKING | Candidate — placement open | *pending reconciliation* |
| OM-008 | Trust Framework | OM/OM-008 Trust Framework.md | Trust | WORKING | Candidate | 04-SHARED-CAPABILITIES/Trust/ |
| OM-009 | One Delivery | OM/OM-009 One Delivery.md | Delivery model | WORKING | Candidate — placement open | *pending reconciliation* |
| DM-001 | Decision Model | DM/DM-001 Decision Model.md | Decision Model | WORKING | Candidate | 04-SHARED-CAPABILITIES/Decision-Model/ |
| PA-007 | Context Engine | PA/PA-007 Context Engine.md | Trusted-context assembly | **SHELL** | None until written | 04-SHARED-CAPABILITIES/Trusted-Context/ |
| PA-008 | Knowledge Graph | PA/PA-008 Knowledge Graph.md | Knowledge Graph | **SHELL** | None until written | 04-SHARED-CAPABILITIES/Knowledge/ |
| PA-009 | Repository Architecture | PA/PA-009 Repository Architecture.md | Repository architecture | **SHELL** | None until written | 02-DOMAINS/Operations/Architecture/ |
| PA-010 | Entity Model | PA/PA-010 Entity Model.md | Entity Model | WORKING | Candidate — placement open | *pending reconciliation* |
| PA-011 | AI Foundation | PA/PA-011 AI Foundation.md | AI Foundation | WORKING | Candidate | 04-SHARED-CAPABILITIES/AI/ |

## Discovery / Research (Layer A)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| RS-001 | Sigma Discovery & Research | RS/RS-001 Sigma Discovery & Research.md | Discovery/research | **SHELL** | None until written | 06-DISCOVERY/Research/ |
| RS-003 | Discovery Findings | RS/RS-003 Discovery Findings.md | Discovery findings | **SHELL** | None until written | 06-DISCOVERY/Evidence/ |
| — | KB Accuracy Review (2026-08-30) | Sigma_KB_Accuracy_Review.md *(repo root)* | Prior audit evidence | HISTORICAL | Evidence only | 06-DISCOVERY/Evidence/ |

## Execution / handoff (Layer B)

| ID | Document | Current Path | Concept / Domain | Knowledge Status | Canonical Role | Planned V2 Path |
|--|--|--|--|--|--|--|
| — | Operational Data Foundation (annual initiative) | Operations-Store/Operational-Data-Foundation.md | Cross-domain annual plan (Ops+Geo) | WORKING (dirty formatting) | Candidate | 07-EXECUTION/Annual-Plans/ |
| — | Final Execution Handoff 2026–2027 | SIGMA_FINAL_EXECUTION_HANDOFF_2026_2027.xlsx | Execution handoff | WORKING (binary, unreviewed) | Candidate | 07-EXECUTION/Handoffs/ |

---

## Unresolved canonical conflicts (exposed, not resolved)

1. **Operations Store vs Operations Repository (CAT-010) vs Operational Repositories (PR-017)** — possibly distinct abstraction levels; kept separate; **no merge authorized** pending semantic reconciliation.
2. **Commander Space vs "Commander Experience"** — same experience layer; **Commander Space is canonical**; "Commander Experience" is legacy drift found in the Context & Meaning and Geography packs. Historical documents are not being rewritten yet.
3. **Personal Workspace vs My Space** — **My Space** is the current name; PR-016 remains the stable ID; "Personal Workspace" retained for traceability.
4. **Operational Meaning (OM-004) vs Operational Signal (C&M schema)** — **distinct** (capability vs concrete output/contract); relationship to be documented, not merged.
5. **Foundational shells** — DOC-001, OM-001, PR-001, RS-001, RS-003, PA-007, PA-008, PA-009 are placeholders/skeletons with **no canonical authority** despite classification.
6. **Placement open** — Entity Model (PA-010), Actionable Experience (OM-007), One Delivery (OM-009), and the CAT-001 catalog have no settled canonical home yet.
7. **ARC-001** — referenced by DOCUMENT_REGISTRY (legacy), CAT-001, DM-001, PA-010, PA-011 but **does not exist and will not be created**; those references are marked for removal during migration.
