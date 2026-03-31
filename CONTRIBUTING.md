# Contributing to SOUL ID

SOUL ID is an open specification. Contributions are welcome.

---

## Ways to Contribute

- **Propose changes** — open an issue to discuss ideas before submitting a PR
- **Fix errors** — typos, inconsistencies, broken links
- **Improve examples** — add or update Soul Document examples
- **Implement adapters** — build runtime adapters using the SDK (RFC-SOULID-0005)
- **Build tooling** — extend the `soul` CLI or create new SDK packages

---

## Process

### For spec changes (RFCs)

1. Open an issue describing the proposed change and its motivation
2. Wait for discussion and rough consensus
3. Submit a PR with the new or modified RFC
4. RFC format: `spec/vX.Y.md` following the existing structure

### For documentation, examples, and tooling

1. Fork the repo and create a branch (`feat/your-change`)
2. Make your changes
3. Submit a PR with a clear description

---

## RFC Structure

Each RFC document should include:

- **Abstract** — one paragraph summary
- **Introduction** — motivation and context
- **Specification** — normative content (use MUST/SHOULD/MAY per RFC 2119)
- **Security Considerations**
- **Compatibility** — backward compatibility notes
- **Conclusion**

---

## Design Principles

Keep contributions aligned with SOUL ID's core principles:

- **Runtime independence** — avoid binding identity to a specific execution environment
- **Portability** — Soul Documents must be interpretable across runtimes
- **Minimal footprint** — prefer small, composable additions over large monolithic changes
- **Backward compatibility** — new spec versions must not break existing Soul Documents

---

## Validation

New or modified Soul Documents in `examples/` must validate against the JSON Schema:

```bash
npx ajv validate -s schema/soul-document.json -d examples/your-example.json
```

---

## Code of Conduct

See [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md).

---

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](./LICENSE).
