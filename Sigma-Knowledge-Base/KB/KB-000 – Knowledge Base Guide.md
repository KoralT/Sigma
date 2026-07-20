---
id: KB-000
title: Sigma Knowledge Base Guide
version: 1.0
status: Draft
classification: Foundational
owner: Sigma
last_updated: 2026-07-20
---

# Sigma Knowledge Base Guide

## Purpose

The Sigma Knowledge Base Guide defines the structure, organization, and governance of the Sigma Knowledge Base.

Its purpose is to ensure that every document follows a consistent structure, every concept has a single authoritative source, and the knowledge base evolves in a maintainable and scalable manner.

This document defines how the documentation system operates—not Sigma itself.

---

## Audience

This guide is intended for anyone authoring, reviewing, or maintaining Sigma documentation.

---

## Scope

This document defines:

- Knowledge Base structure
- Document hierarchy
- Document ownership
- Document relationships
- Writing principles
- Governance rules
- Naming conventions
- Versioning principles

---

## Out of Scope

This document does not define Sigma's operating model, products, architecture, or strategy.

Those topics are documented in their respective knowledge domains.

---

# Knowledge Base Structure

The Sigma Knowledge Base is organized into independent knowledge domains.

Each domain owns a distinct area of knowledge and acts as the single source of truth for that domain.

```
KB
?
??? DOC – Doctrine
??? OM – Operating Model
??? PA – Platform Architecture
??? PR – Product
??? RS – Research
```

---

# Document Hierarchy

Knowledge flows from abstract concepts toward implementation.

```
Doctrine
        ?
Operating Model
        ?
Platform Architecture
        ?
Products
        ?
Implementation
```

Documents may reference lower layers but must never redefine them.

---

# Single Source of Truth

Every concept within Sigma must have exactly one authoritative definition.

Documents may reference concepts defined elsewhere but must never redefine them.

If a concept requires modification, the owning document must be updated rather than duplicating the definition.

---

# Writing Principles

Every document must:

- Answer one primary question.
- Define one area of responsibility.
- Avoid implementation details unless explicitly within scope.
- Reference other documents instead of duplicating knowledge.
- Remain understandable independently.
- Remain stable over time.

---

# Knowledge Domains

| Domain | Responsibility |
|---------|----------------|
| KB | Documentation governance |
| DOC | Strategic doctrine |
| OM | Operating model |
| PA | Platform architecture |
| PR | Product landscape |
| RS | Discovery and research |

---

# Document Relationships

Documents should reference one another through dependencies rather than duplication.

Knowledge always flows downward.

Changes should be introduced at the highest appropriate level.

---

# Naming Convention

Every document follows:

```
<ID> – <Title>
```

Example:

```
DOC-001 Sigma Doctrine

OM-004 Operational Meaning

PA-007 Context Engine
```

---

# Versioning

Major versions indicate conceptual changes.

Minor versions indicate additions or clarifications.

Editorial corrections do not require conceptual version changes.

---

# Governance

The Knowledge Base is maintained according to four principles:

1. One concept ? One owner.
2. One document ? One responsibility.
3. Reference instead of duplication.
4. Stable documents over implementation details.
