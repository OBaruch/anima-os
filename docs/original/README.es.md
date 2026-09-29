# Persona Console

GUI para **configurar, versionar y evaluar** “personalidades operativas” de **agentes IA** / personajes ficticios.

## Guardrails (no negociables)
- **Solo agentes IA / personajes ficticios**. Prohibido modelar/optimizar para **personas reales**.
- Prohibido: manipulación, persuasión encubierta, ingeniería social.
- Transparencia: la app debe mostrar **qué parámetros** cambian y **cómo** afectan el prompt/comportamiento.
- Reversibilidad: versionado, diff, rollback, auditoría.
- Seguridad: no exponer secretos; logs sin datos sensibles; permisos mínimos.

## MVP (7–14 días)
- UI Web (Next.js): sliders OCEAN + estilos + restricciones + preview del prompt.
- Perfiles versionados + export/import.
- Runner de evaluación con escenarios + métricas básicas.
- Docs: ETHICS.md + SECURITY.md.

## Estructura
- `personalities/` perfiles generados (`.md` + `.json`)
- `eval/` escenarios y runner
- `app/` UI
