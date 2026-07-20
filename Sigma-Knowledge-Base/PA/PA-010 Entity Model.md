---
id: PA-010
title: Entity Model
version: 1.0-draft
status: Working Draft
classification: Platform Architecture
owner: Sigma
last_updated: 2026-07-20
parent: PA-001
---

# Entity Model

> **Purpose**
>
> This document defines the conceptual entities that form Sigma's operational knowledge model.
>
> Rather than describing database structures or implementation details, it establishes the common language used throughout the Sigma Platform, Operational Repositories, Commander Space, and AI capabilities.
>
> Every operational concept referenced across the Sigma Knowledge Base is formally defined through this model.

---

# Purpose

Operational organizations rely upon a shared understanding of their environment.

That understanding can only remain consistent when every product, service, workflow, and intelligent capability interprets organizational concepts in the same way.

The Entity Model provides this common semantic foundation.

It defines the conceptual entities, relationship principles, and governance model that collectively describe Sigma's operational domain.

Rather than serving as a database model, the Entity Model defines the language through which Sigma represents organizational reality.

---

# Model Status

The Sigma Entity Model is intentionally evolutionary.

Rather than defining a fixed and exhaustive catalog of entities, this document establishes the semantic principles used to model operational concepts across the Sigma ecosystem.

The entities presented here represent the organization's current shared understanding of the operational domain. As discovery progresses, new concepts, distinctions, and relationships are expected to emerge.

The introduction of new entities should extend the model rather than invalidate its existing semantics.

This approach allows the Entity Model to evolve alongside operational understanding while preserving consistency across the Sigma Platform, Operational Repositories, Commander Space, and future Sigma products.

---

# Scope

This document defines:

- Conceptual entity model
- Entity families
- Current entity catalog
- Relationship principles
- Entity definition standard
- Entity evolution
- Entity governance

---

# Out of Scope

This document intentionally excludes:

- Database schemas
- API contracts
- Storage technologies
- UI representations
- Engineering implementation
- Product workflows

These concerns belong to implementation and product-specific architecture rather than Sigma's conceptual model.

---

# References

- ARC-001 Sigma Reference Architecture
- OM-005 Operational Assets
- PA-008 Knowledge Graph
- PA-009 Repository Architecture
- PR-017 Operational Repositories

---

# Contents

1. Conceptual Entity Model

2. Entity Families

3. Current Entity Catalog

4. Relationship Model

5. Entity Definition Standard

6. Discovery and Model Evolution

7. Entity Governance

---

# Part I – Conceptual Entity Model

Operational organizations continuously reason about real-world concepts.

Objectives.

Activities.

Decisions.

People.

Resources.

Knowledge.

Rather than modeling software objects, Sigma models these operational concepts directly.

An entity represents a meaningful concept that exists within the operational domain independently of any specific application, database, or user interface.

Entities establish the shared semantic language consumed throughout the Sigma ecosystem.

Commander Space.

Operational Repositories.

AI capabilities.

Platform services.

All reason about the same conceptual entities.

This separation ensures that organizational understanding remains stable even as products and technologies evolve.

---

## Why Entities

Without a shared semantic model, different systems interpret the same operational concepts differently.

The Entity Model eliminates this ambiguity by establishing one common vocabulary for the organization.

Every operational capability references the same conceptual definitions, ensuring consistent interpretation across products, services, workflows, and AI capabilities.

---

## Entity Principles

Every Sigma entity follows the same architectural principles.

### Represents a Real Operational Concept

Entities model organizational reality rather than software constructs.

---

### Has Operational Meaning

Every entity contributes to organizational understanding.

---

### Exists Within Context

Entities derive meaning from their relationships with other entities.

---

### Evolves Over Time

Entities reflect changes in operational reality while preserving continuity.

---

### Can Be Governed

Every entity may possess ownership, lifecycle, metadata, governance, and relationships.

---

### Contributes to Trusted Context

Collectively, entities establish the Trusted Context consumed throughout the Sigma ecosystem.

---

# Part II – Entity Families

Operational entities are organized into conceptual families.

These families provide a stable organizational structure while allowing the model itself to evolve through discovery.

Individual entities may be introduced, refined, or deprecated over time without requiring changes to the overall semantic architecture.

The families represent enduring categories of operational concepts rather than fixed lists of entities.

---

## Direction Entities

Represent organizational intent and desired outcomes.

Examples include:

- Objective
- Mission
- Priority
- Constraint

---

## Execution Entities

Represent operational work and coordination.

Examples include:

- Activity
- Task
- Dependency
- Milestone

---

## Decision Entities

Represent organizational reasoning and decision-making.

Examples include:

- Decision
- Alternative
- Approval
- Evidence

---

## Organizational Entities

Represent people and organizational structures.

Examples include:

- Person
- Role
- Team
- Organizational Unit

---

## Knowledge Entities

Represent reusable organizational knowledge.

Examples include:

- Operational Asset
- Observation
- Procedure
- Lesson Learned

---

## Assessment Entities

Represent evaluation of operational conditions.

Examples include:

- Readiness
- Risk
- Issue
- Gap

---

## Context Entities

Represent the operational environment.

Examples include:

- Location
- Event
- Time Window
- Operational State

---

## Resource Entities

Represent capabilities required to execute operational work.

Examples include:

- Resource
- Capability
- System
- Equipment

---

The families above are not exhaustive.

Additional entity families may emerge through discovery, product evolution, and changes in organizational needs.

The semantic structure should remain stable while allowing the model itself to grow.

---

# Part III – Current Entity Catalog

The Entity Catalog represents Sigma's current understanding of the operational domain.

It is intentionally non-exhaustive and is expected to evolve over time.

Each entity listed within the catalog should follow the common definition standard described in this document.

The catalog serves as the authoritative inventory of conceptual entities currently recognized by the Sigma Platform.

New entities should be introduced only when they represent meaningful operational concepts that cannot be adequately expressed through existing entities.

---

# Part IV – Relationship Model

Entities do not exist independently.

Operational understanding emerges from the relationships that connect entities into a coherent knowledge network.

Relationships describe how entities influence, support, depend upon, or provide context for one another.

Rather than relying on hierarchical structures, Sigma represents organizational knowledge as an interconnected semantic graph.

Relationship definitions remain independent of storage technology or implementation.

Every relationship should strengthen organizational understanding, traceability, and explainability.

---

## Relationship Principles

Relationships should:

- Connect meaningful operational concepts.
- Be semantically explicit.
- Support bidirectional understanding where appropriate.
- Preserve traceability.
- Enable contextual navigation.
- Strengthen Trusted Context.

---

# Part V – Entity Definition Standard

Every entity introduced into Sigma should be documented consistently.

Each entity definition should include:

- Name
- Purpose
- Description
- Entity Family
- Responsibilities
- Typical Relationships
- Lifecycle Considerations
- Governance Considerations
- Representative Examples

This standard ensures that new entities remain understandable and consistent across the Sigma ecosystem.

---

# Part VI – Discovery and Model Evolution

The Entity Model is expected to evolve continuously.

Operational discovery may reveal:

- new operational concepts,
- missing distinctions,
- additional relationships,
- refinements to existing semantics.

Evolution should preserve backward conceptual compatibility whenever possible.

Changes should extend the model rather than redefine existing concepts unless supported by significant architectural justification.

The objective is to maintain a stable semantic foundation while continuously improving the organization's representation of operational reality.

---

# Part VII – Entity Governance

Entity governance ensures that Sigma maintains one authoritative conceptual language.

Governance responsibilities include:

- approving new entity types,
- preventing duplicate concepts,
- preserving semantic consistency,
- documenting relationships,
- maintaining naming conventions,
- reviewing conceptual changes,
- aligning entities across Platform, Products, AI, and Operational Repositories.

The Entity Model should remain the single source of truth for operational concepts across the Sigma ecosystem.

---

# Summary

The Sigma Entity Model defines the shared semantic language used throughout the platform.

Rather than prescribing implementation details, it establishes the conceptual entities, relationship principles, and governance framework through which Sigma represents organizational reality.

The model is intentionally evolutionary.

It provides a stable architectural foundation while allowing new operational concepts to emerge through discovery, organizational learning, and product evolution without compromising semantic consistency.
