# Intent: Persona Console

> **Layer:** *Why.* This file captures the purpose behind the project. It is derived from the original documents in [`../original/`](../original/) and changes rarely. The **What** lives in [`spec.md`](spec.md) and the **How / When** in [`plan.md`](plan.md).
>
> Labels: **[C]** Confirmed by an original document · **[I]** Inferred · **[?]** Unknown.

## Purpose

Give builders of AI agents a **transparent, reversible and testable** way to design an agent's "operational personality", instead of editing prompts by hand. **[C]** from the original README goal and **[I]** for the framing against hand-edited prompts.

## Intended users

- Developers and designers of **AI agents** and **fictional characters**. **[C]** scope, **[I]** audience.

## Outcomes sought

1. A user can **configure** a personality using understandable parameters (OCEAN traits, style, constraints). **[C]**
2. A user can **see** how each parameter changes the generated prompt and behavior. **[C]**
3. Every change is **versioned** and can be diffed, rolled back and audited. **[C]**
4. A personality can be **evaluated** against scenarios for coherence, tone, helpfulness, risk and guardrail compliance. **[C]**

## Guiding principles (non-negotiable)

These principles come directly from the original README, `ETHICS.md` and `SECURITY.md`. They override any feature request.

| # | Principle | Source |
| --- | --- | --- |
| P1 | **Fictional or artificial subjects only.** Never model or optimize for real people. | README, ETHICS **[C]** |
| P2 | **No manipulation.** No covert persuasion, no social engineering, no exploitation of human vulnerabilities. | README, ETHICS **[C]** |
| P3 | **Transparency.** Parameters → generated prompt → tests/results must be visible. | README, ETHICS **[C]** |
| P4 | **Reversibility.** Versioning, diff, rollback, audit trail. | README, ETHICS **[C]** |
| P5 | **Security.** No secrets in profiles, no sensitive data in logs, least privilege, strict schema validation. | README, SECURITY **[C]** |

## Non-goals

- Profiling, predicting or influencing real individuals. **[C]**
- Persuasion optimization or engagement maximization. **[I]** (follows from P2)
- A production multi-tenant platform in the MVP. **[I]** (the MVP is timeboxed to 7–14 days)

## Success looks like

A small, honest tool in which a personality profile is a readable and versioned artifact, its effect on the prompt is visible, and its behavior is checked by repeatable scenarios. **[I]**
