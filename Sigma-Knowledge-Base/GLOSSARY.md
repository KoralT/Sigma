# Sigma Glossary

> Shared vocabulary for the Sigma Knowledge Base. Definitions are **seeded from KB-001 (Sigma Glossary)** and extended only with terminology that is **explicitly present in approved repository material**. No definitions are invented to force consistency.
>
> Where a term's meaning is contested or unresolved between documents, that is stated openly rather than smoothed over. Canonical naming decisions are recorded in [05-DECISIONS/DECISION-LOG.md](05-DECISIONS/DECISION-LOG.md).

---

## Naming — canonical terms and their aliases

### Commander Space
The canonical name for Sigma's experience / decision / product layer, through which relevant understanding becomes human awareness, decision, and action. Defined in PR-014. **This is the term to use.**

### Commander Experience *(deprecated alias)*
Legacy terminology drift for **Commander Space**. Appears in the Context & Meaning and Geography document packs to refer to the same experience layer. It is **not** a separate product or domain. Retained here only so older documents remain interpretable; new material should say *Commander Space*.

### My Space
The **current** name for the individual operational experience within Commander Space (situational awareness, personal execution, task management). Documented under stable ID **PR-016**.

### Personal Workspace *(former term)*
The **former** name for what is now **My Space**. Retained for traceability to PR-016 and to older references; not the current term.

---

## Operations terminology — kept separate (not merged)

> These three terms have overlapping names but are treated as **different abstraction levels**. They must **not** be automatically merged. The Operations Store ↔ Operations Repository relationship is still pending full semantic reconciliation (see [CURRENT-STATE.md](CURRENT-STATE.md) and the registry's conflict list).

### Operations Store
Owner-designated role: the **operational domain capability / system of record for Sigma's canonical Operation representation and relevant operational state**. It owns operation identity/core, plan, activities, milestones, dependencies, relevant factual state, projections/references to external professional objects, provenance, planned-vs-actual, and snapshots/audit where defined. It does **not** own cross-domain operational meaning, Commander attention/prioritization, GIS/spatial computation, machine-generated readiness scores, or professional-system source objects. Authored in the `Operations-Store/` package (currently `.docx`, **pending conversion** — contents not yet reviewable as text). Home: `02-DOMAINS/Operations/`.

### Operations Repository
The **operations knowledge model** described in CAT-010 (now `02-DOMAINS/Operations/Knowledge/Operations-Repository.md`) — operations as interconnected operational objects within a dynamic operational network. Treated as an **earlier/broader** repository model: knowledge status WORKING, **not canonical**, and it **does not override** the current Operations Store contracts.

### Operational Repositories
The older product-level concept in PR-017, now archived (`99-ARCHIVE/Historical/Product-Concepts/`) with knowledge status **HISTORICAL**. Retained as historical product framing; it does **not** define the current Operations Store architecture.

---

## Meaning vs Signal — distinct (not synonyms)

### Operational Meaning
An organizational / platform **concept and capability**: turning operational signals into shared, meaningful operational understanding. Concept paper: OM-004. *(KB-001 sense: "the shared interpretation assigned to one or more operational signals.")*

### Operational Signal
Two definitions for this term currently exist in the repository and **conflict**; neither has been designated canonical:
- **Legacy definition (observed in KB-001):** "a raw observation, event, or data point generated during operational activity … facts before interpretation."
- **Current C&M contract definition (observed in the Operational Signal Schema v0.1):** "a traceable statement of operational meaning derived from domain facts in context," explicitly **not** a raw event and **not** a commander-specific recommendation.

> **Recorded conflict:** these two definitions are incompatible (raw pre-interpretation fact vs. evidence-backed meaning statement). Per owner decision, *Operational Signal* and *Operational Meaning* are **not synonymous**. The conflict between the two *Operational Signal* definitions above **remains unresolved**; no single definition is selected as canonical here.

---

## Core concepts *(seeded from KB-001)*

### Capability
A reusable organizational ability that enables a specific operational outcome. Capabilities are independent of products and technology.

### Trusted Context
A coherent operational understanding assembled from validated operational meaning. Trusted Context provides decision-makers with reliable situational awareness. Concept paper: OM-006.

### Actionable Experience
A user-facing operational experience that enables people to understand, decide, or act using trusted context. Concept paper: OM-007.

### Operational Asset
A reusable organizational knowledge asset that contributes to operational capability. Examples include repositories, playbooks, procedures, policies, models, and structured knowledge. Concept paper: OM-005.

### Repository
A managed collection of operational assets maintained as a trusted organizational source. Repositories preserve institutional knowledge and enable reuse. *(See the separate, unresolved Operations terminology above before equating this with "Operations Repository".)*

### Workspace
A user-facing operational environment designed to support a specific set of responsibilities. Workspaces consume platform capabilities rather than implement them.

### Entity
A uniquely identifiable operational object represented within Sigma. Entities may represent people, units, assets, locations, missions, systems, or any other operational object. Model paper: PA-010.

### Relationship
A meaningful connection between two or more entities. Relationships provide the structural foundation for understanding operational context.

### Context
The current operational understanding derived from relevant entities, relationships, operational meaning, and organizational knowledge.

### Knowledge
Validated organizational understanding that remains reusable beyond a single operational event.

### Platform
The collection of shared capabilities that enable Sigma's operating model. The platform serves all Sigma products.

### Product
A user-facing solution that delivers operational value using the shared Sigma platform.

### Governance
The mechanisms through which Sigma maintains consistency, quality, ownership, and long-term sustainability.

### Trust Framework
The principles ensuring that Sigma remains transparent, explainable, auditable, and trustworthy throughout its operation. Concept paper: OM-008.

### Human-in-the-Loop
A design principle in which operational decisions remain under human authority while Sigma provides decision support.

---

## Terms present in repository material — no single glossary definition yet designated

> The following terms appear in current domain/engineering material. They are listed so the gap is visible: a term appearing here means the repository has **no single designated glossary definition** for it — not that it lacks meaning in the source documents. Any definition must come from approved source material, not invention.

- **Spatial Intelligence** — appears in the Geography domain material (shared organizational spatial information, computation, relationships, and spatial evidence); no single glossary definition has yet been designated.
- **Federated Spatial Intelligence Layer** — appears in the Geography material as its architectural stance (federate + compute over authoritative sources; no default canonical geo store); no single glossary definition has yet been designated.
- **Evidence Gate**, **Trust Contract**, **Capability Mesh** — appear in repository material; no single glossary definition has yet been designated.
