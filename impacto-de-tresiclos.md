# Impacto de TRESICLOS — qué está hecho y qué está planeado

> Documento base: antes de hablar de pitch, entender **qué cambia TRESICLOS en una empresa**. Separa lo **hecho** (código en dev), lo **parcial** y lo **planeado**.
> Verificado el 2026-11-04 contra los `STATUS.md` de backend, frontend y agent. Donde dice "sin verificar", no se leyó el código.

> **Vista por capacidades** (lo que se hace por la empresa, por reto): [`capacidades-de-tresiclos.md`](./capacidades-de-tresiclos.md). Este documento queda como anexo de funcionalidades y estado.

**Dato que condiciona todo:** hoy TRESICLOS corre en **desarrollo**; ninguna empresa lo usa en producción (según la memoria del proyecto: solo se usa la BD de dev). El impacto medido hasta ahora es **ninguno**: lo que sigue es capacidad construida, no resultado.

---

## 1. Lo hecho — qué puede hacer una empresa con TRESICLOS en dev

| Frente | Qué permite | Estado |
|---|---|---|
| Operar procesos | Diseñar procesos con versiones; ejecutar casos y actividades con SLA, asignación e historial inmutable | Hecho |
| Trabajo diario | Tareas y proyectos libres + actividades de proceso en un solo centro (`/workbox`) | Hecho (Task/Project Manager, oleadas 0–8) |
| Atender clientes | Inbox WhatsApp en tiempo real, multimedia, humano e IA conviviendo, contactos | Hecho |
| Vender | CRM (contactos, empresas, oportunidades), embudo kanban, derivar oportunidad, metas comerciales MVP | Hecho; asignación y derivación comercial por IA en código, prueba en dev pendiente (D-197) |
| Agentes IA | Workbench: crear agentes, bases de conocimiento, herramientas, permisos mínimos. Natalia (agente comercial por WhatsApp) cerrada funcionalmente en dev (2026-07-28) | Hecho; Roy (primer contacto al derivar) en desarrollo |
| Saber cómo va | Centro de Análisis (tableros, semáforo, constructor, metas), Bodega de archivos, Content Library | Hecho |
| Mejorar | MCA V1 (cerrado 2026-09-19): mejoras, indicadores, iniciativas, actas; `agente_mejora_continua` (lectura, hallazgos, acta confirmada); Koda, el copilot conversacional | Hecho en V1 |
| Automatizar | Automatizaciones por evento, manual, horario y fecha relativa | Parcial: la acción "agente" está en Backlog |

## 2. Lo planeado — sin código o bloqueado

- **Evaluación del cliente al cierre** (D-135): spec aprobada; tabla, canal, API y UI en Backlog.
- **Motor ejecutando actividades por agente** (`ai_task`): Blocked (D-010). Hoy los agentes operan casos por tools en modo conversacional.
- **Iniciativa proactiva:** el modo Autonomous del Agent figura Won't do; auto-followups (D-164) en Backlog.
- **Centro de control de agentes** (AI Control Tower): solo visión; existe parte: el ámbito Trazas del workbench.
- **Agente contextual en cada módulo** (FE-051) y multi-agente/voz (FE-052): pendientes.
- **Pruebas sistemáticas de agentes:** hoy solo guías manuales por dominio.
- **Indicadores MCA alimentados por el propio sistema:** el plan V1 los dejó como captura manual (por confirmar contra el estado actual).
- **Producción real con un cliente (Vecina):** pendiente.

## 3. Las 12 capacidades (propuesta del análisis del whitepaper, contra el repo)

| # | Capacidad | Estado |
|---|---|---|
| 1 | Objetivos y KPI | Parcial — metas comerciales, indicadores MCA |
| 2 | Responsabilidades | Parcial — roles y asignación para personas; para agentes, sin verificar |
| 3 | Motor de procesos | Hecho |
| 4 | Motor de agentes | Hecho |
| 5 | Trazabilidad | Hecho |
| 6 | Supervisión | Parcial — Trazas; Control Tower solo visión |
| 7 | Evaluación | Backlog |
| 8 | Pruebas | Manual |
| 9 | Análisis | Hecho |
| 10 | Diagnóstico | Hecho en V1 |
| 11 | Gestión de mejoras | Hecho en V1 |
| 12 | Medición de impacto | Parcial — indicadores MCA, sin alimentación automática confirmada |

Lectura: lo construido se concentra en ejecutar, controlar y mejorar; lo que falta son las **entradas** del ciclo (evaluación del cliente, indicadores automáticos) y la **supervisión de agentes** con evidencia.

## 4. Qué cambia en la empresa — hipótesis a medir, no resultados

| Cambio esperado | Hecho que lo apoya | Planeado que lo completa | Cómo se mediría |
|---|---|---|---|
| La operación deja de depender de la memoria de la gente | Procesos, SLA, historial, workbox | — | Casos perdidos o vencidos, SLA cumplido, contra línea base |
| Ningún cliente queda sin respuesta | Inbox, Natalia, traspaso humano↔IA | Roy, auto-followups | Tiempo de primera respuesta; consultas sin atender |
| El dueño ve cómo va sin preguntar | Centro de Análisis, metas comerciales | — | Uso de tableros; decisiones tomadas con ellos (cualitativo) |
| La empresa sabe qué mejorar y lo ejecuta | MCA + agente de mejora continua | Indicadores automáticos + evaluación del cliente | Mejoras cerradas con el indicador movido |
| La voz del cliente entra al sistema | — | Evaluación al cierre (D-135) | Calificación por proceso, tasa de respuesta |
| Los agentes se supervisan con evidencia | Trazas, historial | Control Tower, pruebas sistemáticas | % de resultados aceptados sin corrección |

## 5. Lo que no sabemos

- No hay datos de producción, y no encontré una línea base documentada de Vecina (sin ella no se puede probar impacto).
- Si la lente BSC (Kaplan & Norton) opera como contenido del agente: no aparece en el código del agente (puede vivir como dato en el backend; sin verificar).
- Cuánto del impacto de las filas 2, 4 y 5 depende de lo planeado y aún no construido.

## Siguiente paso

Con esto claro: definir **cómo cambia la vida de una compañía** (a partir de la sección 4). El pitch queda para después.
