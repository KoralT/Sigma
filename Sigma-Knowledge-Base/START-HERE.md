# START HERE — Sigma Knowledge Base

> Entry point for a new Product Lead, Engineering Lead, or Architect.
> Read this first. It tells you what Sigma is, how the pieces fit, and — just as important — what you may **not** assume from a document simply existing.

---

## 1. What Sigma is

Sigma exists to help operational organizations make better decisions by turning fragmented information held in professional source systems into **shared, trusted operational understanding**, and delivering that understanding to commanders as awareness, decision, and action.

Sigma is not a single application. It is an organizational capability composed of domains, shared platform capabilities, and a commander-facing experience layer. It is intended to operate through shared principles, domain boundaries, and reusable capabilities. (The document that would formalize this operating model, OM-001, is currently an authoring shell — see [CURRENT-STATE.md](CURRENT-STATE.md).)

---

## 2. How the major pieces fit together

Sigma is organized around a single flow of meaning. **Preserve these ownership boundaries — do not collapse them to simplify structure:**

```
Professional Source Systems      own professional / source-of-record information
        │
        ▼
Domain truth & capabilities      Operations (operational state & truth),
                                 Geography / Spatial Intelligence (spatial information,
                                 computation, relationships, spatial evidence)
        │
        ▼
Context & Meaning                interprets across trusted information — meaning,
                                 relevance, relationships, change, and impact
        │
        ▼
Commander Space                  the experience / decision layer where relevant
                                 understanding becomes human awareness, decision, action
        │
        ▼
Human authority                  final operational decisions remain with people
```

Cutting across these layers are **Shared Capabilities** (Trusted Context, Operational Meaning, Decision Model, AI Foundation, Knowledge, Trust) that the domains and the experience layer consume rather than re-implement.

**Canonical naming:** the experience/product layer is **Commander Space**. Some newer documents say "Commander Experience" for the same layer — treat that as legacy terminology drift, not a separate product (see [GLOSSARY.md](GLOSSARY.md) and [05-DECISIONS/DECISION-LOG.md](05-DECISIONS/DECISION-LOG.md)).

---

## 3. Where current truth is maintained

- **[CURRENT-STATE.md](CURRENT-STATE.md)** — what is actually true about Sigma right now, based on repository evidence. Read this before assuming anything is built. It separates *defined/validated direction* from *delivered capability*.

## 4. Where canonical knowledge is maintained

- **[DOCUMENT-REGISTRY.md](DOCUMENT-REGISTRY.md)** — every knowledge document, its stable ID, current location, concept/domain, knowledge status, and canonical role where one is established. It also lists **unresolved canonical conflicts** openly.
- **[GLOSSARY.md](GLOSSARY.md)** — the shared vocabulary, including deprecated aliases and terms whose relationship is still unresolved.
- Domain and capability knowledge lives under its owning area (Operations, Geography, Context & Meaning, Commander Space, Shared Capabilities). The registry points to the current physical path of each.

## 5. Where decisions and evidence are maintained

- **[05-DECISIONS/DECISION-LOG.md](05-DECISIONS/DECISION-LOG.md)** — owner decisions taken during the knowledge-base refactor (naming, authority, scope), with rationale and implications.
- Architecture Decision Records live **with their domain** (e.g. the Context & Meaning and Geography ADRs) and are indexed from the decision log. An ADR is created only when a real architectural/product decision was made — not to record every terminology cleanup.
- Prior review evidence (e.g. the KB accuracy review) is kept as **evidence**, not as current direction.

---

## 6. How to navigate the repository

The navigation-first V2 structure is now in place:

- `01-FOUNDATIONS/` — Platform Architecture, One Delivery (Doctrine/Operating Model/Product Portfolio remain shells under legacy `DOC/`, `OM/`, `PR/`).
- `02-DOMAINS/` — `Operations/`, `Geography/`, `Context-and-Meaning/` (each with a `README.md`).
- `03-EXPERIENCE/Commander-Space/` — `Commander-Space.md`, `Headquarters/`, `My-Space/`.
- `04-SHARED-CAPABILITIES/` — Operational-Meaning, Trusted-Context, Decision-Model, AI, Knowledge (Operational Assets, Entity Model), Trust, Actionable-Experience.
- `05-DECISIONS/`, `06-DISCOVERY/`, `07-EXECUTION/`, `99-ARCHIVE/`.

A few legacy folders remain by design: `DOC/`, `OM/`, `PR/`, `RS/` hold authoring **shells** not yet rebuilt; `KB/` holds the legacy guide/glossary; `Operations-Store/` still holds the **`.docx` Operations Store package pending conversion (Batch 2B)**. Use the **DOCUMENT-REGISTRY** as the map of record — every `Current Path` there is the real physical path. Do not rely on folder location alone.

Document **IDs are stable identifiers for traceability** (OM-006, PR-014, PA-011, …). Folders and filenames are for human navigation. When an ID and a location disagree, the registry is authoritative.

---

## 7. What NOT to infer from a document existing

Read this carefully — it is the most common way to be misled by this repository:

- **A document existing does not mean the capability is built.** Strategy, PRD, HLD, ADR, and target-state documents describe intended or approved *direction*, not delivered software. Delivery status is tracked only in CURRENT-STATE, and only where evidence exists.
- **"Foundational" classification does not mean the content is complete.** Several foundational documents (Doctrine, Operating Model, Product Portfolio, Discovery) are currently **authoring shells** with placeholder sections. They carry no canonical authority until written.
- **Newer does not automatically override older, and older does not automatically win by being "foundational."** Layer A (doctrine/operating-model/platform/product/research) and Layer B (current domain/engineering material) **coexist with unequal authority**: current approved domain decisions take precedence where the content supports them; placeholder foundational docs do not.
- **Similar names are not proof of the same concept.** "Operations Store", "Operations Repository", and "Operational Repositories" are kept **separate** pending semantic reconciliation. Likewise, "Operational Meaning" (a capability) and "Operational Signal" (a Context & Meaning output/contract) are **not** synonyms.
- **`ARC-001` does not exist and will not be created.** Older documents reference it as an entry architecture; that role is now served by this file, the Platform Architecture document, and the registry.

When in doubt, check the registry for the document's knowledge status and canonical role, and check CURRENT-STATE for whether anything is actually delivered.
