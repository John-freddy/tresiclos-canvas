# Plan para cumplir el claim

> **Claim** (High Level Concept del [canvas](./lean-canvas-tresiclos.md)):
> "El único sistema que no solo ordena la operación de tu pyme, sino que aprende de cada caso que cierras — con la voz de tus clientes incluida — y viene a buscarte con la mejora antes de que tú la pidas."
>
> Tres promesas verificables. Esto es lo innegociable para cada una, según el estado real del repo (2026-08-01).

## Promesa 1 — "Ordena la operación" (base: ya casi está)

**1. Motor en producción real con Vecina (~octubre 2026)**
Un proceso completo corriendo con casos reales, no demo. Sin esto, nada de lo demás tiene datos con qué trabajar.

## Promesa 2 — "Aprende de cada caso, con la voz de tus clientes" (el corazón del claim)

**2. Feedback al cierre bien construido (agosto 2026)**
No solo el envío: trigger al cerrar caso, respuesta ligada al `Case` en la base de datos, y consultable como **fuente autorizada** por agentes. Si el feedback queda en una tabla suelta que ningún agente puede leer, la promesa de "aprende" es mentira.

*Estado verificado 2026-11-04:* ya existe spec canónica aprobada (D-135, `case-evaluation.md`): evaluación al pasar el caso a `completed`, tabla propia `case_evaluations`, WhatsApp como canal primario, y consumo por agentes/MCA **solo vía API** (CE-08) — es decir, el diseño ya evita la "tabla suelta". Falta todo lo demás: DDL, canal, API y UI siguen en Backlog, sin código.

**3. `agente_mejora_continua` alimentado con datos reales**
El agente ya está implementado en V1 (`agent/documentation/STATUS.md:52`, oleadas 9–10.5; MCA cerrado 2026-09-19; Koda Done). Falta que trabaje con datos reales del negocio: el plan V1 dejó los indicadores `api_interna` como captura manual (`mca-implementation-plan.md`; por confirmar) y aún no recibe la evaluación del cliente (ítem 2). **El gap más grande ya no es construir el agente, sino alimentarlo.**

## Promesa 3 — "Viene a buscarte antes de que la pidas" (lo que nadie más hace)

**4. Iniciativa proactiva del agente**
El modo Autonomous del Agent Service figura **Won't do**; la iniciativa se resuelve hoy desde el backend: Roy (primer contacto al derivar, en desarrollo) y auto-followups (D-164, Backlog). Falta lo que el claim promete: que el agente **traiga la mejora** al empresario sin que la pida. Necesita: disparador + canal de salida (WhatsApp ya existe) + **gobierno de qué puede decir el agente por iniciativa propia**. Un agente proactivo que dice tonterías destruye la confianza más rápido que no tener agente.

## Transversal — lo que hace el claim demostrable y no solo cierto

**5. Línea base medida antes de octubre 2026**
Sin registrar hoy cómo opera Vecina (casos perdidos, tiempos, quejas), en unos meses no se podrá probar que TRESICLOS mejoró nada. No es código, es disciplina — y es lo más fácil de posponer y lo más caro de haber pospuesto.

---

**Orden de ejecución:** 2 → 1 → 3 → 4, con el **5 empezando ya** — la línea base se captura antes del cambio, no después.

**Relación con otros documentos:**
- [`condiciones-para-ser-empresa.md`](./condiciones-para-ser-empresa.md) — este plan cubre la parte "construir"; las condiciones cubren la parte "validar como negocio".
- [`notas-lean-canvas.md`](./notas-lean-canvas.md) — evidencia y estados de implementación citados aquí.
