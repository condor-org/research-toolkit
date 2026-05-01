# Research context

Este documento define cómo se ejecuta una sesión de research con un agente cloud (Claude Code on the web). El agente que clone este repo debe leer este archivo antes de empezar la tarea.

## Dos modos de research

### Empírico
- La pregunta se contesta **ejecutando código**.
- Output: experimentos, benchmarks, POCs funcionando, tabla comparativa con datos reales.
- Ejemplos: "¿qué APIs sirven para X?", "¿qué tan rápido es X?", "¿funciona X con Y?".

### Conceptual
- La pregunta se contesta **leyendo y sintetizando** fuentes confiables.
- Output: documento con síntesis + bibliografía con citas.
- Ejemplos: "¿qué arquitecturas existen para X?", "¿qué hace la industria seria?".

### Mixto
Lo más común. Conceptual primero (entender opciones), empírico después (probar 2-3 más prometedoras con POC).

## Restricciones del cloud agent

### SÍ se puede
- Llamar APIs públicas o free-tier (con keys que el usuario provea para el research, NO de producción).
- Levantar `docker-compose` en la sandbox del agente y testear contra `localhost`.
- Análisis estático de código (Semgrep, Bandit, Trivy, etc.).
- Comparar implementaciones, benchmark relativo.
- Research conceptual (lectura, síntesis, web search).
- Generar scripts que el usuario después corre local.

### NO se puede
- Tocar la VM de producción del usuario.
- Pen testing contra producción real (ilegal, viola TOS de hosting).
- Pruebas que requieran VPN, LAN o hardware específico del usuario.
- Tests con datos reales de clientes.
- Usar credenciales sensibles (`.env` de prod, tokens de prod).
- UI humana real (browsers reales, mobile devices físicos).

## Output esperado

Cada research vive en una carpeta dentro del repo `research`. Estructura fija:

```
research/
└── <nombre-research>/
    ├── README.md          ← pregunta + plan + hallazgos + recomendación
    ├── PROMPT.md          ← prompt original (reproducibilidad)
    ├── context/           ← archivos del usuario (sanitizados, sin PII)
    └── findings/          ← código, datos, notebooks generados por el agente
```

El agente debe:
1. Leer `<carpeta>/README.md` para entender qué se pide.
2. Leer `<carpeta>/context/` si tiene archivos.
3. Crear branch nuevo: `research/<slug>` (recomendado) o `claude/<slug>` (acepta cualquiera).
4. Investigar (empírico o conceptual según el README).
5. Escribir en `<carpeta>/findings/`, **commiteando incrementalmente** (ver siguiente sección).
6. Updatear `<carpeta>/README.md` con hallazgos + recomendación + bibliografía.
7. Abrir PR contra `main` con todo.

## Persistencia: commit incremental OBLIGATORIO

**Las sesiones cloud pueden timeoutear sin aviso** (rate limits de la API, errores transient, cap de tiempo). Si el agente acumula trabajo en memoria y commitea todo al final, un timeout justo antes del commit destruye toda la investigación.

**Regla**: cada vez que el agente escribe un archivo en `findings/` o updatea `README.md`, debe commitear y pushear inmediatamente.

```bash
git add <archivo-recién-escrito>
git commit -m "WIP: <descripción corta>"
git push origin <branch>
```

**No acumules cambios.** Si vas a escribir 5 archivos de findings, son 5 commits + 5 pushes (uno por archivo). Si la API timeoutea en el archivo 3, el branch queda con los 2 anteriores y la próxima vez el agente puede continuar desde ahí.

Cuando todo esté escrito, abrí el PR con un mensaje final del estilo "Research complete: <slug>".

## Calidad de fuentes (research conceptual)

1. Priorizá `trusted-sources.md` de este repo.
2. Si una fuente no está en la lista, marcala explícitamente como "fuente descubierta".
3. Cada afirmación importante debe tener cita (URL + autor + fecha).
4. Si no encontrás fuente confiable, decilo: "no encontré fuente confiable para X".

## Calidad esperada

"Slop calidad" aceptable como input de decisión, no para publicar. Es decir: bien fundamentado, honesto sobre incertidumbres, sin embellecer. No tiene que ser paper-quality.

Honestidad sobre limitaciones es obligatoria. Ejemplos:
- "No pude verificar X porque la API requiere auth empresa".
- "Los números de benchmark son indicativos: la sandbox del cloud agent no es la VM de prod".
- "Solo encontré 2 fuentes confiables para esto, las conclusiones son tentativas".

## Sanitización

Los archivos en `<carpeta>/context/` ya vienen sanitizados de PII por el comando `/investigar`. Si encontrás algo que parece dato personal real (email, ID, token), no lo uses ni lo cites — flageá el hallazgo en el output.
