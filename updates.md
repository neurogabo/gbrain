# Estado y actualizaciones del repositorio

Repositorio: [neurogabo/gbrain](https://github.com/neurogabo/gbrain). Público; fork. Rama predeterminada: `master`.

**Revisión del 2026-10-07 06:01:53, America/Mexico_City: no hubo actualizaciones**. Cobertura **completa** del intervalo desde 2026-10-06 06:03:14 America/Mexico_City. Se conserva el último resumen sustantivo y sus pendientes. La publicación anterior, que solo modificó updates.md, se excluye como novedad.

## Estado actual y punto para retomar

Fork público de GBrain: memoria y conocimiento para agentes, con ingestión, recuperación híbrida, síntesis y grafo. La versión declarada es **0.42.25.0**. El proyecto ofrece CLI y servidor MCP, con motores PGLite y Postgres; su documentación distingue la base de datos elegida (brain), las fuentes que contiene y los permisos de llamadas locales o remotas. No hay evidencia consultada de una instalación operativa propia de neurogabo. Las cifras y experiencias de producción del README pertenecen al proyecto upstream descrito allí.

**Por dónde retomar:** leer [CLAUDE.md](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/CLAUDE.md) para la arquitectura y [TODOS.md](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/TODOS.md) para el backlog heredado; localizar después el archivo concreto en [KEY_FILES.md](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/docs/architecture/KEY_FILES.md). Para trabajo sobre costes, el punto concreto pendiente es el uso de la tabla canónica desde el rastreador de presupuesto. Para fiabilidad, revisar el seguimiento de recuperación del gateway y el ciclo de vida de conexiones. Cotejar cada tarea con su anotación de estado antes de implementarla: las casillas históricas no equivalen todas a trabajo abierto.

## Cambios integrados y trabajo en otras ramas

El contraste del intervalo no añade cambios sustantivos. El resumen siguiente describe el estado conservado de la revisión anterior.

**En master:** el último cambio sustantivo unifica los precios de modelos de chat en src/core/model-pricing.ts y deriva de allí varias tablas consumidoras. Los cambios inmediatamente anteriores enrutan la toma y renovación de locks al pool de sesiones, añaden prioridad de CPU para trabajadores y corrigen propiedad y desconexión del singleton de Postgres. Se cotejaron los diffs con el código y las notas de versión; no se ejecutaron esas funciones. Los precios son datos versionados, no tarifas actuales verificadas.

**Conciliación de evaluación:** TODOS.md conserva tres casillas P0 originales por trazabilidad, pero su sección D1 declara incorporados el comando eval gate y la conexión de la sonda nocturna. El código actual contiene el despacho a eval-gate.ts y la llamada a runNightlyQualityProbe desde autopilot. La sonda requiere su opción enabled; su existencia no acredita activación o ejecución. La captura por defecto y su endurecimiento de privacidad permanecen diferidos en el propio backlog. Esta aclaración de la revisión inicial del 2 de octubre corrige la lectura anterior de las casillas; no describe una implementación nueva.

Solo se encontró una rama remota, master; no hay trabajo en otras ramas del fork que conciliar.

**Último cambio sustantivo de Git verificado:** 2026-06-04 00:00:11 America/Mexico_City (UTC−06:00); [9a0bae8d62](https://github.com/neurogabo/gbrain/commit/9a0bae8d62cdd1e0dd6655e24e082fe6c69c5dac), «v0.42.25.0 fix(pricing): unify chat-model pricing into one canonical source; add Opus 4.8 (#1819) (#1827)»; cambio sustantivo documentado en `master`. Este criterio usa fecha de commit y cambios reales de archivos, no la fecha pushed_at del repositorio.

## Pendientes y bloqueos documentados

TODOS.md contiene **281 casillas sin marcar**, con duplicados y seguimientos históricos; esta cifra no representa 281 tareas vigentes distintas. Se conserva el backlog completo en su fuente y no se da por cerrado un punto solo porque haya desaparecido o porque exista un arreglo cercano.

- **Evaluación:** sigue documentada como pendiente la captura por defecto con garantías de privacidad. El gate y la conexión de la sonda tienen evidencia explícita de incorporación, aunque sus casillas originales permanezcan abiertas. No son prueba de una evaluación ejecutada en este fork.
- **Costes:** la unificación de tablas no completa el soporte del rastreador para modelos ajenos a Anthropic. El propio TODO lo marca parcialmente atendido y el código conserva consultas a ANTHROPIC_PRICING. Quedan además normalización de identificadores, manejo de mayúsculas, pruebas de rutas negativas y precios de presentación de proveedores.
- **Fiabilidad:** se conservan el replay del historial tool-result al reanudar el gateway (P1), la propiedad del singleton con reconexiones concurrentes (P2), el refresco de pools y el drenado de colas antes de desconectar (P3). El arreglo de propiedad de conexiones no cierra esos seguimientos separados.
- **SkillOpt y actualización:** persisten los seguimientos de best.md en modo sin mutación, tamaño del pool directo, firma/checksum antes de actualizar y drenado de solicitudes durante una actualización.
- **Otras familias registradas:** indexación y recuperación de código, aislamiento entre fuentes y permisos, paridad de motores y cliente remoto, cobertura de evaluación, mantenimiento y observabilidad. Usar las entradas originales para alcance y prioridad; no se asignan aquí responsables ni fechas nuevos.

Los pendientes heredados no implican que neurogabo haya aceptado ejecutarlos. No se encontró un bloqueo adicional de acceso al repositorio.

## PR, issues y comprobaciones

Se enumeraron con paginación 0 PR (0 abiertos, 0 integrados y 0 cerrados sin integración) y 0 issues (0 abiertos).

No se encontraron releases publicadas en la respuesta de GitHub.

No se encontraron ejecuciones de GitHub Actions en la respuesta consultada. No se ejecutaron aplicaciones, pruebas ni despliegues.

## Evidencia y alcance

Se enumeró de nuevo 1 rama remota y se contrastaron sus puntas con la última revisión completa. Se leyeron updates.md antes de la revisión, las instrucciones aplicables y 72 fuentes de texto pertinentes. Se inspeccionó el diff real de 1 commit del intervalo: 1 modifica exclusivamente updates.md. Se paginaron PR, issues y releases, y se comprobaron las ejecuciones recientes de Actions y el intervalo desde el corte anterior. Se conservaron los datos de fuentes históricas cuyo contenido permanece anclado por su SHA. No se ejecutaron pruebas, aplicaciones ni despliegues.

El alcance es el estado del repositorio y su documentación: no certifica que cada casilla histórica sea una incidencia reproducible, no revalida todos los resultados de evaluaciones heredadas y no supone una auditoría de seguridad línea por línea. Los hallazgos de permisos o seguridad del backlog se conservan como documentados; no se probaron contra servicios.

Las afirmaciones externas conservan el alcance y la fecha de su fuente. Esta revisión no certificó servicios vivos, hardware ni resultados clínicos. Los commits que solo modifican updates.md se excluyen como novedades y de la fecha del último cambio sustantivo.

- [TODOS.md](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/TODOS.md).
- [CHANGELOG.md](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/CHANGELOG.md).
- [Arquitectura y orientación](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/CLAUDE.md).
- [Índice de archivos](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/docs/architecture/KEY_FILES.md).
- [Versión declarada](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/VERSION).
- [Despacho de eval gate](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/src/commands/eval.ts).
- [Sonda en autopilot](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/src/commands/autopilot.ts).
- [Configuración de la sonda](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/src/core/config.ts).
- [Tabla canónica](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/src/core/model-pricing.ts).
- [Rastreador de presupuesto](https://github.com/neurogabo/gbrain/blob/4a1fed4f8ad85da6c66d3fa3049c9d0210f3c1a3/src/core/budget/budget-tracker.ts).

<details>
<summary>Referencias de todas las ramas al revisar</summary>

| Rama | Commit auditado |
| --- | --- |
| `master` (predeterminada) | [c01c091fce](https://github.com/neurogabo/gbrain/tree/c01c091fce67e0b5a187b2f3b226b21daadce7c9) |

El commit anterior del informe se incluye como referencia observada, pero no cambia la fecha del último cambio sustantivo. Los resúmenes de ramas conservan su distinción entre trabajo integrado y pendiente.

</details>

<!-- audit-state
{
  "schema": "neurogabo-updates/v1",
  "owner": "neurogabo",
  "repo": "gbrain",
  "reviewed_at": "2026-10-07T12:01:53.937Z",
  "timezone": "America/Mexico_City",
  "coverage": "completa",
  "initial": false,
  "last_complete_review_at": "2026-10-07T12:01:53.937Z",
  "last_complete_refs": {
    "master": "c01c091fce67e0b5a187b2f3b226b21daadce7c9"
  },
  "observed_refs": {
    "master": "c01c091fce67e0b5a187b2f3b226b21daadce7c9"
  },
  "default_branch": "master",
  "audited_default_sha": "c01c091fce67e0b5a187b2f3b226b21daadce7c9",
  "last_substantive_commit": "9a0bae8d62cdd1e0dd6655e24e082fe6c69c5dac",
  "last_substantive_commit_at": "2026-06-04T06:00:11Z",
  "events": {
    "pulls": [],
    "issues": [],
    "releases": [],
    "workflow_runs": []
  },
  "ignore_report_only_commits": true,
  "interval_from": "2026-10-06T12:03:14.021Z",
  "report_only_commits_excluded": [
    "c01c091fce67e0b5a187b2f3b226b21daadce7c9"
  ],
  "completed_prior_partial": true,
  "coverage_scope": "Estado documental, ramas, historial pertinente y eventos de GitHub; sin reproducir experimentos ni validar servicios externos."
}
-->
