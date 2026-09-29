# Security: Persona Console

> English translation of the original [`docs/original/SECURITY.es.md`](docs/original/SECURITY.es.md). The Spanish original is authoritative.

- No secrets in profiles or versions.
- Logs must not contain sensitive content.
- Principle of least privilege (API keys kept outside the repository, in a local `.env`).
- Export/import with strict schema validation.
