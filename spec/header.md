# High Assurance Verifiable Identifiers (HAVID) Bridging Specification

**Version:** Draft 07  
**Authors:** Alex Tweeddale, Jesse Carter  
**Contributors:** Markus Sabadello, Scott Perry, Drummond Reed, Tim Bouma

---

## 1. Abstract

The digital identity landscape comprises multiple Verifiable Identifier (VID) types, including X.509 certificates, Decentralized Identifiers (DIDs), and DNS records. Each serves a distinct purpose. X.509 certificates bind public keys to domain names under Certificate Authority governance. DIDs provide controller-managed cryptographic key control. DNS offers globally recognizable, human-readable naming and discoverability. These systems will continue to coexist, yet no widely adopted method exists for establishing verifiable relationships between them.

This specification defines **cross-endorsement**: the practice of having identifiers in different ecosystems explicitly and verifiably reference one another to establish that they are controlled by the same entity. Cross-endorsement enables a composite trust picture in which each identifier contributes the assurance it is best suited to provide, without collapsing the distinct governance, lifecycle, and security properties of each system.

Implementers MAY additionally establish **key alignment**, demonstrating the same or verifiably linked cryptographic key material across identifiers, as a supplementary assurance mechanism. Key alignment carries significant risks and is subject to strict normative requirements defined herein.

Together, cross-endorsement and (optionally) key alignment allow a VID to participate in a **High Assurance Verifiable Identifier (HAVID)**: a composite identity structure in which multiple identifiers, each operating under its native trust model, are linked through verifiable mutual references and (where warranted) cryptographic proof.

This specification defines a **linking mechanism**, not a trust framework. The trust semantics of each identifier remain governed by their native frameworks (Web PKI, DNSSEC, DID method specifications, eIDAS, GLEIF, etc.). A HAVID complements these frameworks by enabling verifiable cross-referencing between them. It does not substitute for them.

---

## 2. Status of This Document

*This section is non-normative.*

| Document Stage | Version | Reviewed by | Date | Status |
|---|---|---|---|---|
| Working Draft | 07 | High Assurance VID Taskforce Members | TBD | Ongoing |
| Working Group Approved Draft | v1.0 | Technology Stack Working Group | ... | ... |
| ToIP Approved Draft | v1.0 | ToIP Steering Committee | ... | ... |

---