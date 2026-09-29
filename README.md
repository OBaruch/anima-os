# Persona Console (`anima-os`)

> A planned web GUI to **configure, version and evaluate "operational personalities"** for **AI agents and fictional characters**, with ethics and security guardrails defined up front.

**Status:** early scaffold / design stage. The repository has documentation and a planned folder layout. It does **not** have application code yet.

---

## Project Overview

Persona Console is meant to be a tool for designing the *personality* of an AI agent in a transparent and reversible way. You adjust personality parameters (Big Five / OCEAN traits, communication style, constraints), see the prompt they produce, keep every change versioned, and check the result against evaluation scenarios.

The repository was started on **2026-02-11** with two commits: a documentation scaffold and a `.gitignore`. It holds the project's vision, its non-negotiable guardrails, an MVP scope, and the planned directory layout.

## Project Context

| Aspect | Value | Evidence level |
| --- | --- | --- |
| Project origin | **Personal Project**, at the concept / scaffold stage | Inferred |
| Author | Baruch Lopez | Confirmed (git history) |
| Created | 2026-02-11 | Confirmed (git history) |
| Original language of docs | Spanish | Confirmed |
| Academic context | None found | Unknown. The repository has no reference to a course or institution |

The repository has no university, course or assignment material. The scaffold reads as a self-defined product plan (an MVP with a 7–14 day timebox), so a personal project is the most reasonable reading. This cannot be fully confirmed. See [`docs/project-context.md`](docs/project-context.md).

## Problem Statement

People who build AI agents often shape personality through hand-edited prompts. This has three problems:

- **Opaque:** it is hard to see which setting causes which behavior.
- **Irreversible:** there is no history, diff or rollback.
- **Unevaluated:** nobody checks tone, coherence or guardrail compliance in a systematic way.

*(Inferred from the stated guardrails and MVP. The original documents do not state the problem explicitly.)*

## Objective

The original README states the goal: a GUI to **configure, version and evaluate** operational personalities of AI agents and fictional characters, under these non-negotiable guardrails:

- **Scope:** AI agents and fictional characters only. Modeling or optimizing for **real people** is forbidden.
- **No manipulation:** covert persuasion and social engineering are forbidden.
- **Transparency:** the app must show *which* parameters change and *how* they affect the prompt and behavior.
- **Reversibility:** versioning, diff, rollback and audit trail.
- **Security:** no exposed secrets, no sensitive data in logs, least privilege.

## Repository Structure

```
anima-os/
├── README.md               # This file (English)
├── ETHICS.md               # Ethical scope and prohibitions (English translation)
├── SECURITY.md             # Security rules (English translation)
├── AGENTS.md               # Working rules for AI coding agents / contributors
├── .gitignore              # Original ignore rules (Node/Next.js, env, logs, /data/)
├── personalities/          # Planned: versioned personality profiles (.json + .md)
│   └── README.md
├── eval/                   # Planned: evaluation scenarios and runner
│   └── README.md
└── docs/
    ├── project-context.md          # Origin, evidence and scope of the project
    ├── possible-improvements.md    # Observed gaps. Not applied.
    ├── sdlc/
    │   ├── intent.md               # Why: purpose, users, principles
    │   ├── spec.md                 # What: requirements and acceptance criteria
    │   └── plan.md                 # How / when: phased MVP plan
    └── original/                   # Original Spanish documents, unmodified
```

The original README also mentions an `app/` folder for the UI. **That folder was never created**, so it is not in the tree.

## Original Implementation

This repository preserves the original state of the project. **No application source code exists yet.** The only original artifacts are the planning documents and the `.gitignore`. The documents are kept verbatim in [`docs/original/`](docs/original/) and the `.gitignore` is unchanged at the root.

This repository preserves the original implementation of the project. The original content has intentionally not been rewritten or modernized, so that the historical context and the original development approach are kept.

## Technologies

| Technology | Status | Source |
| --- | --- | --- |
| Next.js (web UI) | **Planned** | Original README ("UI Web (Next.js)") |
| Node.js ecosystem | **Planned** (inferred) | `.gitignore` ignores `node_modules/`, `.next/`, `out/` |
| JSON (profile schema) + Markdown (human-readable render) | **Planned** | `personalities/README.md` |
| Big Five / OCEAN personality model | **Planned** (as UI sliders) | Original README |

No language model provider, database, test framework or package manifest has been chosen or committed yet. The repository does not give enough information to determine them.

## How It Works (intended design)

The flow below is the **planned** behavior described in the original documents. None of it is implemented.

1. **Configure:** the user sets OCEAN sliders, style options and constraints in the web UI.
2. **Preview:** the UI shows the generated prompt and makes clear how each parameter affects it (transparency guardrail).
3. **Version:** each profile is saved as `profile.json` (source of truth) plus `personality.md` (human-readable render) under `personalities/`, with diff, rollback and export/import.
4. **Evaluate:** a runner in `eval/` executes scenarios against a profile and reports basic metrics: coherence, tone, helpfulness, risk and guardrail compliance.

For the full requirements see [`docs/sdlc/spec.md`](docs/sdlc/spec.md).

## Inputs and Outputs (planned)

- **Inputs:** personality parameters (OCEAN traits, style, constraints), imported profiles, evaluation scenarios.
- **Outputs:** versioned profiles (`.json` + `.md`), generated prompts, evaluation results and metrics.

## Running the Project

There is nothing to run yet. The repository has no `package.json`, no application code and no run scripts. No commands, versions or environment variables are documented here, because none can be determined from the repository.

## Documentation

- [Project context](docs/project-context.md): origin, evidence and scope
- [Intent](docs/sdlc/intent.md): purpose, users and guiding principles
- [Specification](docs/sdlc/spec.md): functional and non-functional requirements
- [Plan](docs/sdlc/plan.md): phased MVP plan and current status
- [Possible improvements](docs/possible-improvements.md): observed gaps, intentionally not applied
- [Ethics](ETHICS.md) · [Security](SECURITY.md)
- [Original documents (Spanish)](docs/original/)
- [Agent / contributor guidelines](AGENTS.md)

## Historical Note

This repository was later reorganized and documented to improve readability and to preserve the historical context of the original project. The original Spanish documents were moved unmodified to [`docs/original/`](docs/original/) and translated into English. Intent, spec and plan documents were derived from them. No original content was deleted.
