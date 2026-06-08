---
layout:
  width: default
  title:
    visible: false
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
metaLinks:
  alternates:
    - https://app.gitbook.com/s/dU03bcgqfvodP4msaMaL/
---

# GovStack Architecture

<figure><img src=".gitbook/assets/image (9).png" alt="" width="375"><figcaption></figcaption></figure>

#### Abstract

Architecture Specification defines the structural and technical constraints and decisions that shape a system's overall design to achieve technical **interoperability**: the ability for different autonomous systems and Building Blocks to collaborate and provide an ecosystem of value.&#x20;

> At its core, interoperability means that technical systems can speak and understand the same language and follow the same principles - so that the ecosystem they form is sustainable over the long term and flexible enough to change and expand as needs grow.

In practice, an architecture specification includes technology choices, integration patterns, deployment strategies, scalability models and rules for how components interact. It guides the system's evolution, ensures consistency across modules and aligns the technical foundation with organizational strategy - often serving as a contract between development and operations.

GovStack Architecture Specification is primarily targeted for public sector and digital government transformation, but the principles and requirements apply for design of any kind of digital ecosystem, including in the private sector. The reason this specification exists is straightforward: without shared architectural rules, government digital services end up with point-to-point dependencies between systems, duplicated capabilities across agencies and growing vendor lock-in. Interoperability is not only a technical integration problem. It requires consistent architecture principles, explicit interface contracts and cross-functional requirements that hold across every component in the ecosystem.

This document covers five areas. Common Terminology establishes a shared language across all GovStack specifications. Nine Architecture Principles define the design posture: openness, modularity, interoperability, sustainability, security, data ownership, user-centered design, API-first access and reusability. Building Block Architecture describes how systems are composed from loosely coupled, autonomous components - including the role of the Information Mediator for secure cross-boundary data exchange. The Specification Framework defines how Building Block specifications are identified, versioned, classified and extended, creating a stable foundation for compliance, procurement and marketplace operations through GovMarket. Cross-Functional Requirements - covering development, deployment, architecture, quality, security and data - specify the operational qualities that every Building Block must meet, from transport security and container packaging to observability, backup and access control.

Cross-functional requirements deserve particular attention. Historically called both cross-cutting requirements and often known as non-functional requirements, these qualities - availability, performance, security, usability and maintainability - directly determine whether a government service works reliably for citizens and civil servants. They are not secondary to business logic. They shape how systems behave under real conditions and how they are perceived by the people who depend on them. This specification treats cross-functional requirements as first-class, testable obligations that span across services and systems.

This specification has been created by an international community of experts with experience primarily from the public sector. Specification development has been led by Kristo Vaher, a computer scientist with an MSc in E-Governance Technologies and Services and former government CTO for the Republic of Estonia.

_Compliance with this specification is mandatory for all projects that apply GovStack principles or aim to create compliant software solutions. This specification is also mandatory for solutions offered on GovMarket._

#### Background

GovStack architecture specification has been developed in accordance to GovSpecs 2.0 Strategy, which is available here: [https://govstack.global/news/govspecs-2-0-strategy-2025-2027-a-blueprint-for-future-ready-digital-public-services/](https://govstack.global/news/govspecs-2-0-strategy-2025-2027-a-blueprint-for-future-ready-digital-public-services/)
