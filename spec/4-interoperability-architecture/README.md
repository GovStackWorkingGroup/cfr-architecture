---
description: >-
  This page gives general overview about GovStack Interoperability and Building
  Block architecture: what it is about and how to apply it in creation of
  digital government services.
metaLinks:
  alternates:
    - >-
      https://app.gitbook.com/s/dU03bcgqfvodP4msaMaL/4-interoperability-architecture
---

# 4 Interoperability Architecture

Interoperability is the ability of different organizations, systems and technologies to work together towards shared public service delivery goals.&#x20;

**In its simplest form, interoperability is a language that allows systems to collaborate, similarly to how people speaking the same language are able to collaborate effectively.**

When two systems understand the same language - the same data formats, the same protocols, the same rules for what a request means and what a response contains - they can collaborate. When they do not, every connection becomes a custom project that costs too much and breaks too easily.

It is important to remember that this goes beyond technology. For government institutions to deliver connected services, they need alignment at multiple levels: organizations must agree on responsibilities, data must carry consistent meaning across institutional boundaries, applications must expose predictable interfaces and infrastructure must provide a reliable foundation. A failure at any one of these levels breaks the conversation, even if every other level works fine.

Most governments start by building systems ministry by ministry, each serving a specific mandate. Over time this creates an environment where dozens of isolated systems hold overlapping data, duplicate each other's functions and cannot coordinate without manual work. Citizens experience this as repeated requests for the same information and slow processing across agencies. Institutions experience it as integration projects that consume budget without producing anything reusable.

#### Interoperability Frameworks

Interoperability Framework establishes the shared language - common rules, standards and governance - that allow systems to work together without requiring every pair of institutions to negotiate their own arrangements from scratch. It defines how data should be described so it carries the same meaning everywhere, how services should expose their capabilities so others can consume them reliably and how organizations should coordinate so that responsibilities are clear.

<figure><img src="../.gitbook/assets/TOGAF for GovStack (1).png" alt="" width="375"><figcaption><p>GovStack specifications through TOGAF perspective</p></figcaption></figure>

**What an interoperability framework should cover?**

It is a common misconception that an Interoperability Framework is only about data exchange between applications. A mature and modern interoperability framework operates across four core layers, with governance and legal as cross-cutting layers that apply to all of them. Each one can block progress independently if left unaddressed.

* **Governance** sets the authority structure. It assigns a central team responsible for maintaining the framework, updating it annually, running the national service and API catalogues and coordinating the architecture community across the public sector. It establishes workgroups for digital services, data governance and architecture review. Ministries keep control of their own services - they decide what to build. The central team sets the rules for how it should be built so that everything connects. Governance also defines how compliance is enforced: review processes before launch, reporting during operation and ties to funding and audit cycles.
* **Legal layer** provides the basis for everything else. It covers the laws and regulations that allow or constrain data exchange between institutions: data protection legislation, electronic communications rules, cybersecurity obligations, digital signature requirements and institutional mandates. Before two institutions can share data, there must be a legal basis for that exchange. The legal layer also includes data-sharing agreements between institutions that formalize what data flows where, under what conditions and with what accountability.
* **Organizational layer** defines who does what. It establishes service ownership - every digital service needs a named business owner and a named technical owner. It sets the rules for how institutions coordinate when a service crosses ministry boundaries: documented processes, agreed responsibility splits, service level agreements. It includes a national service catalogue where every public digital service is registered with its owner, legal basis, access method and supported standards. Without this layer, systems can technically connect but nobody knows who is responsible when something breaks or needs to change.
* **Semantic layer** defines what data means. It covers common data models, naming conventions, classification systems and metadata requirements so that when one institution sends a record to another, both sides interpret it the same way. It also covers the format side - the agreed structure of requests, responses, error codes and API specifications (typically OpenAPI). This layer requires active management: a terminology platform, data quality rules, reference data registries and clear guidelines for how new data elements get defined and published. Without it, connected systems produce mismatched or duplicate data.
* **Technical layer** defines how systems talk to each other. It specifies the protocols (HTTPS, REST), data formats (JSON, XML), authentication methods (OAuth2, PKI), API design standards and the national data exchange platform that routes traffic between institutions. It also covers reusable components - shared libraries, authentication modules, notification services - that ministries can use instead of building their own. Cross-functional requirements like logging, traceability, error handling and versioning belong here. This layer is what developers and vendors work with directly, so it must be specific enough to put into procurement documents and tender requirements.
* **Infrastructure layer** defines the foundation everything runs on. It covers hosting standards (cloud-first policies, data center requirements), network connectivity between participants, backup and recovery expectations, cybersecurity baselines and scalability requirements. Digital services run around the clock and interoperability means your system's availability affects other institutions - not just your own users. Infrastructure security is especially critical because a breach at this level can compromise trust in the entire data exchange platform.

> GovStack and its specifications are not an Interoperability Framework, however they compliment interoperability frameworks notably in the non-governance and non-legal blocks. It is highly recommended for governments to implement GovStack architecture specification as part of government interoperability framework.

**Why governments need an interoperability framework?**

Without a framework, interoperability still happens - through point-to-point connections, informal agreements and workarounds. This works for a handful of integrations. It falls apart at national scale because each new connection multiplies complexity instead of reducing it. A country with fifty government systems and no common standards faces up to 1,225 unique integration paths. The same fifty systems with a shared framework face fifty connections to a common set of rules.

The case for a framework comes down to four things:

* **Citizen value**. Connected services mean that a life event - a birth, a business registration, a change of address - can trigger coordinated responses across relevant institutions without the citizen acting as a messenger between them. This only works when systems share a common language for identifying people, describing events and routing requests.
* **Institutional efficiency**. When ministries can reuse components, data services and integration patterns instead of building everything from scratch, delivery gets faster and cheaper. Reuse requires standards. Without agreed API conventions, data models and security requirements, one ministry's component is another ministry's integration problem.
* **Vendor independence**. A framework built on open standards means no single technology provider controls the interfaces between public institutions. Systems built to open specifications can be replaced, upgraded or extended without rewriting every connection they participate in. This is the difference between a government that can evolve its technology step by step and one that faces expensive, high-risk replacement projects every few years.
* **Trust and accountability**. When data flows between institutions through governed channels with clear audit trails, citizens can understand who accessed their information and why. When data flows through informal channels and untracked exports, accountability disappears.

Every government building digital services faces the same structural questions: how should APIs be designed, what metadata should accompany data exchanges, how should identity be verified across institutional boundaries, what security baseline applies to all services.&#x20;

Answering these questions independently, country by country, is reinventing the wheel and this is where GovStack plays a role. GovStack specifications provide a common architectural language - tested, open and vendor-neutral - so that countries can focus their effort on services that matter to their citizens rather than on infrastructure problems that have already been solved elsewhere.
