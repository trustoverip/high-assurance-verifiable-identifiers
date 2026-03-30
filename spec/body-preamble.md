## 3. Goals and Motivation

*This section is non-normative.*

### 3.1. Motivation

Today, a digital wallet holding a DID has no standardized way to prove that the DID belongs to a specific legal entity. A Certificate Authority that wants to include a DID in an X.509 certificate has no defined procedure for validating DID control. A DNS domain can serve as a globally recognizable anchor for an organization, but provides no cryptographic identity binding beyond TLS. Each of these gaps exists because the identifier systems involved were designed independently, and no common mechanism exists for establishing verifiable, machine-readable relationships between them.

Without such a mechanism, relying parties are forced to treat each identifier in isolation, forgoing the composite assurance that comes from knowing that a DID, a domain, and a certificate are all controlled by the same organization. This specification addresses that gap by defining cross-endorsement as a standard bridging pattern, giving implementers a concrete, auditable way to link identifiers across ecosystems without requiring any single system to become authoritative over the others.

### 3.2. Goals

This specification has two goals:

**Goal 1: Asserting legal and organizational identity for identifiers.** By linking identifiers across ecosystems, relying parties can trace an abstract digital identifier (such as a DID or domain name) to a legally recognized organization through standardized metadata, including organizational identifiers such as LEIs.

**Goal 2: Creating common patterns for cross-endorsement of identifiers controlled by the same entity.** This specification defines how identifiers in different ecosystems can verifiably reference one another, establishing that the same entity controls them and enabling composite assurance without requiring convergence on a single identifier format or trust model.

These goals are intentionally scoped. This specification does not seek to unify the governance models of different identifier ecosystems, nor does it prescribe which identifier type is authoritative. It provides a framework for enabling trust to flow between systems in a verifiable, auditable, and safe manner.

---

## 4. Conformance

In addition to sections marked as non-normative, all authoring guidelines, diagrams, examples, and notes in this specification are non-normative. Everything else in this specification is normative.

The key words MAY, MUST, MUST NOT, OPTIONAL, and SHOULD in this document are to be interpreted as described in BCP 14 [RFC2119] [RFC8174] when, and only when, they appear in all capitals.

### 4.1. Conformance Classes

This specification defines requirements for three conformance classes. An implementation MAY conform to more than one class.

| Conformance Class | Description | Primary Sections |
|---|---|---|
| Identifier Controller | An entity that establishes and maintains cross-endorsements and (optionally) key alignment across identifiers it controls. | §9, §10, §11, §12, §13 |
| Verifier / Resolver | An entity that resolves identifiers, traverses cross-endorsement references, validates integrity, and determines assurance level. | §9, §10, §14, §15 |
| Certificate Authority | A CA that issues X.509 certificates participating in cross-endorsements, including certificates referencing DIDs. | §13, §20.1 |

---