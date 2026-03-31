# Changelog

All notable changes to this specification will be documented in this file.

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