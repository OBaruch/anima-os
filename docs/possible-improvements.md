# Possible Improvements

> **These suggestions have NOT been applied.** They are kept separate on purpose, so that the original state of the project stays as it was. They are observations made during the later reorganization, not part of the original work.

## Repository

- **Add a license.** The repository has no `LICENSE` file, so reuse rights are undefined.
- **Resolve the naming.** Decide whether the project is `anima-os` or Persona Console, and use one name everywhere.
- **Document `/data/`.** Explain what the ignored `/data/` directory is for, or remove the rule.
- **Create or drop `app/`.** The README refers to an `app/` folder that does not exist.

## Specification gaps (before building the MVP)

- Define the `profile.json` schema formally (for example as a JSON Schema). The security rules require strict validation on import, and that needs a schema.
- Decide how each evaluation metric is measured: rubric, heuristics, or a model acting as judge. Also define pass/fail thresholds.
- Choose the language model provider(s), and define how API keys are loaded under the least-privilege rule.
- Define what "audit" means in practice: who changed what and when, and where that record is stored.
- Make the ethics guardrails enforceable, not only documented. For example, the evaluation scenarios could include refusal tests for real-person modeling or manipulation requests.

See [`sdlc/spec.md`](sdlc/spec.md) and [`sdlc/plan.md`](sdlc/plan.md) for how these gaps are tracked as open questions.
