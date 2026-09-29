# Project Context

This document rebuilds the context of the project from the evidence in the repository. Each statement is labeled with one of three levels:

- **Confirmed:** directly supported by files or git history.
- **Inferred:** a reasonable deduction from the available material.
- **Unknown:** cannot be determined from the repository.

## Sources analyzed

The original repository had six files and two commits:

| File | Type | Role |
| --- | --- | --- |
| `README.md` | Documentation (Spanish) | Vision, guardrails, MVP scope, planned structure |
| `ETHICS.md` | Documentation (Spanish) | Permitted scope, prohibitions, transparency rules |
| `SECURITY.md` | Documentation (Spanish) | Security rules |
| `personalities/README.md` | Documentation (Spanish) | Planned profile format |
| `eval/README.md` | Documentation (Spanish) | Planned evaluation module |
| `.gitignore` | Configuration | Ignore rules for a Node.js / Next.js project |

The repository had no source code, PDF, Word, PowerPoint, image, diagram, dataset, notebook, or generated output files. Nothing needed visual (page-by-page) inspection.

Git history (**Confirmed**):

| Commit | Date (UTC) | Author | Message |
| --- | --- | --- | --- |
| `a938e96` | 2026-02-11 07:31 | Baruch Lopez | `chore: scaffold Persona Console (docs + structure)` |
| `524c0c0` | 2026-02-11 07:32 | Baruch Lopez | `chore: add gitignore` |

## Origin

| Question | Answer | Level |
| --- | --- | --- |
| Project type | Personal Project at the Proof-of-Concept / scaffold stage | Inferred |
| University / course / assignment | None referenced | Unknown |
| Motivation | Make AI-agent personality design transparent, reversible and testable, with ethical limits | Inferred from the guardrails |
| Target users | Developers or designers of AI agents and fictional characters | Inferred |

The "personal project" label is an inference. The documents read like a self-directed product plan: a named product, a timeboxed MVP ("7–14 days") and self-imposed ethics and security policies. Nothing mentions a course, a professor, a grade or a deliverable. The repository does not have enough information to confirm this further.

## Objective (Confirmed)

From the original README: a GUI to **configure, version and evaluate "operational personalities"** of **AI agents and fictional characters**.

## Scope

**Confirmed (planned MVP, 7–14 days):**
- Web UI (Next.js): OCEAN sliders, styles, constraints and a prompt preview.
- Versioned profiles with export/import.
- An evaluation runner with scenarios and basic metrics.
- Docs: `ETHICS.md` and `SECURITY.md`. These were the only MVP items delivered.

**Confirmed (out of scope / forbidden):** modeling real people, manipulation, covert persuasion, social engineering, and evaluations that exploit human vulnerabilities.

## Current state (Confirmed)

- Delivered: vision, guardrails, ethics and security policies, planned folder layout, `.gitignore`.
- Not started: the UI (`app/` was never created), the profile schema, profiles, evaluation scenarios, the runner, and any dependency manifest.

## Naming and inconsistencies

- **Repository name vs. product name:** the repository is called `anima-os`, but every document calls the product **Persona Console**. The repository does not explain the difference. Both names are kept as they are.
- **Planned `app/` folder:** the README lists `app/` for the UI, but that folder does not exist.
- **Profile format wording:** the README describes profiles as "`.md` + `.json`". `personalities/README.md` is more specific: `profile.json` (schema, source of truth) and `personality.md` (human-readable render). The two statements agree, and the second is used as the reference.
- **`/data/` in `.gitignore`:** the `.gitignore` excludes a local `/data/` directory that no document mentions. Its purpose is **Unknown**. It may have been meant for local profiles or evaluation outputs.

## Unknowns

- Which language model or provider the prompts and the evaluation runner were meant to target.
- How the metrics (coherence, tone, helpfulness, risk, compliance) were meant to be computed.
- The exact `profile.json` schema.
- Persistence, authentication, and whether the app was meant to be single-user or multi-user.
- Why the repository is named `anima-os`.
