# Sigma Glossary

> Shared vocabulary for the Sigma Knowledge Base. Definitions are **seeded from KB-001 (Sigma Glossary)** and extended only with terminology that is **explicitly present in approved repository material**. No definitions are invented to force consistency.
>
> Where a term's meaning is contested or unresolved between documents, that is stated openly rather than smoothed over. Canonical naming decisions are recorded in [05-DECISIONS/DECISION-LOG.md](05-DECISIONS/DECISION-LOG.md).

---

## Sigma vs Zira — system vs experience layer

> `Sigma` and `Zira` are **not** synonyms; do not use "Zira / Sigma" as an interchangeable label. See [DECISION-LOG D-17](05-DECISIONS/DECISION-LOG.md).

### Sigma
The wider **system / capability ecosystem**: the domain and shared capabilities that establish trusted facts, computation, synthesis and reusable organizational capabilities — e.g. Operations Store, Geography / Spatial Intelligence, Context & Meaning, and shared capabilities.

### Zira
**Sigma's product / experience layer** for users. Zira contains the user-facing modules and experiences (current examples: **Commander Space**, **Operations Management**).

**Boundaries:**
- Operations Store, Geography / Spatial Intelligence, and Context & Meaning are **Sigma capabilities**, *not* Zira modules.
- Commander Space and Operations Management are **modules inside Zira**.
- Commander Space does **not** contain Operations Management.

---

## Naming — canonical terms and their aliases

### Commander Space
The current name of the user-facing **module inside Zira** for the personal/commander experience — awareness, attention, investigation, decision, action, relevant approvals, and knowledge continuity. It is **not** the whole Sigma experience layer (that is **Zira**) and does **not** contain every capability. Defined in PR-014. **This is the term to use.**

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
The **broader capability/concept**: translating trusted context into operationally relevant meaning. Concept paper: OM-004.

### Operational Signal
The **concrete, evidence-backed output of Context & Meaning**: *an evidence-backed statement of operational meaning produced by C&M.* It is **not** a raw event, a raw observation, or an uninterpreted data point — raw source events/observations remain distinct factual **inputs**.

> **Resolution (owner decision, see [DECISION-LOG D-19](05-DECISIONS/DECISION-LOG.md)):** the current authoritative definition of *Operational Signal* is the C&M evidence-backed statement above. The **legacy KB-001 definition** ("a raw observation, event, or data point … facts before interpretation") is **stale / superseded**. *Operational Signal* (concrete C&M output) and *Operational Meaning* (broader capability) remain **distinct** and are not used interchangeably.

---

## Geography — product capabilities and spatial outputs

### Geography product-capability model (current)
The current **product-level** capability model for Geography / Spatial Intelligence is **Spatialize · Resolve · Relate · Reconstruct · Qualify**. This is the **current product model — not historical.** It need not map 1:1 onto the lower-level spatial-operation enum exposed by the Geography technical contract; product capabilities and API operations are different abstraction levels. See [DECISION-LOG D-21](05-DECISIONS/DECISION-LOG.md).

### Spatial Evidence vs SpatialResult
- **Spatial Evidence** — the **product / business** abstraction: factual spatial evidence produced by Geography for consumption by Context & Meaning or another authorized consumer.
- **SpatialResult** — the **technical / contract** representation through which Geography returns that result.

These are two abstraction levels of the same thing, **not** competing/drifting terms.

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
