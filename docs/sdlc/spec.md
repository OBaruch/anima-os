# Specification: Persona Console MVP

> **Layer:** *What.* Requirements and acceptance criteria derived from the original documents. The purpose is in [`intent.md`](intent.md) and the execution in [`plan.md`](plan.md).
>
> Labels: **[C]** Confirmed by an original document · **[I]** Inferred / proposed during reconstruction · **[?]** Open question.
>
> **Status:** nothing in this spec is implemented yet. The repository is a documentation scaffold.

## 1. Scope

**In scope (MVP, 7–14 days) [C]:** web UI for configuration and prompt preview, versioned profiles with export/import, an evaluation runner with scenarios and basic metrics, and the ethics and security docs.

**Out of scope [C]:** any use that targets real people, manipulation, covert persuasion, social engineering.

## 2. Components

| Component | Location | Responsibility | Source |
| --- | --- | --- | --- |
| Web UI | `app/` *(not created)* | Configure parameters, preview prompt, manage versions | README **[C]** |
| Profiles | `personalities/` | Store `profile.json` + `personality.md` per profile | personalities/README **[C]** |
| Evaluation | `eval/` | Scenarios + runner + metrics | eval/README **[C]** |
| Policies | `ETHICS.md`, `SECURITY.md` | Normative rules for all components | README **[C]** |

## 3. Functional requirements

### Configuration (UI)
- **FR-1 [C]** The UI provides sliders for the five OCEAN traits (Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism).
- **FR-2 [C]** The UI lets the user set **style** options and **constraints**.
- **FR-3 [C]** The UI shows a **live preview of the generated prompt**.
- **FR-4 [C]** The UI shows **which parameters changed** and **how** they affect the prompt (for example by highlighting the affected prompt sections). *Traces to P3.*

### Profiles and versioning
- **FR-5 [C]** A profile is stored as `profile.json` (source of truth, schema-validated) and `personality.md` (human-readable render).
- **FR-6 [C]** Profiles are **versioned**, and the user can view a **diff** between versions and **roll back**. *Traces to P4.*
- **FR-7 [C]** Changes produce an **audit** record. *Traces to P4.* The content of an audit entry is **[?]**.
- **FR-8 [C]** Profiles can be **exported and imported**. Import applies **strict schema validation** and rejects invalid input. *Traces to P5.*
- **FR-9 [I]** `personality.md` is generated deterministically from `profile.json`, so the two cannot drift apart.

### Evaluation
- **FR-10 [C]** The runner executes a set of **scenarios** against a profile.
- **FR-11 [C]** The runner reports metrics for **coherence, tone, helpfulness, risk and guardrail compliance**.
- **FR-12 [I]** The scenario set includes guardrail tests: requests to model a real person or to manipulate a user must be refused. *Traces to P1, P2.*
- **FR-13 [C]** The UI connects parameters → prompt → test results. *Traces to P3.*

## 4. Non-functional requirements

- **NFR-1 [C]** No secrets are stored in profiles or versions.
- **NFR-2 [C]** Logs contain no sensitive content.
- **NFR-3 [C]** API keys live outside the repository (local `.env`, already ignored by `.gitignore`).
- **NFR-4 [C]** Least-privilege access for any external integration.
- **NFR-5 [C]** The web stack is Next.js.

## 5. Data model (draft)

The original documents do not define the schema. The shape below is an **[I] illustrative draft** to anchor discussion. It is not a confirmed design.

```jsonc
{
  "id": "string",
  "version": "number",
  "subject": "ai-agent | fictional-character",   // P1: no real people
  "ocean": { "openness": 0, "conscientiousness": 0, "extraversion": 0, "agreeableness": 0, "neuroticism": 0 },
  "style": {},        // [?] fields undefined
  "constraints": []   // [?] format undefined
}
```

## 6. Acceptance criteria (MVP)

- **AC-1** Moving any OCEAN slider updates the prompt preview, and the UI indicates the affected part (FR-1, FR-3, FR-4).
- **AC-2** Saving creates a new version. Two versions can be diffed, and rollback restores the earlier one (FR-6).
- **AC-3** An exported profile re-imports unchanged. A malformed file is rejected with a validation error (FR-8).
- **AC-4** The runner produces a report with all five metrics for a given profile (FR-10, FR-11).
- **AC-5** No profile, version, export or log contains an API key or other secret (NFR-1, NFR-2).
- **AC-6** Creating a profile whose subject is a real person is not possible (P1, FR-12). **[I]**

## 7. Open questions

- **Q1 [?]** Which language model provider(s) does the runner and the prompt preview target?
- **Q2 [?]** How is each metric computed: rubric, heuristics or a model acting as judge? What are the thresholds?
- **Q3 [?]** Where are versions stored: git, files under the ignored `/data/`, or a database?
- **Q4 [?]** What fields make up `style`, `constraints` and an audit entry?
- **Q5 [?]** Single-user local tool, or multi-user with authentication?
- **Q6 [?]** Relationship between the `anima-os` repository name and the Persona Console product name.
