# research-toolkit

Toolkit público para investigación asistida por IA con agentes cloud (Claude Code on the web).

## Para qué sirve

- Define qué tipos de research se pueden ejecutar en cloud agent y cuáles no.
- Cura una lista de fuentes confiables que el agente debe priorizar en research conceptual.
- Acompaña al comando local `/investigar`, que genera prompts que apuntan a este repo.

## Cómo lo usa el cloud agent

Cuando se dispara una sesión cloud con `claude --remote`, el prompt instruye al agente a clonar este repo y leer `CONTEXT.md` antes de empezar. Así el agente arranca con contexto sin que el usuario tenga que pegárselo cada vez.

## Archivos

- `CONTEXT.md` — reglas de research (qué se puede probar, restricciones del cloud agent, modos empírico vs conceptual, formato de output esperado).
- `trusted-sources.md` — fuentes priorizadas para research conceptual.

## Mantenimiento

Cambios en este repo impactan inmediatamente en los próximos researches que dispare `/investigar`. No requiere bumpear versión ni nada — el cloud agent siempre clona la versión más nueva.
