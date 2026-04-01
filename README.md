# SOUL ID

Identity layer for autonomous entities.

SOUL ID is a runtime-agnostic specification that defines how autonomous entities are identified, versioned, owned, and trusted across runtimes.

**Website:** [soulid.io](https://soulid.io)

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

| Version | Title | Status |
|---|---|---|
| [v0.1](./spec/v0.1.md) | Identity | Merged |
| [v0.2](./spec/v0.2.md) | Trust | Merged |
| [v0.3](./spec/v0.3.md) | Interoperability | Merged |
| [v0.4](./spec/v0.4.md) | Registry | Merged |
| [v0.5](./spec/v0.5.md) | Ecosystem | Merged |
| [v0.6](./spec/v0.6.md) | Decentralization | Merged |

---

## Quick Example

```json
{
  "soul_id": "soulid:custodian:v1:001",
  "name": "Custodian",
  "archetype": "Guardian",
  "purpose": "Monitor and maintain system stability",
  "values": ["non-destructive", "clarity", "reliability"],
  "capabilities": ["shell", "alerts", "monitoring"],
  "memory": { "type": "persistent", "scope": "system" },
  "lineage": { "origin": "soulid:custodian:v1", "parent": null },
  "owner": { "id": "soulid", "type": "organization" },
  "trust": { "level": "self-signed" }
}
```

Validate against the schema:

```bash
npx ajv validate -s schema/soul-document.json -d examples/custodian.json
```

---

## Current Scope

### v0.1 — Identity

Introduces the foundational identity layer:

- canonical `soul_id` (format: `namespace:archetype:version:instance`)
- Soul Document structure
- runtime-agnostic design
- lineage model
- lifecycle semantics

### v0.2 — Trust

Extends the specification with trust primitives:

- ownership model
- cryptographic signatures
- trust levels (`unverified`, `self-signed`, `vouched`, `verified`)
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
- resolution protocol (`GET /resolve/<soul_id>`)
- publishing and revocation
- discovery API with filters
- DNS TXT namespace-to-registry mapping

### v0.5 — Ecosystem

Tooling, SDK, and extension points for third-party adoption:

- `soul` CLI (init, export, import, migrate, publish, resolve, verify, sign, fork)
- Runtime Adapter SDK (`@soulid/core`, TypeScript interface)
- SDK packages: `@soulid/adapter-openclaw`, `@soulid/adapter-claude-code`, `@soulid/registry-client`
- Extension model: memory backends, registry extensions, capability providers

### v0.6 — Decentralization

Sovereignty without central authority:

- **Track A — IPFS**: content-addressed storage, CID in Soul Document, pinning services
- **Track B — DID**: `did:soul` method, W3C DID Document, Universal Resolver driver
- **Track C — On-chain**: `SoulRegistry` contract on Base/Ethereum/Polygon, immutable lineage proofs
- Composable: any combination of the three tracks

---

## Core Principles

- **Identity Persistence** — an entity retains its identity across runtimes and executions
- **Runtime Independence** — identity must not depend on a specific execution environment
- **Portability** — Soul Documents are interpretable across multiple runtimes
- **Evolvability** — entities support lineage, versioning, and specialization
- **Verifiability** — identity can express authenticity, ownership, and trust

---

## Repository Structure

```text
.
├── README.md
├── LICENSE
├── CHANGELOG.md
├── VERSIONING.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── schema/
│   └── soul-document.json
├── spec/
│   ├── v0.1.md
│   ├── v0.2.md
│   ├── v0.3.md
│   ├── v0.4.md
│   ├── v0.5.md
│   └── v0.6.md
└── examples/
    ├── custodian.json
    ├── scout.json
    ├── scribe.json
    └── rasputina.json
```

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

## Security

See [SECURITY.md](./SECURITY.md).

## License

[MIT](./LICENSE)
