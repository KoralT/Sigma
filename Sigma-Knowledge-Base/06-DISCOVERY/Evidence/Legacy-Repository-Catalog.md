---
id: CAT-001
title: Repository Catalog
version: 1.0-draft
status: Working Draft
classification: Knowledge Architecture
owner: Sigma
last_updated: 2026-07-20
---

> **Migration note (2026-08-30):** Retained as historical evidence of the previous repository taxonomy. Knowledge status: **HISTORICAL**. It does not define V2 navigation or current architecture; its original content is unchanged. See `DOCUMENT-REGISTRY.md` for the current map.

# Repository Catalog

> **Purpose**
>
> This document defines the operational knowledge domains that organize Sigma's repositories.
>
> Rather than prescribing a fixed repository structure, it establishes the conceptual boundaries through which organizational knowledge is grouped, governed, and evolved.
>
> Repositories represent the primary organizational containers for Operational Assets and provide the knowledge foundation consumed by the Sigma Platform, Knowledge Graph, Artificial Intelligence, and Commander Space.

---

# Purpose

Operational organizations manage knowledge across multiple domains.

Each domain represents a distinct area of organizational understanding with its own concepts, relationships, governance requirements, and operational responsibilities.

The Repository Catalog defines these domains and provides the architectural framework through which organizational knowledge is organized.

Rather than maintaining one large repository of unrelated information, Sigma structures knowledge into coherent repositories that reflect how the organization understands and operates within its environment.

This approach improves discoverability, governance, semantic consistency, and long-term maintainability while enabling each repository to evolve independently without compromising the overall knowledge architecture.

---

# Model Status

The Repository Catalog is intentionally evolutionary.

The operational domains presented in this document represent Sigma's current understanding of the organization's knowledge landscape.

As operational discovery progresses, new repositories may emerge, existing repositories may expand, and repository boundaries may evolve.

The objective is to maintain a stable conceptual structure while allowing the knowledge architecture to mature alongside organizational understanding.

---

# Scope

This document defines:

- Operational knowledge domains.
- Repository classification.
- Repository boundaries.
- Repository definition principles.
- Repository specification standard.
- Relationships between repositories.
- Repository governance.

---

# Out of Scope

This document intentionally excludes:

- Entity definitions.
- Operational Asset definitions.
- Product-specific features.
- User interfaces.
- Storage technologies.
- Database schemas.
- Search implementation.
- Engineering implementation.

These concerns are defined in their respective architectural documents.

---

# References

- ARC-001 Sigma Reference Architecture
- OM-005 Operational Assets
- PA-009 Repository Architecture
- PA-010 Entity Model
- PR-017 Operational Repositories

---

# Contents

1. Operational Knowledge Domains

2. Repository Principles

3. Current Repository Landscape

4. Repository Specification Standard

5. Cross-Repository Relationships

6. Repository Governance

7. Catalog Evolution

---

# Part I – Operational Knowledge Domains

Sigma organizes organizational knowledge around operational domains rather than around systems, applications, or organizational departments.

Each domain represents a coherent body of operational understanding with clearly defined concepts, responsibilities, and relationships.

Repositories provide the persistent knowledge foundation for these domains, allowing organizational knowledge to be governed independently while remaining semantically connected through the Sigma Platform.

The current Sigma knowledge architecture focuses on four primary operational domains.

---

## Resources & Force Structure

This domain represents the organizational resources available for operational execution.

It includes personnel, organizational structures, equipment, capabilities, and force readiness.

This domain already exists within the organization and serves as one of the primary foundations for operational planning.

As Sigma evolves, this domain is expected to expand significantly through richer relationships, governance, and contextual understanding.

---

## Events & Reports

This domain captures the operational events occurring across the organization together with the reports, observations, and documented information describing those events.

It represents the organization's operational awareness and historical record.

This domain already exists today and serves as a critical source of operational evidence that supports situational understanding and future decision-making.

---

## Operations

This domain represents operational planning and execution.

It introduces organizational concepts such as missions, objectives, operational activities, dependencies, milestones, execution status, and operational outcomes.

Unlike the previous domains, Operations represents a new knowledge capability introduced by Sigma.

It provides the structured representation of operational intent and coordinated execution that enables Commander Space to support mission planning and operational readiness.

---

## Geography

This domain represents the operational environment in which activities occur.

It includes locations, operational areas, geographic relationships, terrain-related context, and spatial dependencies between operational entities.

Geography forms the contextual layer that connects resources, events, and operations into a shared operational picture.

This domain is also introduced as part of Sigma and becomes a foundational component of contextual understanding across the platform.

---

Together, these four operational domains establish the initial knowledge landscape of Sigma.

They provide the conceptual boundaries from which individual repositories, entities, Operational Assets, and future knowledge capabilities will evolve while remaining connected through a unified semantic architecture.
# Part II – Repository Principles

Repositories are the primary organizational containers through which Sigma manages operational knowledge.

Each repository represents a coherent body of knowledge that can evolve, be governed, and be consumed independently while remaining connected to the broader organizational context.

The objective of repository design is not to mirror organizational structures or existing information systems, but to reflect how the organization understands and reasons about its operational world.

---

## Domain-Driven Organization

Repositories are organized around operational domains rather than around departments, applications, or projects.

Each repository owns a well-defined area of knowledge with clear conceptual boundaries.

This approach enables knowledge to remain stable even as organizational structures, systems, or technologies evolve.

---

## Single Source of Truth

Each operational concept has a single authoritative repository.

Although information may be surfaced across multiple products and experiences, its ownership remains within one repository.

This principle minimizes duplication, improves governance, and ensures semantic consistency across the platform.

---

## Repository Independence

Repositories are autonomous knowledge components.

Each repository maintains its own lifecycle, governance processes, ownership, and evolution roadmap.

Changes within one repository should not require structural changes across unrelated repositories.

This independence enables incremental evolution of the knowledge architecture over time.

---

## Connected by Relationships

Repositories are not isolated.

Operational understanding emerges from the relationships between repositories rather than from the repositories themselves.

The Sigma Knowledge Graph provides the semantic layer that connects entities across repositories, allowing users and AI to reason across organizational domains without duplicating information.

---

## Knowledge Before Products

Repositories exist independently of any product experience.

Commander Space, Headquarters Workspace, Personal Workspace, Artificial Intelligence, analytics, and future products all consume the same underlying repositories.

Products present knowledge.

Repositories own knowledge.

---

## Evolutionary by Design

Repository boundaries are expected to evolve.

As organizational understanding matures, repositories may:

- expand,
- split into multiple repositories,
- merge,
- or introduce entirely new knowledge domains.

The Repository Catalog is therefore treated as an evolving architectural artifact rather than a fixed taxonomy.

---

## Governed Operational Assets

Repositories do not merely store data.

They govern Operational Assets.

Each Operational Asset maintains:

- identity,
- ownership,
- lifecycle,
- relationships,
- operational meaning,
- and contextual relevance.

This governance enables Sigma to build Trusted Context from reliable and explainable organizational knowledge.

---

## Repository Design Criteria

A new repository should only be introduced when it represents a distinct operational domain with:

- clear conceptual boundaries,
- independent governance,
- dedicated operational ownership,
- meaningful relationships to other domains,
- and long-term organizational value.

Repositories should never be created solely to reflect application boundaries, technical implementation details, or temporary organizational structures.
# Part III – Current Repository Landscape

The current Sigma knowledge architecture is centered around four operational domains.

Each domain represents a major area of organizational understanding and serves as the foundation for one or more repositories.

The repository landscape is expected to evolve as organizational discovery progresses. The repositories presented below represent Sigma's current architectural direction rather than a final implementation.

---

## Resources & Force Structure

**Domain Status:** Existing Domain (Expansion)

This domain represents the organization's operational resources and force structure.

It captures the people, organizational units, equipment, capabilities, readiness, and other operational resources required to execute missions.

Although this knowledge already exists within the organization, Sigma significantly expands its semantic richness by introducing structured relationships, lifecycle management, governance, and contextual understanding.

Potential repositories within this domain may include:

- Personnel Repository
- Organizational Structure Repository
- Equipment Repository
- Capabilities Repository
- Readiness Repository

The exact repository boundaries will be determined during domain discovery.

---

## Events & Reports

**Domain Status:** Existing Domain

This domain represents operational awareness.

It captures events occurring across the organization together with reports, observations, assessments, incident documentation, intelligence updates, and other forms of operational evidence.

This knowledge provides the historical and real-time evidence required to understand what has happened and what is currently happening.

Potential repositories may include:

- Events Repository
- Reports Repository
- Observations Repository
- Assessments Repository

As Sigma evolves, this domain becomes a primary source of evidence used to build Trusted Context.

---

## Operations

**Domain Status:** New Domain

Operations introduces a structured representation of operational planning and execution.

Unlike Events, which describe what happened, Operations represents what the organization intends to achieve.

This domain enables Sigma to model missions, operational objectives, planning activities, dependencies, execution progress, risks, approvals, and operational outcomes.

Potential repositories may include:

- Missions Repository
- Objectives Repository
- Operational Activities Repository
- Plans Repository
- Decision Repository

This domain becomes one of the central knowledge domains powering Commander Space.

---

## Geography

**Domain Status:** New Domain

Geography provides the spatial context required to interpret operational knowledge.

It captures locations, operational areas, facilities, regions, boundaries, infrastructure, terrain, and geographic relationships.

Rather than functioning as a mapping system, the Geography domain provides semantic understanding of the operational environment.

Potential repositories may include:

- Locations Repository
- Areas Repository
- Facilities Repository
- Geographic Relationships Repository

Every operational domain may reference geographic knowledge to establish contextual understanding.

---

# Repository Relationships

Although repositories are governed independently, they rarely operate in isolation.

Operational understanding emerges through relationships across domains.

Examples include:

- Missions consume Resources.
- Resources participate in Events.
- Events occur within Geographic Areas.
- Missions are executed within Geographic Areas.
- Reports describe Events.
- Decisions reference Missions, Resources, Events, and Geography.

These relationships are maintained by the Sigma Knowledge Graph, allowing organizational knowledge to remain distributed while being interpreted as a unified operational context.
# Part IV – Repository Specification Standard

Every repository within Sigma follows a common specification model.

The objective of this model is to ensure that repositories remain consistent in structure, governance, and interoperability regardless of the operational domain they represent.

Using a shared specification standard enables repositories to evolve independently while remaining compatible with the broader Sigma Knowledge Architecture.

Each repository specification should answer the following questions.

---

## 1. Repository Purpose

Why does this repository exist?

Describe the operational problem the repository solves and the organizational capability it enables.

The purpose should focus on operational value rather than technical implementation.

---

## 2. Domain Ownership

Which operational domain does the repository belong to?

Every repository belongs to exactly one primary operational domain.

Examples:

- Resources & Force Structure
- Events & Reports
- Operations
- Geography

---

## 3. Repository Scope

Define what knowledge belongs inside the repository.

Clearly identify:

- what is included,
- what is excluded,
- and where repository boundaries exist.

Repository boundaries should prevent duplication between repositories.

---

## 4. Core Operational Assets

Identify the primary Operational Assets governed by the repository.

Examples may include:

- Mission
- Event
- Report
- Location
- Equipment
- Personnel

Operational Assets are defined in OM-005 and represented through the Entity Model.

---

## 5. Relationships

Describe how repository assets relate to assets governed by other repositories.

Relationships should describe semantic dependencies rather than implementation details.

These relationships become part of the Sigma Knowledge Graph.

---

## 6. Consumers

Identify the organizational capabilities that consume repository knowledge.

Consumers may include:

- Commander Space
- Headquarters Workspace
- Personal Workspace
- Artificial Intelligence
- Analytics
- Future Sigma Products

Repositories are shared organizational capabilities and should not be designed for a single consumer.

---

## 7. Governance

Describe how repository knowledge is governed.

Governance should define:

- ownership,
- lifecycle,
- validation,
- stewardship,
- and quality expectations.

---

## 8. Evolution

Repositories are expected to evolve.

Each specification should identify anticipated areas of future expansion together with assumptions that remain subject to operational discovery.

Repository specifications should avoid prematurely fixing structures that are expected to mature over time.
# Part V – Cross-Repository Relationships

Operational knowledge is inherently interconnected.

Although repositories provide clear ownership boundaries, meaningful operational understanding emerges only through relationships that span multiple repositories.

Sigma deliberately separates knowledge ownership from knowledge interpretation.

Repositories own knowledge.

The Knowledge Graph connects knowledge.

Trusted Context interprets knowledge.

Artificial Intelligence reasons over knowledge.

Products present knowledge.

This layered approach enables organizational understanding without duplicating information across repositories.

---

## Relationship Principles

Cross-repository relationships should follow several architectural principles.

### Semantic Relationships

Relationships describe operational meaning rather than database references.

The Knowledge Graph represents concepts such as participation, dependency, ownership, location, sequence, and influence.

---

### No Knowledge Duplication

Repositories reference knowledge owned elsewhere.

Information should not be copied simply to support another operational capability.

---

### Shared Context

Multiple repositories contribute simultaneously to the construction of Trusted Context.

No single repository is expected to provide complete operational understanding in isolation.

---

### Evolution Without Coupling

Repositories may evolve independently provided that shared semantic relationships remain consistent.

This enables organizational knowledge to grow incrementally without creating unnecessary architectural dependencies.
Operational Domain
        ↓
Repository
        ↓
Operational Assets
        ↓
Entity Model
        ↓
Knowledge Graph
        ↓
Trusted Context
        ↓
AI
        ↓
Commander Space
# Part VI – Catalog Evolution & Governance

The Repository Catalog is a living architectural artifact.

It reflects Sigma's current understanding of the organization's operational knowledge and evolves alongside the organization itself.

The objective of the catalog is not to define a permanent repository structure, but to provide a stable conceptual framework that can accommodate organizational growth without compromising architectural consistency.

As new operational capabilities emerge, repositories may be introduced, refined, merged, or retired while preserving the integrity of the overall knowledge architecture.

---

## Repository Lifecycle

Repositories evolve throughout the lifecycle of the platform.

A repository may be:

- Introduced when a new operational domain is identified.
- Expanded as organizational understanding matures.
- Split into multiple repositories when knowledge complexity increases.
- Merged with another repository when boundaries prove artificial.
- Retired if the represented knowledge is no longer operationally relevant.

Repository evolution should be driven by operational needs rather than technical implementation.

---

## Introducing a New Repository

A new repository should only be created when all of the following conditions are met:

- It represents a distinct operational domain or sub-domain.
- It owns knowledge that cannot be naturally governed by an existing repository.
- It introduces long-term organizational value.
- It requires independent governance and lifecycle management.
- It contributes meaningful relationships to the Sigma Knowledge Graph.

Creating repositories to mirror applications, databases, organizational departments, or temporary projects should be avoided.

---

## Repository Ownership

Every repository must have a clearly defined owner.

Ownership includes responsibility for:

- Knowledge quality.
- Repository evolution.
- Operational governance.
- Semantic consistency.
- Lifecycle management.
- Cross-domain collaboration.

Ownership is organizational rather than technical.

---

## Architectural Consistency

All repositories should remain aligned with Sigma's architectural principles.

Specifically, repositories should:

- Govern Operational Assets.
- Avoid duplication of knowledge.
- Participate in the Knowledge Graph.
- Contribute to Trusted Context.
- Support explainable AI reasoning.
- Remain independent of product implementations.

This ensures that every repository strengthens the overall knowledge architecture instead of creating isolated knowledge silos.

---

## Continuous Discovery

The Repository Catalog is expected to evolve continuously through operational discovery.

User research, operational observations, workshops, prototype validation, and real-world usage may reveal:

- Missing repositories.
- Better repository boundaries.
- New operational concepts.
- Additional relationships.
- New governance requirements.

Repository discovery is therefore considered an ongoing architectural activity rather than a one-time design exercise.

---

# Summary

The Repository Catalog provides the organizational blueprint for Sigma's knowledge architecture.

By organizing knowledge into operational domains and governed repositories, Sigma establishes a scalable foundation for operational understanding, trusted context, artificial intelligence, and future product capabilities.

Rather than prescribing a fixed repository hierarchy, the catalog defines the principles through which organizational knowledge can evolve while remaining semantically consistent, explainable, and operationally meaningful.

As Sigma grows, the Repository Catalog will continue to mature alongside the organization, ensuring that new knowledge capabilities strengthen the platform without compromising architectural integrity.
# Appendix A – Initial Domain Roadmap

The following roadmap summarizes Sigma's current operational knowledge domains and their expected direction of evolution.

This roadmap is intended to guide future repository design and prioritization.

Repository definitions remain subject to operational discovery and may evolve as organizational understanding matures.

| Operational Domain | Current Organizational State | Sigma Direction | Expected Maturity |
|--------------------|------------------------------|-----------------|------------------|
| Resources & Force Structure | Existing | Expand semantic understanding, relationships and readiness | High |
| Events & Reports | Existing | Structure operational evidence and historical knowledge | High |
| Operations | New | Introduce mission planning, execution and operational coordination | Medium |
| Geography | New | Build shared spatial operational context | Medium |

---

# Appendix B – Repository Hierarchy

The repository hierarchy is intentionally layered.

Operational Domain

↓

Repository

↓

Operational Asset

↓

Entity

↓

Relationships

↓

Knowledge Graph

↓

Trusted Context

↓

Artificial Intelligence

↓

Product Experiences

This hierarchy provides a clear separation of responsibilities across Sigma's knowledge architecture.

Domains organize knowledge.

Repositories govern knowledge.

Operational Assets represent knowledge.

The Knowledge Graph connects knowledge.

Trusted Context interprets knowledge.

Artificial Intelligence reasons over knowledge.

Products consume knowledge.
