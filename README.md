# SOUL ID

Identity layer for autonomous entities.

SOUL ID is a runtime-agnostic specification that defines how autonomous entities are identified, versioned, owned, and trusted across runtimes.

---

## Overview

Modern AI agents can execute tasks, but they typically lack:

- persistent identity
- traceable evolution
- clear ownership
- verifiable trust
- portability across runtimes

SOUL ID addresses these limitations by separating **identity** from **execution**.

It introduces a structured model for defining entities that can persist across different environments while retaining continuity, lineage, and verifiability.

---

## Specification

- [SOUL ID v0.1](./spec/v0.1.md)
- [SOUL ID v0.2](./spec/v0.2.md)
- [SOUL ID v0.3](./spec/v0.3.md)
- [SOUL ID v0.4](./spec/v0.4.md)

---

## Current Scope

### v0.1 — Identity

Introduces the foundational identity layer:

- canonical `soul_id`
- Soul Document structure
- runtime-agnostic design
- lineage model
- lifecycle semantics

### v0.2 — Trust

Extends the specification with trust primitives:

- ownership model
- cryptographic signatures
- trust layer
- provenance and verification support

### v0.3 — Interoperability

Defines how runtimes bind and instantiate Soul Documents:

- runtime adapter interface
- reference adapters for OpenClaw and Claude Code
- pointer-index memory strategy
- cross-runtime migration protocol

### v0.4 — Registry

Defines how Soul Documents are published, discovered, and resolved:

- registry model (public, private, namespace-scoped)
- resolution protocol (`/resolve/<soul_id>`)
- publishing and revocation
- discovery API with filters
- DNS-based namespace-to-registry mapping
- trust level integration

---

## Core Principles

SOUL ID is built on the following principles:

- **Identity Persistence**  
  An entity should retain its identity across runtimes and executions.

- **Runtime Independence**  
  Identity must not depend on a specific execution environment.

- **Portability**  
  Soul Documents should be interpretable across multiple runtimes.

- **Evolvability**  
  Entities should support lineage, versioning, and specialization.

- **Verifiability**  
  Identity should be able to express authenticity, ownership, and trust.

---

## Example Use Cases

SOUL ID can be used to:

- define persistent identities for autonomous agents
- track lineage across versions and forks
- verify ownership and authenticity of entity definitions
- support interoperability across runtimes such as OpenClaw, Claude, or Hermes
- power registries and marketplaces of portable entities

---

## Repository Structure

```text
.
├── README.md
├── LICENSE
├── CHANGELOG.md
├── VERSIONING.md
├── CONTRIBUTING.md
├── spec/
│   ├── v0.1.md
│   ├── v0.2.md
│   ├── v0.3.md
│   └── v0.4.md
└── examples/
    ├── custodian.json
    ├── scout.json
    ├── scribe.json
    └── rasputina.json