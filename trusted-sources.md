# Trusted sources

Fuentes priorizadas para research conceptual. El agente cloud debe consultar primero estas, y solo recurrir a fuentes descubiertas si no cubren un punto (marcándolas explícitamente).

## Cómo se popula este archivo

Hay un baseline inicial curado a mano por dominio técnico. Cada research nuevo puede agregar fuentes que prueben ser útiles 2-3 veces. La curación es manual: si una fuente está acá, es porque aporta señal alta y bajo ruido.

## Formato

Una sección por dominio. Para cada fuente: nombre, URL, autor/origen, y una línea de **por qué es confiable** (autoridad, experiencia, track record).

Las fuentes están ordenadas por relevancia/autoridad dentro de cada sección, no alfabéticamente.

---

## 1. System design & arquitectura de aplicaciones

- [martinfowler.com](https://martinfowler.com) — Martin Fowler, autor de *Patterns of Enterprise Application Architecture* y *Refactoring*; ThoughtWorks chief scientist por décadas. Referencia canónica para patterns y trade-offs arquitecturales.
- [Designing Data-Intensive Applications (DDIA)](https://dataintensive.net) — Martin Kleppmann, ex-LinkedIn/Confluent. El libro que la industria usa como referencia para sistemas distribuidos.
- [High Scalability](http://highscalability.com) — Todd Hoff. Case studies en profundidad de arquitecturas reales (Twitter, Netflix, Stack Overflow, etc.) desde 2007.
- [ACM Queue](https://queue.acm.org) — Publicación peer-reviewed de la ACM con artículos escritos por practitioners senior (Pat Helland, Werner Vogels, etc.).
- [The Architecture of Open Source Applications](http://aosabook.org) — Greg Wilson et al. Capítulos escritos por los mantenedores principales de proyectos OSS reales.
- [AWS Architecture Blog](https://aws.amazon.com/blogs/architecture/) — Casos de uso reales documentados por arquitectos de AWS.
- [Azure Architecture Center](https://learn.microsoft.com/azure/architecture/) — Patterns de Microsoft con trade-offs y diagramas formales.

---

## 2. Bases de datos (énfasis en PostgreSQL)

- [PostgreSQL official docs](https://www.postgresql.org/docs/) — Docs oficiales, mantenidas por el core team. Fuente autoritativa.
- [Use The Index, Luke!](https://use-the-index-luke.com) — Markus Winand. Autoridad mundial en SQL indexing y query optimization (autor de *SQL Performance Explained*).
- [pganalyze blog](https://pganalyze.com/blog) — Lukas Fittl, founder de pganalyze, ex-founding engineer de Citus Data. Profundidad técnica en performance de Postgres.
- [Bruce Momjian's site](https://momjian.us/main/blogs/pgblog.html) — Postgres core team member desde 1996, presentaciones técnicas y artículos.
- [Crunchy Data blog](https://www.crunchydata.com/blog) — Empresa con varios contributors al core de Postgres. Artículos prácticos de operaciones.
- [Citus Data blog](https://www.citusdata.com/blog/) — Adquirida por Microsoft. Especialistas en escalado horizontal de Postgres.
- [Database Internals](https://www.databass.dev) — Alex Petrov, libro canónico sobre cómo funcionan los DB engines por dentro.

---

## 3. Backend / API design

- [Google API Improvement Proposals (AIPs)](https://google.aip.dev) — Reglas formales que Google usa internamente para diseñar APIs. Referencia para REST + gRPC.
- [Google Cloud API Design Guide](https://cloud.google.com/apis/design) — Versión condensada del anterior; orientada a developers que diseñan APIs públicas.
- [Microsoft API Guidelines](https://github.com/microsoft/api-guidelines) — Reglas internas de Microsoft, abiertas en GitHub. Buena referencia para versioning y errores.
- [Stripe API docs](https://stripe.com/docs/api) — Referencia de la industria para developer experience en API design (idempotency, paginación, errores).
- [API Design Patterns (JJ Geewax)](https://www.manning.com/books/api-design-patterns) — Libro de Manning escrito por staff engineer de Google. Cubre patterns más allá de REST básico.
- [IETF HTTP Working Group (HTTPbis)](https://datatracker.ietf.org/wg/httpbis/documents/) — Especificaciones formales de HTTP. Para dudas sobre semantics de método/status, ir acá.
- [REST API Tutorial](https://restfulapi.net) — Buen baseline para fundamentos de REST cuando hace falta refresh.

---

## 4. Frontend / React

- [react.dev](https://react.dev) — Docs oficiales reescritas en 2023 (ex-reactjs.org). Cubre fundamentos y patterns modernos con ejemplos sólidos.
- [overreacted.io](https://overreacted.io) — Dan Abramov, ex-Redux/React core team. Posts profundos sobre el modelo mental de React.
- [Josh Comeau](https://www.joshwcomeau.com) — Educator senior. Posts excepcionalmente bien explicados sobre React, CSS, animación, performance.
- [Kent C. Dodds](https://kentcdodds.com) — Creador de Testing Library, autor de *Epic React*. Foco en testing y patterns prácticos.
- [Patterns.dev](https://www.patterns.dev) — Lydia Hallie + Addy Osmani (Google). Patterns modernos de frontend con ejemplos visuales.
- [Mark Erikson — Redux maintainer](https://blog.isquaredsoftware.com) — Mantenedor principal de Redux. Posts técnicos profundos sobre state management.
- [web.dev](https://web.dev) — Google web platform team. Performance, Core Web Vitals, accesibilidad, PWAs.

---

## 5. DevOps / Infrastructure

- [Brendan Gregg](https://www.brendangregg.com) — Ex-Netflix, Intel. Autoridad mundial en performance, profiling, BPF, Linux internals. Libros: *Systems Performance*, *BPF Performance Tools*.
- [Julia Evans (jvns.ca)](https://jvns.ca) — Zines técnicos sobre Linux, networking, debugging. Excelente para fundamentos.
- [Docker official docs](https://docs.docker.com) — Documentación oficial. Referencia para Compose, networking, build.
- [Kubernetes docs](https://kubernetes.io/docs/) — Docs oficiales con concepts bien estructurados.
- [Tailscale blog](https://tailscale.com/blog) — Networking, mesh VPNs, NAT traversal. Posts técnicos profundos.
- [Honeycomb blog](https://www.honeycomb.io/blog) — Observability moderna (traces, eventos vs logs). Charity Majors et al.
- [DigitalOcean Community](https://www.digitalocean.com/community/tutorials) — Tutoriales tested-and-pragmatic. Bueno para setups concretos en Linux.
- [AWS Builders' Library](https://aws.amazon.com/builders-library/) — Cómo Amazon construye sistemas a escala. Artículos por principal engineers de AWS.

---

## 6. Seguridad de aplicaciones

- [OWASP](https://owasp.org) — Top 10, Cheat Sheets, ASVS. Referencia obligada para web security.
- [Troy Hunt](https://www.troyhunt.com) — Creador de haveibeenpwned.com, MVP de Microsoft. Foco en práctica real (passwords, breaches, headers).
- [Snyk Security blog](https://snyk.io/blog/) — Foco en seguridad de dependencias y supply chain.
- [Cloudflare blog](https://blog.cloudflare.com) — Edge security, DDoS, post-mortems técnicos de incidentes.
- [Krebs on Security](https://krebsonsecurity.com) — Brian Krebs. Periodismo investigativo sobre breaches y threat actors.
- [Google Security Blog](https://security.googleblog.com) — Investigación de seguridad de Google (Project Zero, etc.).
- [NIST SP 800 series](https://csrc.nist.gov/publications/sp800) — Standards formales (auth, crypto, riesgos). Referencia para compliance.
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) — Material de entrenamiento de los creadores de Burp Suite.

---

## 7. Performance & profiling

- [Brendan Gregg — Systems Performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) — Libro canónico para perf en Linux. Su site tiene años de posts sobre flame graphs, BPF, perf.
- [web.dev/learn/performance](https://web.dev/learn/performance/) — Google web perf curriculum oficial.
- [Aleksey Shipilev (shipilev.net)](https://shipilev.net) — JVM performance authority, ex-Oracle/Red Hat. JMH benchmarking y JIT internals.
- [MDN Web Performance](https://developer.mozilla.org/en-US/docs/Web/Performance) — Mozilla, baseline para perf web cross-browser.
- [High Performance Browser Networking](https://hpbn.co) — Ilya Grigorik (Google). Libro free online sobre HTTP/2, TLS, WebRTC.
- [pganalyze 5mins of Postgres](https://pganalyze.com/blog/5mins) — Lukas Fittl. Series semanal de 5 min sobre performance de Postgres.

---

## 8. AI / Coding agents

- [Anthropic Engineering & Research](https://www.anthropic.com/research) — Source of truth para Claude, agentic patterns, MCP, alignment research.
- [Claude Code official docs](https://code.claude.com/docs) — Documentación oficial de Claude Code (CLI, web, hooks, skills, plugins, routines).
- [Simon Willison's Weblog](https://simonwillison.net) — Prolífico, balanced. Tracks LLM developments con experimentos concretos. Su [Agentic Engineering Patterns guide](https://simonwillison.net/guides/agentic-engineering-patterns/) es referencia para coding agents.
- [Every — Chain of Thought](https://every.to/chain-of-thought) — Dan Shipper, Kieran Klaassen. Enfoque en compound engineering y workflows agénticos reales.
- [Model Context Protocol spec](https://modelcontextprotocol.io) — Spec oficial del MCP, el estándar abierto para conectar LLMs con tools/data.
- [OpenAI Engineering](https://openai.com/index/research/) — Posts técnicos del equipo de OpenAI sobre agentes, tools, evals.
- [Andrej Karpathy (karpathy.ai)](https://karpathy.ai) — Ex-OpenAI, ex-Tesla. Videos y posts sobre LLM internals (transformers, training, inference).

---

## 9. Engineering practices

- [martinfowler.com (Refactoring/CI)](https://martinfowler.com) — Cubre también refactoring, CI/CD, microservices. Su libro *Refactoring* (2da ed) es referencia.
- [Charity Majors (charity.wtf)](https://charity.wtf) — Co-founder Honeycomb. Observability + engineering management.
- [Will Larson (lethain.com)](https://lethain.com) — Autor de *An Elegant Puzzle* y *Staff Engineer*. Ingeniería senior y management.
- [The Pragmatic Engineer](https://newsletter.pragmaticengineer.com) — Gergely Orosz. Newsletter #1 de tech en Substack. Práctica real con data de empresas.
- [Software Engineering at Google](https://abseil.io/resources/swe-book/) — Libro free online. Cómo Google maneja code review, testing, dependency management a escala.
- [Continuous Delivery](https://continuousdelivery.com) — Jez Humble y Dave Farley. Libro canónico de CD; el sitio tiene posts y recursos.
- [Kent Beck — TDD/XP](https://tidyfirst.substack.com) — Creador de TDD y Extreme Programming. Su Substack actual sigue activo.
- [Dan Luu](https://danluu.com) — Posts técnicos profundos sobre engineering practices, hardware, debugging.

---

## Notas de uso

- Si una afirmación viene de una fuente acá listada, citala como `[CURATED]: <nombre> (URL)`.
- Si viene de una fuente descubierta en el camino, citala como `[DISCOVERED]: <nombre> (URL)`.
- En el reporte final, separá citas curadas de descubiertas para que el usuario pueda evaluar la procedencia.
