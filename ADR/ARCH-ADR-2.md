---
title: Shape of the Cross-Functional Requirements publication
status: proposed
date: 2026-09-21
decision-makers:
  - Architecture Committee
consulted:
  - Architecture Working Group
  - GovStack Technical Committee
informed:
  - All Working Groups
  - GovMarket
---
<!-- markdownlint-disable-next-line MD025 -->
# Shape of the Cross-Functional Requirements publication

## Context and Problem Statement

[ARCH-ADR-1](./ARCH-ADR-1.md) introduced Reference Architectures as a publication concept.
Work following from it proposes separating the current `cfr-architecture` repository into
distinct publications, because it presently holds material of two different kinds: an
architecture description (chapters 2, 3 and 4, which contain no normative provisions) and a
requirements specification (chapter 6, which contains 19 REQUIRED and 59 RECOMMENDED
requirements).

Separating them raises a question the current single repository never had to answer: **is
GovStack Cross-Functional Requirements one publication, or a series of publications?**

Chapter 6 already divides into six domains: development, deployment, architecture, quality,
security and data. Each reads as a self-contained body of requirements.

| Domain | REQUIRED | RECOMMENDED |
|---|---|---|
| 6.1 development | 2 | 7 |
| 6.2 deployment | 3 | 9 |
| 6.3 architecture | 3 | 16 |
| 6.4 quality | 2 | 6 |
| 6.5 security | 6 | 10 |
| 6.6 data | 3 | 11 |

The question is not academic. It determines what `extends` resolves to in every Building
Block specification, what GovMarket assesses a solution against, whether the six domains can
be revised on independent cadences, and how an individual cross-functional requirement is
cited from outside GovStack.

### What is already decided

Two positions are already published and would be reversed, not merely extended, by some of
the options below.

Chapter 6.2, *Referring to GovStack core cross-functional requirements*, states:

> Since Building Block specifications need to refer to these cross-functional requirements
> […] GovStack CFR can be universally referred to as **govstack-cfr** […] or when referring
> to a specific version: **govstack-cfr-2.0.0**.
>
> *Sub-categories of GovStack CFR (such as govstack-cfr-data) do not have an individual
> version.*

Chapter 6.1, *"Object-oriented" specifications*, states that every Building Block
specification extends the cross-functional requirements "much like a class extends a base
class", inheriting all of them and being unable to contradict or weaken them.

Any option that gives the six domains individual versions contradicts the first of these
directly, and complicates the second.

## Decision Drivers

* **Inheritance arity.** `extends` is currently singular and all-or-nothing: a Building Block
  inherits every core requirement, never a subset. Does the publication shape preserve that?
* **Version skew.** Can a state arise in which a Building Block is assessed against
  `cfr-security` at one version and `cfr-data` at another, and if so, can GovMarket resolve
  what a solution was actually assessed against?
* **Revision cadence.** Security requirements plausibly need revision more often than
  development requirements. Should a security revision compel a release of all six domains?
* **Governance coupling.** Coupling the six domains forces every change through one
  Architecture Working Group agreement. This is a cost if the goal is velocity and a
  **benefit** if the goal is coherence of the baseline. The Committee should decide which it
  intends, because the publication shape will enforce it either way.
* **Citability of an individual requirement.** A procurement document must be able to cite one
  cross-functional requirement stably and have it resolve years later.
* **Weight of a publication.** A standalone publication carries a lifecycle: proposal, draft,
  release candidate, publication, obsoleting, reviewers, a version history. Six of them is six
  lifecycles. The Committee should judge whether each domain warrants that.

## Considered Options

* **Option 1: Single publication.** `govstack:spec:cfr`, one version, six domain chapters.
* **Option 2: Multipart with a shared edition.** Six separately addressable parts that are
  released together under one edition number.
* **Option 3: Independent series.** Six publications, each with its own version and cadence.

## Decision Outcome

Chosen option: **Option 1: Single publication**.

GovStack Cross-Functional Requirements is one publication, `govstack:spec:cfr`, carrying one
version and six domain chapters. This preserves the already-published position of chapter 6.2
and the object-oriented inheritance model of chapter 6.1 without reversal.

The citability concern that motivated the alternatives is resolved by remedy (a) of
*Separable concerns* below rather than by splitting the publication: **an individual
cross-functional requirement is identified by a domain-qualified fragment**, of the form

> `govstack:spec:cfr#<domain>-req-<N>`

for example `govstack:spec:cfr#data-req-3`. The domain is recoverable from the identifier, and
the publication remains one publication.

### Consequences

* Building Block specifications continue to declare a single `extends govstack-cfr-<version>`.
  Inheritance remains singular and all-or-nothing, as chapter 6.1 describes.
* Version skew between domains is not expressible. GovMarket retains one version-pinned
  compliance target, and "100% of REQUIRED requirements of govstack-cfr" continues to name a
  single thing.
* Chapter 6.2 is confirmed rather than amended. It SHOULD be extended to document the
  requirement identifier form, which it does not presently cover.
* A revision to any one domain produces a minor version of the whole publication. All six
  domains therefore remain coupled to a single Architecture Working Group agreement. The
  Committee accepts this coupling as a benefit to baseline coherence rather than a cost to
  velocity.
* Cross-functional requirement identifiers take a different fragment form from Building Block
  functional requirements, which use `#req-<N>`. This partially answers the open question in
  `proposals/requirement-id-scheme.md` as to whether cross-functional requirements share the
  functional requirement identifier space: they do not.
* Per-domain machine-readable compliance artifacts stay available, one requirements manifest and
  one test suite per domain. Artifact granularity is a tooling concern, and publication
  granularity does not constrain it.
* The six domains remain chapters. They are addressable but are not publications, and MUST NOT
  be assigned individual versions.

#### Scope of the identifier

`N` is allocated **per domain**. It restarts in each of the six domains, so
`govstack:spec:cfr#data-req-3` and `govstack:spec:cfr#security-req-3` are distinct and both
valid. Uniqueness is scoped to the pair (publication, domain), and the domain segment is part
of the key rather than a description of it.

Consequences of this scoping:

* The allocator maintains six high-water marks rather than one, or derives them per chapter
  from history. Adding a requirement to one domain never disturbs the numbering of another.
* The never-reuse rule applies per domain: a retired identifier is frozen as `DEPRECATED`
  within its domain and is never reassigned.
* **Moving a requirement between domains is prohibited**, because it would change the
  requirement's identifier and so break external references. Where a requirement is found to
  sit in the wrong domain, it is deprecated in place and reissued under a new identifier in the
  correct domain, with the deprecated entry recording the successor.

### Confirmation

Decision recorded 2026-09-21, pending ratification by the Architecture Committee following
Architecture Working Group discussion. The outcome is implemented in
`spec/6-cross-functional-requirements/README.md` §6.2, in
`meta-specification/chapters/govstack_namespaces.md`, and in the `extends` declaration
documented for Building Block specifications.

## Separable concerns

Two concerns raised in discussion appear to argue for a series, but are in fact independent
of publication shape. The Committee should decide them separately, so that they do not
distort the shape decision.

### The rationale for cross-functional requirements

**Resolved 2026-09-21.** ISO/IEC/IEEE 29148 gives an SRS informative clauses alongside its
requirements clauses: Purpose, Scope, Product perspective, Product functions, User
characteristics, Limitations. Clause 9.6.6 says user characteristics are described "to state the
reasons why certain specific requirements are later specified", not to state requirements. A
specification carries explanatory content by design.

The publication class records what a publication is *assessed against*. It says nothing about
whether every clause within that publication is normative. `govstack:spec:cfr` may therefore
carry the explanatory material serving its own requirements, which dissolves most of the concern.
One piece sits in the wrong place:

| Content | Home | Reason |
|---|---|---|
| The Fowler and Newman rationale; the principle that a choice with no impact on business function must never be a requirement | Stays in `govstack:spec:cfr` | SRS Purpose and Scope |
| §6.2, referring to `govstack-cfr`, and the requirement identifier form | Stays in `govstack:spec:cfr` | Self-referential: how to cite this document |
| §6.1, inheritance described: a Building Block specification extends the baseline as a class extends a base class | Stays in `govstack:spec:cfr` | A reader of the baseline needs it to understand the document's role |
| §6.1, the rule that Building Blocks must not copy-paste core specifications | **Moves to `govstack:core:specification-framework`** | A rule governing how specifications are authored; its conformance subject is documents, not software |
| 4.1.3, *Where GovStack Specifications Sit* | Stays in `govstack:arch:architecture` | Positions the baseline within the interoperability maturity model |

The original framing of this concern is retained below for the record.

#### Original framing

Chapter 6's introductory material is explanatory rather than normative: the Fowler and Newman
argument for the term, the principle that a choice with no impact on business function must
never be a requirement, and §6.1's object-oriented account of inheritance. Chapter 4.1.3,
*Where GovStack Specifications Sit*, carries related explanatory content:

> **Protocol Interoperability** — addressed by GovStack cross-functional requirements
> (govstack-cfr): transport security, data formats, API design, deployment, observability and
> security baselines.

Under [ARCH-ADR-1](./ARCH-ADR-1.md) and the publication-class model, explanatory content of
this kind belongs in the Reference Architecture class rather than in a requirements
specification. Three placements are available, and **none of them depends on whether CFR is
one publication or six**:

* **(a) A standalone `govstack:arch:cfr`.** Coherent, but the material presently amounts to
  roughly one page. A publication lifecycle for one page is likely disproportionate.
* **(b) An introduction chapter of `govstack:spec:cfr`.** Status quo. Mixes informative and
  normative content in one publication, which the class model otherwise avoids.
* **(c) A section of `govstack:arch:govstack`.** The Architecture publication already hosts
  the sibling text at 4.1.3. This placement puts the rationale beside the interoperability
  maturity model it explains, with no new publication.

Placement (c) is recommended. The Committee may wish to record this as a separate decision.

### Citing an individual cross-functional requirement

The requirement identifier scheme under discussion is `publication_identifier#req-N`, for example
`govstack:bb:wallet#req-7`. It lists as an open question whether cross-functional requirements
share that identifier space.

Under Option 1, a naive application yields `govstack:spec:cfr#req-12`, where no reader can
recover the domain from the identifier. The defect is real, and it belongs to the **identifier
scheme** rather than to the publication shape. At least three remedies leave the publication
intact:

* a domain segment in the fragment: `govstack:spec:cfr#data-req-3`;
* a domain-qualified identifier space per chapter, as chapter numbering already implies:
  `govstack:spec:cfr:data#req-3` as an *address* without `govstack:spec:cfr:data` being a
  *publication*;
* chapter-level anchors for prose references: `govstack:spec:cfr#6.6`.

Publication identity and requirement identity are distinct. A chapter need not be a publication
to be addressable, any more than clause 9.6.4 of ISO/IEC/IEEE 29148 needs to be a separate
standard to be cited.

The Committee should direct that whichever option is chosen, the identifier scheme MUST make
the domain recoverable from a cross-functional requirement's identifier.

## Pros and Cons of the Options

### Option 1: Single publication

`govstack:spec:cfr`, one version, six domain chapters. Building Block specifications declare
`extends govstack-cfr-2.0.0`.

* Good, because it is what chapter 6.2 already states, and requires no reversal of a published
  position.
* Good, because `extends` remains singular and all-or-nothing, matching the object-oriented
  model in §6.1.
* Good, because version skew between domains is not expressible, so GovMarket always has one
  version-pinned compliance target.
* Good, because one publication carries one lifecycle rather than six.
* Good, because per-domain machine-readable compliance artifacts stay possible: one requirements
  manifest and one test suite per domain. Artifact granularity is a tooling decision, and
  publication granularity does not constrain it.
* Neutral, because a security revision requires a minor version of the whole publication. This
  is a release cadence question, not a structural one.
* Neutral, because it couples all six domains to a single Architecture Working Group agreement.
  Whether this is a cost or a benefit is precisely what the Committee should decide.
* Bad, because a reader seeking only the data requirements receives a document containing all
  six domains.
* Bad, because the default form of the requirement identifier scheme does not make the domain
  recoverable. *Resolved in the Decision Outcome by adopting the domain-qualified fragment
  `#<domain>-req-<N>`.*

### Option 2: Multipart with a shared edition

Six parts, `govstack:spec:cfr:security` and so on, released together under one edition number on
the model of a multipart ISO standard. `extends` continues to name the edition.

* Good, because each domain is individually addressable and citable, which resolves the
  identifier concern structurally rather than by amendment.
* Good, because a shared edition still prevents version skew.
* Good, because `extends` can continue to name the edition rather than six parts.
* Neutral, because the release unit is still all six parts together, so revision cadence is not
  actually decoupled. The principal benefit of a series is therefore not obtained.
* Bad, because it contradicts the published statement in §6.2 that sub-categories do not have
  an individual version, unless "edition" is carefully distinguished from "version" in the
  namespace and in tooling.
* Bad, because it introduces six publication identifiers for what is released and assessed as
  one thing, which invites the misreading that a solution may conform to some parts and not
  others.

### Option 3: Independent series

Six publications, each with its own version and release cadence. A Building Block specification
extends six documents.

* Good, because each domain can be revised without compelling a release of the others. Security
  can move at its own pace.
* Good, because each domain is individually addressable, citable and separately reviewable.
* Good, because a Working Group other than Architecture could plausibly own a domain.
* Bad, because `extends` becomes six-way, and §6.1's object-oriented model of a single base class
  stops describing what happens.
* Bad, because version skew becomes expressible. A solution assessed against
  `cfr-security-2.4.0` and `cfr-data-2.1.0` requires GovMarket to record and resolve a
  combination rather than a version, and "100% of REQUIRED requirements of govstack-cfr" ceases
  to name a single thing.
* Bad, because it directly reverses the published statement in §6.2.
* Bad, because it creates six publication lifecycles, each requiring proposal, review with
  independent reviewers, release candidate and version history, for bodies of requirements that
  are between 8 and 19 requirements each.
* Bad, because it decouples the governance of a baseline whose value derives from being a single
  coherent baseline.

## More information

* [ARCH-ADR-1](./ARCH-ADR-1.md), Introduce the concept of Reference Architectures
* `spec/6-cross-functional-requirements/README.md` §6.1, §6.2
* `spec/4-interoperability-architecture/4.1-govstack-interoperability.md` §4.1.3
* `meta-specification/chapters/govstack_namespaces.md`
