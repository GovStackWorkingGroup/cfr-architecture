---
title: Whether a version belongs inside a publication identifier
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
# Whether a version belongs inside a publication identifier

## Context and Problem Statement

The canonical convention appends a version to the publication name using the same separator that
divides the identifier's nodes. `specification-framework/chapters/specifications_model.md` §5.2.2
gives `govstack-bb-workflow-2.0.0`, and §6.2 of the Cross-Functional Requirements chapter gives
`govstack-cfr-2.0.0`. A requirement carrying a version is specified in §5.2.1 as

> **govstack-\[document-type]-\[name]-\[requirement-type]-\[version]-#req-\[requirement-number]**

placing the version between the requirement type and the fragment.

The same text **already contains a two-level model**, without naming it. §6.2 states that CFR "can
be universally referred to as **govstack-cfr**" and, "when referring to a specific version", as
**govstack-cfr-2.0.0**. Both are in use: a version-free identifier denoting the publication, and a
version-qualified one denoting a single version of it. The proposed publication metadata draws the
same separation structurally, with a version-free `publication_id` and a `versions:` list beside
it.

What remains unsettled is **how a version attaches**. The current answer, the node separator,
carries three consequences the Committee should weigh.

### It constrains what Working Groups may name a publication

The version shares a separator with the nodes, so a trailing numeric node is ambiguous. §5.2.1
resolves this by prohibiting it:

> **"numbers"** — when separated with dash — are reserved only for version numbering, not for
> naming. *For example govstack-bb-wallet-2 is not allowed, however govstack-bb-wallet2 is.*

The identifier syntax, and nothing about the publication, imposes this naming restriction.

### It leaves requirement identity across versions undefined

§5.2.2 states:

> Requirements themselves are individually not versioned. If a requirement needs to be updated,
> the whole specification document has to be updated.

So `#req-7` denotes the same requirement in 2.0.0 and in 2.1.0, even where its text differs. Two
distinct things need expressing, and only one has a form today:

* **the requirement**, across all versions. "Wallet requirement 7", the thing a `DEPRECATED`
  classifier freezes and the never-reuse rule protects.
* **the requirement as it stood in one version**, which a procurement document or a compliance
  assessment must pin.

Bind the version into the identifier and only the second sense survives. Treat the version as an
optional qualifier on a stable base and both survive.

### It interacts with ARCH-ADR-3

If [ARCH-ADR-3](./ARCH-ADR-3.md) adopts the colon form, appending a version with the node separator
gives `govstack:spec:bb:wallet:2.0.0`, where `2.0.0` looks exactly like a name node. Changing the
separator carries the ambiguity across rather than removing it. Decide the two ADRs together.

## Decision Drivers

* **Stability of identity.** Does the identifier name the publication, or one version of it? A
  reference rewritten at every release is a citation rather than an identifier.
* **Separability.** In either syntax, a reader must be able to tell a version from a namespace
  node.
* **Citation precision.** Procurement documents, `extends` declarations and compliance records
  need to pin a version exactly.
* **Requirement identity across versions.** The scheme must express both the version-independent
  and the version-pinned senses.
* **Freedom in naming.** Whether the syntax goes on restricting what a publication may be called.
* **Continuity.** `govstack-cfr-2.0.0` appears in published normative text.

## Considered Options

* **Option 1: Version appended with the node separator.** The canonical convention,
  `govstack-bb-wallet-2.0.0`, or `govstack:spec:bb:wallet:2.0.0` under ARCH-ADR-3 Option 1.
* **Option 2: Version-free identity, with a distinct version separator.** The identifier carries no
  version. A version attaches through a character reserved for the purpose and legal in neither
  names nor nodes, for example `govstack:spec:bb:wallet@2.0.0`.
* **Option 3: Version-free identity only.** Identifiers carry no version. The surrounding metadata
  or citation context supplies it.

## Decision Outcome

*To be completed by the Architecture Committee.*

The work that produced this ADR recommends **Option 2**. It keeps the two-level model already
present in §6.2, separates the version cleanly in either syntax, expresses both senses of
requirement identity, and dissolves the §5.2.1 naming restriction as a side effect. Option 3 gets
identity right but removes something `extends` declarations and procurement documents use: precise
pinning inside a single string.

### Consequences

*To be completed once the option is chosen.*

### Confirmation

Confirmed by the Architecture Committee, together with [ARCH-ADR-3](./ARCH-ADR-3.md), following
Architecture Working Group discussion. The outcome is implemented in
`specification-framework/chapters/specifications_model.md` §5.2.1 and §5.2.2, in §6.2 of the
Cross-Functional Requirements chapter, and in publication metadata.

## Pros and Cons of the Options

### Option 1: Version appended with the node separator

* Good, because it is the canonical convention and appears in published normative text.
* Good, because it reads naturally: `govstack-bb-wallet-2.0.0`.
* Good, because a single string carries both identity and version, which suits `extends`
  declarations and procurement citations.
* Neutral, because the version-free form stays available, as §6.2 shows. Convention rather than
  syntax preserves the two-level model.
* Bad, because the syntax cannot separate a version from a name node, which forces the prohibition
  on trailing numeric nodes.
* Bad, because under ARCH-ADR-3 Option 1 or 3 it carries that ambiguity into the colon form
  unchanged.
* Bad, because §5.2.1's requirement schema seats the version between the requirement type and the
  fragment, leaving a version-independent reference to a requirement with no defined form.

### Option 2: Version-free identity, with a distinct version separator

`govstack:spec:bb:wallet` is the identity; `govstack:spec:bb:wallet@2.0.0` is one version of it;
`govstack:spec:bb:wallet#fr-req-7` is a requirement; `govstack:spec:bb:wallet@2.0.0#fr-req-7` is
that requirement as it stood in that version.

* Good, because the identifier names the publication and survives every release unchanged.
* Good, because a character legal in neither names nor nodes separates the version, in either
  syntax.
* Good, because both senses of requirement identity become expressible, over a version-free
  base.
* Good, because the §5.2.1 prohibition on trailing numeric nodes dissolves. `wallet-2` and
  `wallet2` both become legal names.
* Good, because it works unchanged whichever syntax ARCH-ADR-3 selects, freeing the Committee to
  resolve the two decisions in either order.
* Neutral, because `@` comes from package managers rather than from the standards world. Another
  reserved character serves as well.
* Bad, because it changes the form of every published version reference, including those in §6.2.
* Bad, because it adds a third punctuation role to identifiers, after the node separator and the
  fragment marker.

### Option 3: Version-free identity only

* Good, because it takes the strictest reading of what an identifier is: a stable name for a
  thing.
* Good, because it removes every ambiguity between versions and nodes.
* Bad, because no one can write a version-pinned reference as a single string, so
  `extends govstack-cfr-2.0.0` becomes a structured declaration.
* Bad, because procurement documents and compliance records cite one version in running text, and
  would carry the version separately from the identifier.
* Bad, because it reverses more published normative text than Option 2 and recovers no capability
  in exchange.

## More information

* [ARCH-ADR-3](./ARCH-ADR-3.md), Reconciling the two GovStack identifier syntaxes
* [ARCH-ADR-2](./ARCH-ADR-2.md), Shape of the Cross-Functional Requirements publication
* `specification-framework/chapters/specifications_model.md` §5.2.1, §5.2.2
* `cfr-architecture/spec/6-cross-functional-requirements/README.md` §6.2
