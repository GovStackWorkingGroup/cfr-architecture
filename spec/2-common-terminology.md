---
description: >-
  Common terminology lists both definitions for GovStack specific terminology,
  general IT terminology used in GovStack as well as a list of abbreviations in
  the end for ease of reference.
metaLinks:
  alternates:
    - https://app.gitbook.com/s/dU03bcgqfvodP4msaMaL/2-common-terminology
---

# 2 Common Terminology

Common Terminology is a list of terms, definitions, and classifications that apply across the entire GovStack specification ecosystem. Terms are capitalized when used in a formal or defined sense (for example, Building Block or Microservice). The same terms may also appear in lowercase without changing their meaning (for example, Microservice = microservice).

**It is required that Building Block specifications do not overwrite and re-define any of the terminology listed here and use this terminology whenever it applies.**

Building Block specifications may define their own terminology, applicable only within their specific scope. However, if a Building Block introduces terms that are relevant across multiple Building Blocks or GovStack in general, those terms should be defined in this common terminology document instead.

### 2.1 GovStack or digital government specific terminology

This is a list of terms that are either unique to GovStack or have been updated enough to be considered relevant within the GovStack context.

#### **Adaptor**

An optional component that maps an existing API to the GovStack specification by transforming URLs, payloads and data formats such as XML to JSON.

#### **Autonomous (Building Block)**

A component (or a building block) that can run independently, often consisting of multiple modules or microservices. An expected quality criteria for building blocks.

#### **Building Block (BB)**

Based on TOGAF: Building Block is "A package of functionality defined to meet business needs across an organization". A reusable software component that provides a basic digital service at scale. These components can be combined across multiple use cases, are interoperable and can evolve over time. Each Building Block exposes a set of services in the form of REST APIs that can be consumed by other Building Blocks or applications.

Ingress access is access from external applications to GovStack Building Blocks and applications. Egress access is access from within GovStack Building Blocks and applications to external applications.

#### **Building Block Emulator**

A lightweight implementation used in a sandbox or demonstration environment to simulate the behaviour of a building block.

#### **Building Block Software**

A software solution distributed by open source code or deployable container that is developed in compliance with GovStack Specification.

#### **Building Block Specification**

Technical specification for GovStack building block.

#### **Civil Registry**

A civil registry or CRVS (Civil Registry and Vital System) is a system recording life events (birth, death, marriage, divorces, adoptions, name changes, etc.) It is used to keep track of the life events of individuals and to produce statistics for policy making.

#### **Consent Agreement**

An agreement to be signed by the Individual and the Data Controller as prescribed by Data Policy, based on which the Data Providing System may transmit data to the Data Consuming System for the purposes described in the agreement.

#### **Consent Record**

A record created when an individual signs a consent agreement. It represents a signed consent agreement.

#### **Credential**

A document, object, or data structure that vouches for the identity of a person or attests to specific claims through some method of trust and authentication. Credentials may be physical (e.g. ID card, passport, driver's licence) or digital (e.g. verifiable credential, eID). A verifiable credential is a set of claims and metadata that are tamper-resistant and that cryptographically prove who issued it. The lifecycle of a credential includes issuance, maintenance, suspension, revocation, and expiration.

#### **Credential Holder**

An entity (person, device, or system) that possesses and manages credentials within a system or framework.

#### **Credential Issuer**

An entity responsible for the lifecycle management of credentials (e.g. issuance and revocation). This entity is typically trusted to verify and confirm the identity of the credential holder before issuing credentials.

#### **Credential Verifier**

An entity responsible for checking the authenticity and validity of credentials presented by a credential holder.

#### **Data Consumer**

A legal entity that requires an Individual's data from Data Providers according to the consent of the Individual.

#### **Data Disclosure Agreement (DDA)**

An agreement between two organisations where one acts as a Data Provider and the other as a Data Consumer. The DDA captures how data is shared between the two organisations and what role and obligation each party has.

#### **Data Policy**

A formal description of the purpose, nature and extent of consent-based Personal Data processing, covering the configuration needs by Data Providing System and Data Consuming System and the conditions defined by law.

#### **Data Provider**

A legal entity that stores and provides access to an Individual's data, which requires the Individual's consent for processing outside of its primary purpose or location.

#### **Digital Credential**

A digitally-issued and verifiable form of a claim or a set of claims made by a single issuer. Digital Credentials can be shared, verified, and stored securely, offering advantages over physical equivalents. They are often cryptographically verifiable, meaning their authenticity can be checked by Verifiers.

#### **Digital Credential Wallet**

A secure and user-controlled digital storage system designed to manage, store, and present digital credentials in a standardized and interoperable format. The wallet provides individuals with a convenient and privacy-centric means of carrying and presenting their verifiable information in various contexts.

#### **Digital Identity**

The unique representation of a subject engaged in an online transaction. A digital identity is always unique in the context of a digital service but does not necessarily need to uniquely identify the subject in all contexts. It allows an entity (citizen, business, administration) to be distinguished from any other through a set of digitally captured and stored attributes and/or credentials.

#### **Digital Public Good (DPG)**

Openly available digital solutions that meet certain standards for openness, privacy and do‑no‑harm, intended to be used by governments and other organizations as shared public resources.

#### **Digital Public Infrastructure (DPI)**

In the GovStack context this term refers to shared digital systems and services used to deliver "best-of-breed digital government services" across sectors. A key goal is to build digital government services and Digital Public Infrastructure that improve efficiency and transparency, particularly in low‑resource settings.

#### **Digital Service System**

A single purpose digital system providing government service consisting of one or multiple Building Blocks. A technical system that supports and automates routines of a Service. It typically includes a service-specific application frontend and backend plus integrations with GovStack Building Blocks and external systems.

#### **Electronic Identification, Authentication, and Trust Services (eIDAS)**

An EU regulation that sets standards for electronic identification and trust services for electronic transactions within the European Union's single market. It aims to facilitate secure cross-border digital interactions for businesses, citizens, and public administrations.

#### **Electronic Identity (eID)**

A means for the user to prove electronically that they are who they say they are and thus gain access to services. An eID is presented in an electronic environment, can appear in a form of a certificate, username, email address, or phone number, and is preferably associated with an electronic identity hardware token with a link back to digital identity.

#### **Electronic Signature (eSignature) / Digital Signature**

A data unit which is used by a Signatory to indicate his or her link to a Document. Electronic signatures enable legally binding approvals in digital government workflows and are supported through specific GovStack Building Blocks.

#### **Entity**

A thing with distinct and independent existence, such as a person, organization, or device. Entities may be subjects of registration, holders of credentials, or participants in transactions across multiple Building Blocks.

#### **Foundational Identity System (fID System)**

An identification system primarily created to manage identity information for the general population and provide credentials that serve as proof of identity for a wide variety of public and private sector transactions and services. Common types include civil registries, universal resident or national ID systems, and population registers.

#### **Functional Identity**

An identity linked to systems that have a specific function with specific business rules (e.g. education, healthcare, justice). Functional identification systems provide official proof of identity and authorization for particular purposes or sectors, including voter identification, ration cards, social security numbers, and health cards.

#### **General Data Protection Regulation (GDPR)**

Privacy requirements that grant individuals rights such as data deletion and require organizations to protect personal data. For example: [https://eur-lex.europa.eu/eli/reg/2016/679/oj](https://eur-lex.europa.eu/eli/reg/2016/679/oj)

#### **GovStack**

GovStack is a collaborative initiative that provides a reference architecture for digital government systems. It promotes a "whole‑of‑government" approach and offers a methodology for leveraging reusable technology components ("building blocks") so that governments can create interoperable digital platforms to address high‑priority use cases.

#### **Individual (Data Subject)**

A person about whom Personal Data is stored in an information system and who agrees or not with the use of this data outside of its primary purpose or location.

#### **Information Mediator (Building Block)**

Component that securely connects applications across the internet and is essentially a data exchange platform used to connect building blocks when services are not co‑located.

#### **Interoperability**

The ability of systems and products to work together. In GovStack, interoperability refers both to the technical capability of Building Blocks and applications to exchange data reliably and to the institutional and governance arrangements that make cross-agency service delivery possible.

#### **Key Functionality (KF)**

This is a specific business function or capability provided by a Building Block.

#### **Member**

An organization that is authorized to communicate via the Information Mediator for a particular GovStack implementation.

#### **Message Room**

A Pub/Sub entity that handles the distribution of events within the Information Mediator. Each Room has a set of connected event types (e.g. the "birth" Room might contain event types: "new\_birth", "birth\_complication", and "infant\_death").

#### **Non-Building Block Software**

Any (legacy) software providing API-based functionalities. May conform to Cross-Functional Requirements but does not match the functional scope of a Building Block.

#### **Organisation**

Entity (usually a government ministry or agency) that maintains applications or services for consumption by others.

#### **Organisational Subsystem**

A single purpose system providing digital government service consisting of one or multiple application, Building Blocks, microservice or other components.

#### **Personal Data**

Any information that (a) can be used to identify the Individual to whom such information relates, or (b) is or might be directly or indirectly linked to the Individual. (ISO/IEC 29100:2011).

#### **Personally Identifiable Information (PII)**

Any information that can be used to identify a specific individual, such as names, addresses, social security numbers, or biometric data.

#### **Policy as Code**

The practice of encoding policies and rules in machine‑readable formats so that they can be automatically enforced and audited.

#### **Publisher**

An entity that produces events or messages and sends them to rooms or topics. Each event has an event type associated with it. Publishers can produce events of different types. The concept applies across the Information Mediator and Messaging Building Blocks.

#### **Registration**

It is a process of issuing any approval/license/certificate by a public entity as a result of a request/application/declaration made by a user of the public service. The result of a "registration" is usually a number and/or a document (called certificate, license, permit, authorization, registration, clearance, approval, etc.)

#### **Registry**

A paper-based or electronic database (centralized or decentralized) where claims are stored and can be consulted. Registries are foundational to multiple Building Blocks including Digital Registries and Registration.

#### **Security Server**

The main piece of software responsible for implementing the "service access" layer of the Information Mediator. This software acts as a gateway and is responsible for mediating requests between various members, applications, and services. It might be a single piece, a clustered, or a serverless deployment.

#### **Service**

A value-delivering offering provided by an Organisation to Users or other organisations. A Service is defined by the outcome it provides, eligibility and obligations, policies and SLAs and the end-to-end process required to deliver it. A Service may be delivered through multiple channels (digital and non-digital) and is supported by one or more Digital Service Systems.

#### **Standard for Public Code**

A set of guidelines that encourage clear documentation, reusable code, open standards, version control and welcoming contributions. More: [https://standard.publiccode.net/](https://standard.publiccode.net/)

#### **Subscriber**

An entity (person, device, or software) that can process events of a certain event type or receive messages. Subscribers are independent of each other and their business logic is different as a rule. The concept applies across the Information Mediator, Messaging, and Scheduler Building Blocks.

#### **Use Case**

A piece of functionality described as a sequence of actions (steps) to achieve a specific goal in a specific context of usage. Each use case may involve a collection of modules or Building Blocks.

#### **Verifiable Credentials (VCs)**

Digital statements that attest to the truth of certain claims. They are issued, held, and presented in a secure and privacy-preserving manner. Verifiable credentials enable portable, tamper-evident attestations across multiple Building Blocks including Identity, Wallet, and Registration.

#### **Verifiable Presentations (VPs)**

The secure and privacy-preserving presentation of verifiable credentials to third parties for verification.

#### **Workflow (Building Block)**

A component that manages complex transactions involving multiple building blocks, including retries and rollbacks.

### 2.2 General IT terminology used in GovStack

These are general IT terms that are used within GovStack, some with explanations taking into account the GovStack context.

#### **Access**

A general term that describes the granting and restriction of access to resources for subjects. Access control is a foundational security concern across all Building Blocks.

#### **Ansible**

An open source automation tool used for configuration management, application deployment and orchestration of IT infrastructure. More: [https://docs.ansible.com/](https://docs.ansible.com/)

#### **API Gateway**

A single entry point through which clients and applications access the services of GovStack building blocks.

#### **Application Programming Interface (API)**

Interface through which Building Blocks expose REST services defined using OpenAPI. An API is a connection between computers or between computer programs and is a type of software interface that offers a service to other pieces of software.

#### **Asynchronous Design / Publish-Subscribe**

A design approach where building blocks communicate using asynchronous messages, often through a publish/subscribe pattern, to accommodate low-bandwidth or intermittent connections.

#### **Authentication**

This is the technical process of establishing that the credentials (i.e. username, password, biometric etc.) provided by a party (user, system, other) is valid and that the party can be granted basic access to system resources with default access rights. Note that authorization also needs to be applied for a party to access protected resources.

#### **Authorization**

This is the technical process of establishing whether or not an authenticated party has rights to access a given protected resource. Access rights can typically be granted or revoked administratively on a read-only and/or read-write and/or execute basis through an administrative provisioning process. Permissions or rights defined for a party typically manifest in an access token that is granted at the time of authentication for the party. Hence the processes of authentication and authorization are intrinsically related.

#### **Availability Zone**

A distinct location within a region that is engineered to be isolated from failures in other zones, providing high availability and fault tolerance.

#### **Biometric Data**

A set of physical attributes which can be used to identify a person. Most common are fingerprints, face, and iris. Biometric data may be used for establishing uniqueness, verifying identity, identifying an unknown person, claiming an identity, or verifying liveness.

#### **Business Process Model and Notation (BPMN)**

A standardized graphical notation for specifying business processes. BPMN process models depict the steps of a business process from end to end and are used by the Workflow Building Block and other process-aware components. More: [https://www.omg.org/spec/BPMN/](https://www.omg.org/spec/BPMN/)

#### **Cascading Style Sheets 3 (CSS3)**

A modular set of W3C specifications that extend CSS 2.1 with capabilities like layout grids, animations, custom properties and media queries, collectively defining how modern web content is visually styled and arranged. More: [https://www.w3.org/TR/css-2024/](https://www.w3.org/TR/css-2024/)

#### **Center for Internet Security (CIS)**

The CIS benchmarks are a set of best-practice cybersecurity standards for a range of IT systems and products. CIS Benchmarks provide the baseline configurations to ensure compliance with industry-agreed cybersecurity standards.

#### **Certificate**

Data that links a public key to a natural person or entity and confirms the identity of that entity. Certificates are used across multiple Building Blocks for authentication, signing, and trust establishment.

#### **Claim**

An attribute asserted by an entity, about itself or another entity. Claims can be pertaining to identity, entitlement, membership, ownership, role, or other associations. Claims are a foundational concept across Identity, Digital Registries, Registration, and Wallet Building Blocks.

#### **Comma-Separated Values (CSV)**

A simple tabular data format where each line represents a record and fields within a record are separated by commas, commonly used for spreadsheets and data export. More: [https://datatracker.ietf.org/doc/html/rfc4180](https://datatracker.ietf.org/doc/html/rfc4180)

#### **Common Vulnerabilities and Exposures (CVE)**

A known vulnerability in a system or network component which can be exploited by a malicious attacker to gain access or create havoc. CVE tracking is expected as part of Building Block security practices.

#### **Containerization**

A form of lightweight virtualization that involves encapsulating an application and its dependencies into a container that can run on any computing environment. All containers on a (virtual) machine share the same operating system.

#### **Cross-Cutting Requirements**

_The use of this term is deprecated. See Cross-Functional Requirements._

#### **Cross-Functional Requirements (CFR)**

Cross-Functional Requirements are technical requirements for a software solution. They may be about quality, security, data and architecture or even development process.

#### **Development Operations and Development Security Operations (DevOps and DevSecOps)**

A set of principles and practices used along with tools that fully integrates and expedites the process of building, securing and deploying code on a scheduled and/or demand basis with the goals of reduced errors, reduced time-to-market, increased security and increased accuracy.

#### **Docker**

Tools that package and orchestrate software and its dependencies in lightweight containers. Dockerfile is a text file with instructions for building a Docker container image, specifying the base image, dependencies and commands to run. More: [https://docs.docker.com/](https://docs.docker.com/)

#### **Domain Driven Design (DDD)**

Approaches that organize software into small, domain-focused services or modules, encouraging loosely coupled interactions.

#### **End of Life (EOL)**

The point at which a language, framework or dependency is no longer supported. Components used in GovStack should not be near their end of life.

#### **Endpoints**

Specific routes or URIs in APIs where specific functions can be accessed.

#### **Event**

Something that "happens" during the course of a process or system operation. Events affect the flow of processes and usually have a cause or an impact. In GovStack, events drive Pub/Sub communication, trigger workflow activities, and enable asynchronous coordination between Building Blocks.

#### **Extensible Access Control Markup Language (XACML)**

A standard that defines a declarative fine-grained, attribute-based access control policy language, an architecture, and a processing model describing how to evaluate access requests according to the rules defined in policies. More: [https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-en.html](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-en.html)

#### **Extensible Markup Language (XML)**

A markup language that uses tags to structure data hierarchically, suitable for document and data interchange across different systems. More: [https://www.w3.org/TR/xml/](https://www.w3.org/TR/xml/)

#### **Federation**

The integration of multiple systems or organizations, allowing them to share resources and manage user identities across different domains while maintaining autonomy. Federated security allows for clean separation between the service a client is accessing and the associated authentication and authorization procedures.

#### **Functional Requirements (FR)**

Functional Requirements are technical requirements for a software solution that directly provide a specific business capability or value.

#### **GraphQL**

A query language and runtime for APIs that allows clients to request only the data they need in a single request, serving as an alternative to REST. More: [https://spec.graphql.org/](https://spec.graphql.org/)

#### **Hardware Security Module (HSM)**

A device or software that can store private keys safely. HSMs are used in cryptographic operations across Building Blocks that handle signing, encryption, and key management.

#### **Hypertext Markup Language 5 (HTML5)**

Web standards for structuring and styling user interfaces. User interfaces should comply with these standards. More: [https://html.spec.whatwg.org/](https://html.spec.whatwg.org/)

#### **Hypertext Transfer Protocol Secure (HTTPS)**

An extension of HTTP that encrypts all communication between a client and server by running HTTP over TLS, ensuring data integrity, confidentiality and server authentication. More: [https://datatracker.ietf.org/doc/html/rfc2818](https://datatracker.ietf.org/doc/html/rfc2818)

#### **Hypervisor**

Software that creates and runs virtual machines by abstracting the hardware and allowing multiple operating systems to run concurrently on a host computer.

#### **Idempotent APIs**

APIs where repeated calls with the same parameters produce the same result. GET and PUT methods should be idempotent, whereas POST and DELETE methods are not.

#### **Identity and Access Management (IAM)**

A framework of policies and technologies for ensuring that the right individuals have access to the right resources at the right times for the right reasons. IAM encompasses authentication, authorization, and the management of identities, roles, groups, and access.

#### **Identity Provider / Authorization Server / Resource Server**

Roles in an authentication system: the identity provider authenticates users and issues tokens, the authorization server handles token management, and the resource server hosts protected resources.

#### **IEEE Spectrum Programming Language Rankings**

Annual rankings published by IEEE Spectrum that evaluate programming languages using factors such as job postings, open source activity and academic research.

#### **Iframe**

An HTML element that embeds one web page within another, used in GovStack for secure UI handoff between applications. More: [https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-iframe-element](https://html.spec.whatwg.org/multipage/iframe-embed-object.html#the-iframe-element)

#### **Infrastructure as Code (IaC)**

The practice of managing virtual infrastructure (software-defined storage, network, compute) as code. IaC enables reproducible, version-controlled deployments across environments.

#### **Input/Output Sanitization (I/O Sanitization)**

The practice of validating and cleaning all inputs and outputs to prevent injection attacks or data corruption.

#### **ISO 8601 / Coordinated Universal Time Timestamps (UTC Timestamps)**

A standard for representing dates and times in a consistent and unambiguous format, using Coordinated Universal Time. More: [https://www.iso.org/iso-8601-date-and-time-format.html](https://www.iso.org/iso-8601-date-and-time-format.html)

#### **JavaScript Object Notation (JSON)**

A lightweight text-based format for structuring data, often used to transmit information between web services and applications. More: [https://datatracker.ietf.org/doc/html/rfc8259](https://datatracker.ietf.org/doc/html/rfc8259) and [https://ecma-international.org/publications-and-standards/standards/ecma-404/](https://ecma-international.org/publications-and-standards/standards/ecma-404/)

#### **JSON Web Token (JWT) / Token-Based Authentication**

A method of authentication where applications exchange signed tokens that contain the claims needed to verify identity or authorization. More: [https://datatracker.ietf.org/doc/html/rfc7519](https://datatracker.ietf.org/doc/html/rfc7519)

#### **Key Rotation Policy**

A plan for regularly changing security keys to minimize the risk of compromise.

#### **Kubernetes**

Container orchestration tools used to deploy and manage multiple containers that compose a building block or set of blocks. Docker is a platform that packages an application and its dependencies into a lightweight container that runs consistently across environments. More: [https://kubernetes.io/docs/](https://kubernetes.io/docs/)

#### **Logging**

The process of recording system events and errors to support troubleshooting and auditing. Logs may be written to standard output or sent to a log management system.

#### **Message**

The main entity of communication in messaging systems. A Message holds all the necessary information to deliver information to the Publisher or to the Subscriber/client, leaving just a track of delivery Logs with no personal data included. Messages follow a predefined protocol and policy for the chosen Communication channel. As a rule, the delivery mode of the Message is asynchronous.

#### **Metadata**

Data about data; describes attributes like content, quality, and origin. Metadata schemas enable discoverability, governance, and interoperability across Building Blocks.

#### **Microservice**

Fine-grained, loosely coupled and autonomous service within an application.

#### **Multi-tenancy**

An architecture in which a single instance of software runs on a server and serves multiple tenants (users or organizations), ensuring secure isolation between them.

#### **Near Field Communication (NFC)**

A short-range wireless communication technology that enables devices to exchange data when placed close to each other. It is commonly used for contactless payments and data transfer in credential presentation scenarios.

#### **Non-Functional Requirements (NFR)**

_The use of this term is deprecated. See Cross-Functional Requirements._

#### **OAuth 2.0**

An authorization framework that enables users to grant applications access to resources without sharing credentials. More: [https://datatracker.ietf.org/doc/html/rfc6749](https://datatracker.ietf.org/doc/html/rfc6749)

#### **Online Certificate Status Protocol (OCSP)**

An Internet protocol used to check the validity of digital certificates in real time, allowing systems to determine if a certificate has been revoked. More: [https://datatracker.ietf.org/doc/html/rfc6960](https://datatracker.ietf.org/doc/html/rfc6960)

#### **Open Container Initiative (OCI)**

An industry consortium that defines open standards for container formats and runtimes, ensuring portability across platforms. More: [https://opencontainers.org/](https://opencontainers.org/)

#### **Open Web Application Security Project (OWASP)**

An online community that produces freely-available articles, methodologies, documentation, tools, and technologies in the field of web application security. OWASP guidelines are referenced in GovStack security requirements.

#### **OpenAPI**

A standardized format for defining and documenting APIs, commonly used in version 3.x to describe GovStack service APIs. More: [https://spec.openapis.org/oas/latest.html](https://spec.openapis.org/oas/latest.html)

#### **OpenID Connect**

An authentication protocol that allows a user to log in once and access multiple applications, using tokens from an identity provider. More: [https://openid.net/specs/openid-connect-core-1\_0.html](https://openid.net/specs/openid-connect-core-1_0.html)

#### **Platform as a Service (PaaS)**

A suite of software components that is fully integrated to provide a secure, convenient and rapid application development and deployment platform for cloud-style applications.

#### **Process**

A business process is defined as a set of one or more linked activities that collectively realize a business objective. A single process may have branching logic based around "gateways" which automate decisions. Processes may be asynchronous (non-blocking, the default in Workflow) or synchronous (blocking, used sparingly).

#### **Provisioning**

A way of propagating the joining or leaving of users from the system and creating/removing the accounts and access rights for users based on their target profile/role.

#### **Publish/Subscribe (Pubsub)**

A messaging pattern where senders (publishers) emit messages to a topic and receivers (subscribers) receive messages by subscribing to that topic, enabling asynchronous communication.

#### **Quick Response Code (QR Code)**

A two-dimensional barcode that must conform to the ISO/IEC 18004:2015 standard. More: [https://www.iso.org/standard/62021.html](https://www.iso.org/standard/62021.html)

#### **Region**

A geographic area where cloud services and resources are deployed, typically consisting of multiple well-interconnected data centers to provide redundancy and ensure low-latency performance.

#### **Representational State Transfer (REST)**

An architectural style that uses standard HTTP methods and resource identifiers for APIs. A type of API that follows guidelines that cover safe API design practices such as keeping personal data out of URLs, supporting caching, identifying resources via URIs and creating self-describing messages. More: [https://ics.uci.edu/\~fielding/pubs/dissertation/rest\_arch\_style.htm](https://ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

#### **Secure Proxy**

An intermediary that manages authentication and authorization for embedded UI interactions, allowing the called application to focus on its core functionality.

#### **Security Assertion Markup Language (SAML)**

An XML-based protocol suite designed for federation of identities across identity providers and service providers. SAML 2.0 is primarily used for web single-sign-on and is one of the protocols through which Single Sign-On can be implemented.

#### **Selective Disclosure**

The practice of sharing only specific information or attributes from a larger set of data or credentials, rather than revealing the entire set. Selective disclosure enhances privacy and security by minimizing the exposure of sensitive data while still providing the necessary information to fulfill a given purpose.

#### **Semantic Versioning (major.minor.patch)**

A three-part versioning scheme where a major version indicates breaking changes, a minor version adds new capabilities while remaining backward compatible, and a patch version corrects errors without changing behaviour.

#### **Service Application Frontend/Backend**

A domain-dependent digital component consisting of a user interface for data entry and a backend that handles business logic, local data access and calls to building blocks.

#### **Service-Oriented Architecture (SOA)**

A design approach that provides services to other components via a communications protocol over a network. SOA principles underpin Building Block interoperability.

#### **Service Registry**

A registry where building blocks register the services they provide and discover services offered by others.

#### SIGTERM

SIGTERM (Signal 15) is the default termination signal used in Unix-like systems to gracefully stop a process, allowing it to save state, close files, and clean up resources.

#### **Simple Mail Transfer Protocol (SMTP)**

A standard protocol used for sending email messages between mail servers and from clients to servers. More: [https://datatracker.ietf.org/doc/html/rfc5321](https://datatracker.ietf.org/doc/html/rfc5321)

#### **Simple Object Access Protocol (SOAP)**

A protocol for exchanging structured information in web services, using XML as its message format.

#### **Single Sign-On (SSO)**

An authentication pattern where a user logs in once and gains access to multiple independent systems without re-authenticating for each one. SSO is a pattern, not a protocol. It is typically implemented through protocols like SAML 2.0 or OpenID Connect.

#### **Soft Delete**

A database practice of marking records as deleted without physically removing them, unless a hard deletion is required by law.

#### Software Bill of Materials

A machine-readable inventory of all software components, libraries and dependencies included in a product, listing their versions and licenses.

#### **Stateless**

A system or API functionality criteria where each request contains all necessary information to complete the call, enabling independent handling and easier scaling.

#### **TIOBE Index**

A ranking of programming languages based on popularity and community activity, often used to gauge industry adoption.

#### **Transaction/Trace/Correlation ID**

An identifier included with each request and response that allows tracing a transaction across multiple services.

#### **Transport Layer Security 1.3 (TLS 1.3)**

The latest version of the Transport Layer Security protocol that establishes encrypted connections between networked systems, offering a faster handshake and stronger cryptographic defaults compared to its predecessors. More: [https://datatracker.ietf.org/doc/html/rfc8446](https://datatracker.ietf.org/doc/html/rfc8446)

#### **Uniform Resource Identifier (URI)**

A unique sequence of characters that identifies a logical or physical resource used by web technologies.

#### **Unicode**

A standard encoding for text characters that supports multiple languages and scripts. More: [https://www.unicode.org/versions/latest/](https://www.unicode.org/versions/latest/)

#### **Unique Identifier**

A number assigned to each requirement that is never reused, even if the requirement becomes obsolete.

#### **Universally Unique Identifier (UUID)**

A unique identifier, typically a random 128-bit number in the format like `a78622a8-1177-47af-b5da-3378ee5d4313`, attached to a newly created resource and then used to uniquely identify and reference it. Other lengths and formatting are possible.

#### **User**

Individual accessing a specific application or set of services.

#### **Version Control**

The use of tools like Git to track changes in source code, with database schema changes managed via migration scripts.

#### **Virtual Machines (VM)**

The virtual hardware with virtual CPUs, memory (RAM), disks, network adapters where consumers can run an Operating System and Software of their choice.

#### **Virtualization**

The process of creating an abstraction layer over computer hardware (storage, network, compute) that allows a computer to share its hardware with multiple virtual separated environments.

#### **Web Content Accessibility Guidelines 2.1 AA (WCAG 2.1 AA)**

The requirement that applications meet the Web Content Accessibility Guidelines 2.1 at level AA, ensuring content is accessible to users with disabilities. More: [https://www.w3.org/TR/WCAG21/](https://www.w3.org/TR/WCAG21/)

#### **Webhooks**

A mechanism for callbacks between building blocks, where a system sends a request to a predefined URL when an event occurs. More: [https://www.standardwebhooks.com/](https://www.standardwebhooks.com/)

### 2.3 Abbreviation Reference

| Abbreviation | Full Term                                                     |
| ------------ | ------------------------------------------------------------- |
| API          | Application Programming Interface                             |
| BB           | Building Block                                                |
| BPMN         | Business Process Model and Notation                           |
| CFR          | Cross-Functional Requirement                                  |
| CIS          | Center for Internet Security                                  |
| CRVS         | Civil Registry and Vital System                               |
| CSS3         | Cascading Style Sheets 3                                      |
| CSV          | Comma-Separated Values                                        |
| CVE          | Common Vulnerabilities and Exposures                          |
| DDA          | Data Disclosure Agreement                                     |
| DDD          | Domain Driven Design                                          |
| DevOps       | Development Operations                                        |
| DevSecOps    | Development Security Operations                               |
| DPG          | Digital Public Good                                           |
| DPI          | Digital Public Infrastructure                                 |
| eID          | Electronic Identity                                           |
| eIDAS        | Electronic Identification, Authentication, and Trust Services |
| EOL          | End of Life                                                   |
| fID System   | Foundational Identity System                                  |
| FR           | Functional Requirement                                        |
| GDPR         | General Data Protection Regulation                            |
| HSM          | Hardware Security Module                                      |
| HTML5        | Hypertext Markup Language 5                                   |
| HTTPS        | Hypertext Transfer Protocol Secure                            |
| IAM          | Identity and Access Management                                |
| IaC          | Infrastructure as Code                                        |
| JSON         | JavaScript Object Notation                                    |
| JWT          | JSON Web Token                                                |
| KF           | Key Functionality                                             |
| NFC          | Near Field Communication                                      |
| OAuth 2.0    | Open Authorization 2.0                                        |
| OCI          | Open Container Initiative                                     |
| OCSP         | Online Certificate Status Protocol                            |
| OWASP        | Open Web Application Security Project                         |
| PaaS         | Platform as a Service                                         |
| PII          | Personally Identifiable Information                           |
| Pubsub       | Publish/Subscribe                                             |
| QR Code      | Quick Response Code                                           |
| REST         | Representational State Transfer                               |
| SAML         | Security Assertion Markup Language                            |
| SBOM         | Software Bill of Materials                                    |
| SMTP         | Simple Mail Transfer Protocol                                 |
| SOA          | Service-Oriented Architecture                                 |
| SOAP         | Simple Object Access Protocol                                 |
| SSO          | Single Sign-On                                                |
| TLS 1.3      | Transport Layer Security 1.3                                  |
| URI          | Uniform Resource Identifier                                   |
| UTC          | Coordinated Universal Time                                    |
| UUID         | Universally Unique Identifier                                 |
| VCs          | Verifiable Credentials                                        |
| VM           | Virtual Machines                                              |
| VPs          | Verifiable Presentations                                      |
| WCAG 2.1 AA  | Web Content Accessibility Guidelines 2.1 AA                   |
| XACML        | Extensible Access Control Markup Language                     |
| XML          | Extensible Markup Language                                    |
