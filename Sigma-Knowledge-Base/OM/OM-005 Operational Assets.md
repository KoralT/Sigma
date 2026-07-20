---
id: OM-005
title: Operational Assets
version: 1.0-draft
status: Working Draft
classification: Domain Paper
owner: Sigma
last_updated: 2026-07-20
---

# Operational Assets

> **Domain Thesis**
>
> Organizations do not operate on information. They operate on operational assets that carry persistent meaning, ownership, relationships, and value across time.

# Executive Summary

Sigma does not manage information. It manages Operational Assets.

An Operational Asset is any persistent organizational object that contributes to operational understanding or decision-making. Unlike raw information, Operational Assets have identity, ownership, lifecycle, governance, and relationships.

Operational Assets provide the durable foundation upon which Sigma builds shared operational understanding.

---

# Purpose

This paper defines the concept of Operational Assets within Sigma.

It explains:

- What qualifies as an Operational Asset.
- Why Sigma manages assets rather than information.
- The characteristics shared by all assets.
- The lifecycle and governance of Operational Assets.
- Their role across the Sigma platform.

---

# Part I – The Problem

## Information Is Not Enough

Operational organizations generate vast amounts of information every day.

Reports, messages, alerts, documents, sensor readings, approvals, and conversations all describe operational reality.

Most of this information is transient.

Very little of it becomes organizational knowledge.

Sigma therefore distinguishes between information and Operational Assets.

## Information vs. Operational Assets

Information is produced continuously.

Operational Assets persist.

Information answers immediate questions.

Operational Assets retain organizational value across multiple operational situations.

Examples:

| Information | Operational Asset |
|-------------|-------------------|
| GPS Coordinate | Strategic Location |
| Message | Validated Operational Meaning |
| Report | Approved Operational Plan |
| Observation | Operational Procedure |
| Approval | Organizational Policy |

---

# Why Operational Assets Matter

Organizations repeatedly solve similar problems.

Without reusable assets, knowledge is recreated rather than reused.

Operational Assets preserve organizational experience and reduce dependency on individual memory.

---

# Part II – Operational Asset Theory

## Definition

An Operational Asset is a persistent organizational object that carries operational value and can be reused across multiple operational situations.

Operational Assets are:

- Persistent
- Governed
- Explainable
- Reusable
- Traceable
- Versioned

## Characteristics

Every Operational Asset possesses:

- Identity
- Owner
- Lifecycle
- Relationships
- Business meaning
- Governance
- Version history

Without these characteristics, information remains transient rather than becoming an organizational asset.

---

# Operational Asset Taxonomy

## Knowledge Assets

- Operational Meanings
- Playbooks
- Procedures
- Lessons Learned

## Operational Assets

- Missions
- Objectives
- Tasks
- Resources
- Plans

## Structural Assets

- Entities
- Organizations
- Locations
- Relationships

## Decision Assets

- Policies
- Constraints
- Business Rules
- Approval Rules

## Experience Assets

- Templates
- Workflow Definitions
- Experience Components

---

# Asset Identity

Every Operational Asset must be uniquely identifiable.

Identity enables:

- Traceability
- Ownership
- Reuse
- Governance
- Historical analysis

Identity separates an organizational asset from an isolated piece of information.

---

# Asset Relationships

Operational Assets derive value from their relationships.

Example:

Mission
?
Objective
?
Task
?
Resource
?
Operational Meaning

Sigma manages this connected network rather than isolated records.

---

# Part III – Operational Properties

## Lifecycle

Creation
?
Validation
?
Publication
?
Consumption
?
Evolution
?
Versioning
?
Retirement

### Creation

An Operational Asset is introduced into the organization.

### Validation

Business ownership confirms its correctness.

### Publication

The asset becomes available for operational use.

### Consumption

Products, workflows, and users consume the asset.

### Evolution

The asset changes as organizational knowledge evolves.

### Versioning

Previous states remain traceable.

### Retirement

Assets no longer relevant are archived while preserving history.

---

# Design Principles

Operational Assets should always be:

## Persistent

Knowledge should survive individual events.

## Reusable

Assets should support multiple operational situations.

## Explainable

Users should understand an asset's operational purpose.

## Governed

Every asset requires clear ownership.

## Connected

Assets derive value through relationships.

## Versioned

History should never be lost.

## Discoverable

Assets should be searchable and reusable.

## Product Independent

Assets should outlive individual applications.

---

# Governance

Operational Assets require governance to preserve trust.

Governance includes:

- Business ownership
- Stewardship
- Review cadence
- Validation criteria
- Change management
- Retirement policy

---

# Counterarguments

## Isn't this Master Data?

No.

Master Data focuses on canonical business entities.

Operational Assets include knowledge, meaning, policies, operational structures, and reusable organizational intelligence.

## Isn't this just a database?

No.

Databases store records.

Sigma governs reusable organizational assets.

## Isn't every document an asset?

No.

Only information with persistent operational value becomes an Operational Asset.

---

# Operational Scenarios

## Military Operations

Mission plans, force structures, operational procedures, and validated lessons become reusable assets.

## Healthcare

Clinical protocols, treatment pathways, and diagnostic guidance become organizational assets.

## Cyber Security

Threat intelligence, response playbooks, and detection rules become reusable assets.

## Logistics

Transportation constraints, supplier knowledge, and routing procedures become operational assets.

---

# Implications

## Architecture

Platform architecture should be asset-centric rather than document-centric.

Operational capabilities should operate on reusable assets instead of isolated records.

## Product

Products should create, consume, enrich, and govern Operational Assets.

No product should maintain its own competing representation of organizational knowledge.

## Governance

Operational Assets require explicit ownership and lifecycle management.

---

# Relationship to Sigma

Operational Signals
?
Operational Meaning

Operational Assets
???????????????
(Persistent organizational foundation)

Trusted Context
?
Actionable Experience

Operational Assets provide the reusable foundation upon which higher-level Sigma capabilities operate.

---

# Key Takeaways

- Sigma manages Operational Assets rather than raw information.
- Operational Assets preserve organizational knowledge.
- Every asset has identity, ownership, governance, and lifecycle.
- Assets are reusable across operational situations.
- Operational Assets form the persistent foundation of the Sigma platform.

# Transition

Operational Assets preserve organizational knowledge over time.

The next paper explains how Sigma dynamically assembles relevant Operational Assets and Operational Meanings into a Trusted Context for decision support.

