---
title: Reconciling the two GovStack identifier syntaxes
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
# Reconciling the two GovStack identifier syntaxes

## Context and Problem Statement

The convention published in the canonical corpus and the convention proposed to replace it use
different identifier syntaxes, and nothing defines the relationship between them.

**The hyphenated form is the canonical convention.** It is specified in
`specification-framework/chapters/specifications_model.md` §5.2.1:

> The schema used is **govstack-\[document-type]-\[name]** for the specification. When referring
> to a version, then the schema is **govstack-\[document-type]-\[name]-\[version]**. When
> referring to a requirement then the schema is similarly
> **govstack-\[document-type]-\[name]-\[requirement-type]#req-\[requirement-number]**.

It yields `govstack-bb-wallet`, `govstack-bb-wallet-2.0.0`, `govstack-cfr-data`,
`govstack-bb-wallet-fr#req-7`. It appears in published normative text: §6.2 of the
Cross-Functional Requirements chapter uses it for every `extends` declaration.

**The colon form is proposed, not deployed.** It is registered in
`meta-specification/chapters/govstack_namespaces.md` and used in the `metadata.yml` of the new
Building Block template and of the Specification Framework, all of which are part of the change
this ADR belongs to. It yields `govstack:spec:bb:wallet`, `govstack:spec:cfr`, `govstack:wg:cfid`.

This ADR asks which convention GovStack adopts going forward. No production system is broken by
the divergence.

No rule converts one form into the other. The hyphenated form **omits the class segment**:
`govstack-bb-wallet` carries no equivalent of `spec`. That segment identifies what a publication
asserts requirements about, so the publication-class model depends on it. Dropping it means a
reader cannot resolve the identifier without consulting a registry.

Settle this **before allocating requirement identifiers**. Once issued, an identifier is never
reused, so renumbering cannot repair a later change of syntax.

> **Out of scope.** Whether a version belongs inside an identifier at all is a separate question,
> carried by [ARCH-ADR-4](./ARCH-ADR-4.md). This ADR concerns only the syntax by which nodes are
> separated. Both ADRs should be decided together, since the separator choice constrains how a
> version can be appended.

> **Note on field names.** `publication_id` and `publication_identifier` both appear across the
> corpus. This reflects templates not yet migrated rather than a competing convention, and the
> field name is unified as part of implementing whichever option is chosen.

## Decision Drivers

* **Separability of namespace nodes.** The principal driver. A reader or a parser must be able to
  recover the nodes an identifier is composed of. The two forms differ here, as set out below.
* **Continuity of published usage.** `govstack-cfr-2.0.0` and `govstack-bb-wallet-2.0.0` appear in
  published normative text and in every `extends` declaration.
* **Usability outside a document.** Identifiers appear in filenames, repository names, URLs, git
  branches, test fixtures and procurement documents, as well as in metadata.
* **Registry dependency.** Whether resolving an identifier requires a lookup table, or can be
  done by inspection.
* **Consistency of requirement fragments.** ARCH-ADR-2 adopted `govstack:spec:cfr#data-req-3`. The
  hyphenated schema expresses the same requirement as `govstack-cfr-data#req-3`. One of the two
  must be canonical.

### The separability problem in detail

The colon form reserves `:` as a node separator and forbids it inside a name. Splitting on the
separator decomposes any identifier:

```
govstack:spec:bb:information-mediator
   └─ govstack │ spec │ bb │ information-mediator
```

The hyphenated form uses `-` as the node separator and also allows it inside names. **Two of the
fourteen Building Block names contain a hyphen**: `cloud-infrastructure` and
`information-mediator`. The ambiguity sits in the current corpus:

```
govstack-bb-information-mediator-fr
   └─ govstack │ bb │ information-mediator │ fr     ← correct
   └─ govstack │ bb │ information │ mediator-fr     ← equally well-formed
```

§5.2.1 acknowledges this and resolves it by appeal to prior knowledge: "Between 'bb' and 'fr'
would be the building block specification name, with or without dashes." To parse an identifier
naming a Building Block, a parser must already hold the set of valid Building Block names.

The same pressure has already produced a second rule whose only purpose is disambiguation:

> **"numbers"** — when separated with dash — are reserved only for version numbering, not for
> naming. *For example govstack-bb-wallet-2 is not allowed, however govstack-bb-wallet2 is.*

The identifier syntax, and nothing else, constrains what Working Groups may name a Building
Block. Each new node type added to the schema widens the reserved-word surface and adds further
rules of this kind. The publication-class model adds at least `arch`, `guide` and `process`.

## Considered Options

* **Option 1: Colon form canonical; hyphenated form retired.**
* **Option 2: Hyphenated form canonical; colon form retired.**
* **Option 3: Colon form canonical; hyphenated form retained as a registered short name.**

## Decision Outcome

*To be completed by the Architecture Committee.*

The work that produced this ADR recommends **Option 3**. Option 1 wins on the principal driver,
but discards a form already present in published normative text, one that serves needs the colon
form serves badly. Option 3 keeps the canonical identity unambiguous and lets the familiar form
continue where it reads better. The cost is a registry GovStack has committed to maintaining
anyway.

### Consequences

*To be completed once the option is chosen.*

### Relationship to ARCH-ADR-2

[ARCH-ADR-2](./ARCH-ADR-2.md) adopted `govstack:spec:cfr#<domain>-req-<N>`. Options 1 and 3 leave
that decision standing. **Option 2 reverses it**, rendering the same requirement as
`govstack-cfr-data#req-3`. The Committee should treat ARCH-ADR-2's identifier form as conditional
on the outcome of this ADR.

Under Option 1 or 3, ARCH-ADR-2's fragment form generalises across publication kinds, with the
fragment prefix naming the requirement's grouping within its publication:

| Publication | Grouping | Requirement identifier |
|---|---|---|
| `govstack:spec:cfr` | domain | `govstack:spec:cfr#data-req-3` |
| `govstack:spec:bb:wallet` | requirement type | `govstack:spec:bb:wallet#fr-req-7` |
| `govstack:spec` | — | `govstack:spec#req-12` |

This replaces the `-fr` and `-cfr` name segments of §5.2.1. Those segments exist because the
hyphenated form has no fragment structure to carry the grouping.

### Confirmation

Confirmed by the Architecture Committee following Architecture Working Group discussion. The
outcome is implemented in `specification-framework/chapters/specifications_model.md` §5.2.1, in
`meta-specification/chapters/govstack_namespaces.md`, and in the publication metadata of every
publication. The `publication_id` / `publication_identifier` field name is unified as part of the
same change.

## Pros and Cons of the Options

### Option 1: Colon form canonical; hyphenated form retired

`govstack:spec:bb:wallet`, `govstack:spec:bb:wallet:2.0.0`, `govstack:spec:cfr#data-req-3`.
Prose, `extends` declarations and test fixtures all migrate.

* Good, because namespace nodes separate without ambiguity, with no reserved-word rules and no
  constraint on what a Building Block may be named.
* Good, because an identifier can be parsed by inspection, with no registry lookup.
* Good, because the class segment is always present, so the conformance subject is recoverable
  from any identifier.
* Good, because one syntax means one field name, one validator and one migration.
* Bad, because it reverses the canonical convention. §6.2 of the CFR README and §5.2.5 of
  `specifications_model.md` both use the hyphenated form in `extends` declarations, and both are
  published normative text.
* Bad, because `:` is awkward or illegal in filenames, repository names, git branches and some CI
  systems. Wherever identifiers meet the filesystem, authors need a separate slug.
* Bad, because `govstack:spec:bb:wallet:2.0.0` reads worse in prose and in procurement documents
  than `govstack-bb-wallet-2.0.0`.

### Option 2: Hyphenated form canonical; colon form retired

`govstack-bb-wallet`, `govstack-cfr-data#req-3`. The namespace registry is rewritten in
hyphenated form and `metadata.yml` files migrate.

* Good, because it is the canonical convention. It preserves every published usage without
  reversal, and requires no migration of existing normative text.
* Good, because identifiers are directly usable as filenames, repository names and URL slugs.
* Good, because it reads well in prose and in procurement documents.
* Bad, because namespace nodes do not separate. Parsing requires prior knowledge of valid names,
  so validation depends on the registry the syntax was meant to make unnecessary.
* Bad, because it requires a growing body of reserved-word and reserved-character rules, and
  narrows what Working Groups may call a Building Block. One naming rule already exists to serve
  the syntax.
* Bad, because the form omits the class segment, so no reader can recover the conformance subject
  from an identifier. Restoring it as `govstack-spec-bb-wallet` contradicts every published usage
  the option exists to preserve.
* Bad, because it reverses ARCH-ADR-2's requirement identifier decision.

### Option 3: Colon form canonical; hyphenated form a registered short name

The colon form is the identity. The hyphenated form is a **short name**: a registered,
human-facing label resolving to exactly one canonical identifier through
`meta-specification/chapters/govstack_namespaces.md`. Working Groups declare short names rather
than deriving them. Short names appear in prose, repository names, filenames and `extends`
declarations. Canonical identifiers appear in metadata, machine-readable artifacts and anywhere a
tool must resolve them without help.

* Good, because the canonical form keeps node separation clean and carries full class
  information.
* Good, because published usage such as `govstack-bb-wallet-2.0.0 extends govstack-cfr-2.0.0`
  stays valid, as a short name rather than as an identity.
* Good, because filesystem-safe and prose-friendly labels stay available, and the canonical syntax
  gives up nothing.
* Good, because the registry that resolves short names is one GovStack already maintains for
  other purposes.
* Neutral, because short names are lossy by design. They omit the class segment, so a tool
  resolves them by lookup rather than by inspection. A label can afford that; an identity cannot,
  and the option turns on that distinction.
* Bad, because editors must keep two forms in step, and no syntax check catches a short name
  registered against the wrong canonical identifier.
* Bad, because authors must know which form belongs in which context, and will sometimes get it
  wrong. Validation limits the damage: metadata fields accept canonical identifiers only.
* Bad, because it is more machinery than either single-syntax option.

## More information

* [ARCH-ADR-2](./ARCH-ADR-2.md), Shape of the Cross-Functional Requirements publication
* `specification-framework/chapters/specifications_model.md` §5.2.1, §5.2.2, §5.2.5
* `meta-specification/chapters/govstack_namespaces.md`
* `cfr-architecture/spec/6-cross-functional-requirements/README.md` §6.2
* `workinggroups-framework/bb-specification-template/new_bb_template/proposals/requirement-id-scheme.md`
