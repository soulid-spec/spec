# Changelog

All notable changes to this specification will be documented in this file.

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