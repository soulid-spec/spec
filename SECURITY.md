# Security Policy

## Scope

This repository contains the SOUL ID specification. Security considerations apply to:

- The cryptographic primitives defined in RFC-SOULID-0002 (signatures, key management)
- The on-chain anchoring protocol defined in RFC-SOULID-0006 (smart contracts)
- The DID method defined in RFC-SOULID-0006 (`did:soul`)
- Reference implementations and example code

---

## Reporting a Vulnerability

If you discover a security vulnerability in the SOUL ID specification or any reference implementation:

1. **Do not open a public issue.**
2. Email: **security@soulid.io**
3. Include:
   - Description of the vulnerability
   - Affected RFC(s) or component(s)
   - Potential impact
   - Steps to reproduce (if applicable)
   - Suggested fix (optional)

We will acknowledge your report within 48 hours and aim to publish a fix or advisory within 30 days.

---

## Known Considerations

### Key Management (RFC-SOULID-0002)

- Signing keys MUST be stored outside the workspace directory
- Key compromise requires revocation of the Soul Document and re-signing with a new key
- The spec does not mandate a specific key rotation policy — implementors should define one

### On-Chain Anchoring (RFC-SOULID-0006)

- The `SoulRegistry` smart contract is immutable after deployment
- Owner wallet key compromise allows unauthorized revocation
- Anchoring is public — do not anchor Soul Documents containing sensitive information
- Use hash commitments only; never store document content on-chain

### DID Method (RFC-SOULID-0006)

- `did:soul` resolution trusts the configured resolver endpoint
- Implementors should verify DID Documents against the `verificationMethod` public key
- Cross-DID ownership (`did:key`, `did:web`, etc.) inherits the security properties of the referenced DID method

---

## Responsible Disclosure

We follow responsible disclosure practices. Security researchers who report valid vulnerabilities will be credited in the relevant advisory unless they prefer to remain anonymous.
