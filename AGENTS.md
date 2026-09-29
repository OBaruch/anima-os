# AGENTS.md

Working rules for AI coding agents and human contributors in this repository.

## Read first
1. [`docs/sdlc/intent.md`](docs/sdlc/intent.md): why the project exists and its non-negotiable principles (P1–P5).
2. [`docs/sdlc/spec.md`](docs/sdlc/spec.md): what to build (requirement IDs and acceptance criteria).
3. [`docs/sdlc/plan.md`](docs/sdlc/plan.md): phase order and current status.

## Rules
- **Guardrails come first.** Only AI agents and fictional characters. No real-person modeling, manipulation, covert persuasion or social engineering. Refuse any task that conflicts with [`ETHICS.md`](ETHICS.md).
- **Spec-driven changes.** Every change references a requirement ID (e.g. `FR-6`). If a change needs new scope, update `spec.md` (and `plan.md`) first.
- **Preserve history.** Never edit files in `docs/original/`. They are the authoritative original documents.
- **Security.** Never commit secrets. Keys stay in a local `.env` (already ignored). Keep sensitive content out of logs. See [`SECURITY.md`](SECURITY.md).
- **Stay honest.** Don't document features as implemented until they exist. Label uncertain claims as Inferred or Unknown.
- **Stay small.** Don't add infrastructure (containers, CI, extra tooling) unless the spec requires it.
