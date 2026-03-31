# Versioning

SOUL ID follows a staged specification evolution model.

---

## Version Format

SOUL ID versions follow the format:

v<major>.<minor>

Examples:

- v0.1
- v0.2
- v1.0

---

## Version Phases

### v0.x — Draft

- Experimental and evolving
- Backward compatibility is NOT guaranteed
- Rapid iteration is expected

### v1.0 — Stable

- First stable version of the specification
- Backward compatibility SHOULD be preserved
- Suitable for production use

### v1.x — Minor Updates

- Backward-compatible improvements
- Clarifications and extensions
- No breaking changes

### v2.0 — Major Revision

- Breaking changes allowed
- Redefinition of core concepts if necessary

---

## Versioning Rules

- A new **minor version** (v0.x or v1.x) SHOULD be released when:
  - new fields are introduced
  - optional features are added
  - clarifications are made

- A new **major version** MUST be released when:
  - identity semantics change
  - core structure changes in a non-compatible way
  - existing documents become invalid

---

## Compatibility

- v0.x versions MAY introduce breaking changes
- v1.x versions MUST remain backward compatible
- Future versions SHOULD clearly document compatibility guarantees

---

## Evolution Path

SOUL ID is expected to evolve through:

1. Identity (v0.1) ✓
2. Trust (v0.2) ✓
3. Interoperability (v0.3) ✓
4. Registry (v0.4) ✓
5. Ecosystem (v0.5) ✓
6. Decentralization (v0.6) ✓
6. Decentralization (future)

---

## Notes

Versioning reflects the evolution of the specification, not the implementation.

Runtimes MAY support multiple versions of SOUL ID simultaneously.