# Changelog

All notable changes to this specification will be documented in this file.

## v0.6

### Added

- Decentralization layer (RFC-SOULID-0006)
  - Track A — IPFS: content-addressed storage, CID en Soul Document, pinning services (Pinata, web3.storage, Infura)
  - Track B — DID: método `did:soul`, DID Document, Universal Resolver driver, cross-DID ownership
  - Track C — On-chain anchoring: hash commitment en Base/Ethereum/Polygon/Arbitrum, contrato `SoulRegistry`, lineage proofs on-chain
  - Composabilidad: los tres tracks son independientes y combinables
  - Privacy: hash commitments, IPFS cifrado, `did:peer` para identidades privadas
- CLI: `soul anchor`, `soul did resolve/export/register`, `soul lineage --chain`

### Compatibility

- Fully backward compatible con v0.1–v0.5
- Todos los tracks son opt-in

---

## v0.5

### Added

- Ecosystem layer (RFC-SOULID-0005)
  - `soul` CLI — comandos completos: `init`, `validate`, `export`, `import`, `migrate`, `publish`, `resolve`, `verify`, `sign`, `fork`
  - Runtime Adapter SDK — interface TypeScript (`SoulAdapter`) para implementar adapters de terceros
  - Paquetes SDK: `@soulid/core`, `@soulid/adapter-openclaw`, `@soulid/adapter-claude-code`, `@soulid/registry-client`, `@soulid/cli`, `@soulid/crypto`
  - Extension model: Memory Backends (file, git, s3), Registry Extensions (http, local, ipfs), Capability Providers
  - Tabla de compatibilidad spec version ↔ SDK version

### Compatibility

- Fully backward compatible with v0.1, v0.2, v0.3, v0.4
- CLI y SDK son opcionales — el core spec funciona sin ellos

---

## v0.4

### Added

- Registry specification (RFC-SOULID-0004)
  - Registry model: public, private, and namespace-scoped registries
  - Namespace ownership via signed claims
  - Resolution protocol: `GET /resolve/<soul_id>` with hash-verified responses
  - Publishing protocol: `POST /publish` with signature validation
  - Update and revocation endpoints
  - Discovery API: `GET /search` with filters (namespace, archetype, owner, trust_level)
  - Well-known endpoint: `GET /.well-known/soul-registry`
  - DNS TXT namespace-to-registry mapping for decentralized resolution
  - Trust level propagation from RFC-SOULID-0002 into registry entries
  - Reference implementation: `registry.metrono.ai`

### Compatibility

- Fully backward compatible with v0.1, v0.2, v0.3
- Registry is optional — Soul Documents remain valid without registration
- Runtimes MAY operate without a Registry for local or private deployments

---

## v0.3

### Added

- Runtime Adapter specification (RFC-SOULID-0003)
  - Introduced `runtime_hints.adapters` field in Soul Documents
  - Defined Runtime Adapter interface (runtime, version, workspace, identity/memory/capability bindings)
  - Reference adapter: **OpenClaw** — file-based workspace mapping (SOUL.md, IDENTITY.md, MEMORY.md)
  - Reference adapter: **Claude Code** — CLAUDE.md integration and pointer-index memory strategy
  - Cross-runtime migration protocol (entity portability between runtimes)
  - Pointer-index memory strategy formalized for both reference runtimes

- New example: `rasputina.json`
  - Real-world OpenClaw-native agent as a portable Soul Document
  - Demonstrates full adapter declaration with identity, memory, and capability bindings

### Updated

- `runtime_hints` field extended
  - Added `adapters` map (runtime → adapter declaration)
  - Existing `preferred` and `compatibility` fields unchanged

### Compatibility

- Fully backward compatible with v0.1 and v0.2
- New `adapters` field is optional
- Existing Soul Documents remain valid without modification

---

## v0.2

### Added

- Ownership model for entities
  - Introduced `owner` field to define entity authority
  - Defined ownership rules and constraints

- Cryptographic signatures
  - Added `signature` field
  - Defined signature structure (algorithm, value, public_key)
  - Established signing scope requirements

- Trust layer
  - Introduced `trust` field
  - Defined trust levels (unknown, self-signed, verified, trusted)
  - Enabled trust evaluation by runtimes

### Updated

- Extended Soul Document structure
  - Added ownership, signature, and trust sections

- Identity model
  - Expanded identity semantics to include verifiability

### Compatibility

- Fully backward compatible with v0.1
- New fields are optional and do not break existing documents

---

## v0.1

### Added

- Initial SOUL ID specification
- Canonical identifier format (`soul_id`)
- Soul Document structure
- Lineage model (origin, parent, forked_from)
- Runtime-agnostic design principles
- Basic lifecycle definition