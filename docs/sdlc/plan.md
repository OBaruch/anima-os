# Plan: Persona Console MVP

> **Layer:** *How / When.* The execution plan for [`spec.md`](spec.md), in service of [`intent.md`](intent.md).
>
> The original documents only state the MVP scope and a **7–14 day** timebox **[C]**. The phase breakdown below was **derived during the reorganization [I]**. It orders the confirmed scope into verifiable steps and does not add features.

## Current status

| Phase | Status |
| --- | --- |
| 0. Foundations (vision, guardrails, policies, layout) | **Done.** Commits `a938e96`, `524c0c0` (2026-02-11) |
| 0b. Repository reorganization and SDLC docs | **Done.** English docs, `docs/original/`, intent/spec/plan |
| 1. Decisions and schema | Not started |
| 2. Profiles and versioning | Not started |
| 3. Web UI | Not started |
| 4. Evaluation runner | Not started |
| 5. Hardening and review | Not started |

## Phases

### Phase 1: Decisions and schema
- Answer open questions Q1–Q5 in the spec and record each decision in the spec.
- Define the `profile.json` JSON Schema, including a `subject` field that is restricted to AI agents and fictional characters (P1).
- Scaffold the Next.js project in `app/` (the only stack decision confirmed by the original docs).
- **Done when:** the schema validates sample profiles and rejects malformed ones (prepares AC-3).

### Phase 2: Profiles and versioning (FR-5 to FR-9)
- Deterministic renderer from `profile.json` to `personality.md`.
- Version storage, diff, rollback and audit entries.
- Export/import with strict validation.
- **Done when:** AC-2 and AC-3 pass.

### Phase 3: Web UI (FR-1 to FR-4, FR-13)
- OCEAN sliders, style and constraint editors.
- Live prompt preview that highlights the effect of each parameter.
- Version history view (diff and rollback).
- **Done when:** AC-1 passes.

### Phase 4: Evaluation runner (FR-10 to FR-12)
- Scenario format and a first scenario set in `eval/`, including guardrail refusal scenarios.
- Metric computation for coherence, tone, helpfulness, risk and compliance, following the Q2 decision.
- Show results in the UI next to parameters and prompt.
- **Done when:** AC-4 and AC-6 pass.

### Phase 5: Hardening and review (NFR-1 to NFR-4)
- Check for secrets in profiles, exports and logs. Load API keys only from the local `.env`.
- Review against `ETHICS.md` and `SECURITY.md`.
- **Done when:** AC-5 passes and every principle P1–P5 traces to at least one passing check.

## Working agreements

- Each change traces back to a requirement ID in the spec. If the scope changes, update `spec.md` first, then this plan.
- Guardrails (P1–P5) are acceptance gates, not backlog items.
- The original documents in `docs/original/` are never edited.
- See [`AGENTS.md`](../../AGENTS.md) for the rules that apply to automated coding agents.
