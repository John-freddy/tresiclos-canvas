# Lean Canvas — TRESICLOS

> Lienzo Lean para: TRESICLOS (Plantear Hipótesis, Iterar, Pivotar, Aprender, Escalar)
> **v0.1 — borrador de hipótesis, framework tomado de Vecina Inmobiliaria**
> Leyenda: 🔧 deriva del código/repo · 📌 decisión del fundador (sin validación de mercado) · ⚠️ hipótesis abierta

**Frase JTBD del cliente (hipótesis):**
> "Quiero que mi negocio opere con criterio y trazabilidad aunque yo no esté encima de cada caso."

---

## 1. PROBLEMA — #jtbd (🔧 firme, con hipótesis a validar)

**Marco ampliado (tesis del fundador, 2026-08-01):**
Toda pyme enfrenta a diario dos desafíos en tensión:
- **Administrar eficientemente** lo que ya existe
- **Emprender para crecer** hacia lo que todavía no existe

Y no resuelve ninguno de los dos bien por 4 barreras (observación empírica):
1. **Mindset** — el empresario no tiene el chip para esto
2. **Framework** — no tiene un modelo probado de planeación/ejecución de estrategia
3. **Tech** — no tiene la tecnología para sostenerlo
4. **Acompañamiento** — nadie lo acompaña de forma constante en la ejecución

| Contexto (Cuando...) | JOB (Quiero...) | Outcome (Para...) |
|---|---|---|
| El negocio crece y los procesos (ventas, atención, seguimiento) dependen de personas dispersas, WhatsApp manual y memoria del equipo | Estandarizar y automatizar la operación sin perder trazabilidad ni criterio humano | Escalar sin que la calidad dependa de que "alguien se acuerde" o esté disponible |
| Un caso se cae (cliente sin respuesta, proceso atado a una sola persona) | Tener visibilidad y control real de cada caso en curso | No enterarse del problema cuando ya es tarde |
| Ya probó CRM + bots sueltos sin gobierno | Que el agente IA actúe con límites claros, no como caja negra | Confiar en lo que el agente hizo y por qué |
| Quiere crecer pero el día a día se lo come; no sabe qué mejorar primero ni si lo que cambió funcionó | Que alguien revise lo que está pasando y me traiga la mejora concreta, con evidencia | Emprender para crecer sin soltar la operación ni contratar una consultora |

**Eventos disparadores emocionales:**
"Algo se cayó y ya no puedo seguir operando a pulso." Caso perdido, cliente que se quejó de que "nadie respondió", proceso crítico que dependía de una sola persona.

**Componente emocional**

| ROLL | NECESIDAD alto nivel | EMOCIÓN |
|---|---|---|
| Dueño/responsable de operación de un negocio de servicio | Tener control y visibilidad sin estar encima de cada caso | Tranquilidad ("Bajar Ansiedad") |

---

## 2. SEGMENTO MDO 📌 (decisión del fundador — tomada, pero sin validación de mercado aún)

**Pymes en general** que enfrentan la tensión administrar-eficientemente vs. emprender-para-crecer y carecen de mindset, framework, tech o acompañamiento para resolverla. El vertical inmobiliario (Vecina Inmobiliaria / Royal Inmuebles) es la **puerta de entrada y piloto**, no el límite del mercado.

**Segmento inicial (primeros 10–20 clientes): por definir** (📌 decisión aplazada, 2026-11-15). ⚠️ Criterio candidato: segmentar por **intensidad** comercial, de servicio u operativa, no por tamaño ni sector (una empresa pequeña califica si tiene alguna intensidad alta); falta medirla en Vecina. Hipótesis de partida en la estrategia comercial: inmobiliarias y otros negocios de procesos relativamente sencillos — ver `notas-lean-canvas.md` §6.

**Early adopter:** redes/franquicias de agentes independientes con modelo de confianza territorial ya validado (ej. Vecina Inmobiliaria), que ya sienten el dolor (casos perdidos, dependencia de una sola persona) y tienen presupuesto para resolverlo.

---

## 3. PROPUESTA DE VALOR — PUV

**PUV conceptual:** TRESICLOS normaliza la operación de la pyme y construye su **capacidad de aprender** — combinando tecnología (Process Engine + CRM + Canal + Agentes IA), un framework probado de planeación/ejecución de estrategia y acompañamiento constante, sin quitarle el criterio humano: el agente razona bajo permisos acotados (`allowed_tools`/`allowed_resources`), el motor de procesos valida el resultado, y el humano supervisa.

**Promesa central 📌 (2026-11-15): "Ejecuta y aprende".** Personas y agentes de IA ejecutan los procesos de la empresa con control y trazabilidad, y la empresa aprende de cada caso que cierra. Es la versión corta y verificable del claim de abajo: *ejecuta* es lo que se puede mostrar primero; *aprende* es lo que ningún stack genérico cierra. Estado honesto de "ejecuta": los agentes operan casos por tools en modo conversacional (Natalia); que el motor ejecute actividades por agente (`ai_task`) sigue Blocked.

**High Level Concept (claim largo):** "El único sistema que no solo ordena la operación de tu pyme, sino que aprende de cada caso que cierras — con la voz de tus clientes incluida — y viene a buscarte con la mejora antes de que tú la pidas."

**Palabras clave:** Normalización operativa · Capacidad de aprender · Multi-tenant · Proceso · Agente operativo · Trazabilidad · Contexto operacional completo · Canal (WhatsApp) · CRM · Supervisión humana

**Un mismo valor, tres lenguajes ⚠️** (a validar con compradores reales):

| Interlocutor | Beneficio principal |
|---|---|
| Propietario o gerente | Control de la compañía y menos dependencia de su intervención |
| Director comercial | Mejor atención, seguimiento y ejecución comercial |
| Responsable de operaciones | Procesos que avanzan, menos tareas repetitivas, más trazabilidad |

**Cómo cambia la vida del cliente:** pasa de administrar el caos a supervisar un sistema que ejecuta con criterio — y cada tarea que ve conserva el proceso que la originó, el caso completo, responsables, SLA e historial, no es una tarjeta aislada como en un gestor de tareas genérico.

---

## 4. SOLUCIÓN — mapeada a las 4 barreras (tesis del fundador)

- **Tech** 🔧 firme: Process Engine (casos + actividades end-to-end), CRM + Entity Explorer, Channel Manager (WhatsApp/inbox), Frontend de supervisión humana. Cada actividad conserva su caso, proceso, responsables, SLA e historial inmutable (`Event Occurrence`) — no una tarjeta aislada como en un task manager genérico. Los agentes ya operan casos hoy mediante tools en modo conversacional (ej. Natalia avanza y deriva oportunidades); la ejecución de actividades por el propio motor (`ai_task`) aún no.
- **Framework** — agentes especializados en el modelo de Kaplan & Norton (Balanced Scorecard) para acompañar planeación y ejecución de estrategia. **Implementado en V1** (`agente_mejora_continua`, D-008/D-015: BSC, 4DX, PDCA, Kaizen y Six Sigma como "lentes metodológicas"): lee datos, propone hallazgos y deja actas confirmadas por una persona (MCA V1 cerrado 2026-09-19). Sin verificar: que la lente BSC opere como contenido — ver `impacto-de-tresiclos.md`.
- **Mindset** — agentes IA especializados que acompañan al empresario en el cambio de chip. Parcialmente cubierto por la lente `coaching` del mismo `agente_mejora_continua` (misma salvedad).
- **Acompañamiento** — agentes activos por iniciativa propia (cron) y por demanda, en ejecución y mejora continua. Por demanda ya existe (Koda, copilot MCA). Por iniciativa propia: el modo Autonomous del Agent figura **Won't do**; la iniciativa proactiva se resuelve desde el backend (Roy al derivar una oportunidad, en desarrollo; auto-followups D-164, Backlog).
- **Agentes IA** con responsabilidad operativa acotada (`allowed_tools`/`allowed_resources`) — no chatbots genéricos, en ninguno de los 4 pilares.

**Fase actual:** el núcleo ya está construido en desarrollo; falta probarlo en producción real con un caso (Vecina) y alimentar el ciclo de mejora con datos reales (ver `impacto-de-tresiclos.md`).

---

## 5. CANALES ⚠️ (hipótesis en construcción; el orden de arranque es decisión 📌 del 2026-11-15)

**Orden acordado 📌:** primero Vecina en producción; después, TRESICLOS como tenant de sí mismo (usa TRESICLOS para vender TRESICLOS). El tenant propio genera evidencia comercial y datos reales para el ciclo de mejora.

**Fases (hipótesis; pueden superponerse):**
1. **Primeros 10–20 clientes:** venta directa, acompañamiento cercano e implementación consultiva; objetivo: validar y volver reutilizable lo que se aprenda.
2. **Adquisición y activación asistidas por IA:** Koda (perfil comercial) asume atención, demostración, seguimiento e incorporación, reduciendo la intervención humana.
3. **Escala:** adquisición digital, autoservicio asistido, soluciones prediseñadas, eventualmente socios.

**Fuentes de interesados:** contenido por público (dueño, director comercial, operaciones), publicidad digital, prospección asistida por IA, alianzas y la red territorial de Vecina. Sin fuerza de ventas convencional al inicio. Koda no genera demanda por sí sola: hay que medir qué fuentes producen clientes rentables.

**Estado:** no existe aún Koda comercial, web comercial conectada, tenants de demostración ni cobro automatizado (no aparecen en la documentación del repo). La autonomía comercial completa es un objetivo por validar, no un supuesto. Detalle en `notas-lean-canvas.md` §6.

---

## 6. INGRESOS ⚠️ (mejor hipótesis disponible — sin pricing definido en código/docs, pendiente validar contigo)

La arquitectura es multi-tenant (`accountId`), lo que apunta a cobro por cuenta. Hipótesis de estructura: base fija por tenant + variable ligada al costo real (ejecuciones/tokens de agente IA, que es el costo marginal identificado en Costos). Sin cifras ni tiers definidos aún.

---

## 7. COSTOS 🔧 (firme — deriva de infraestructura observada)

- **Infraestructura:** hosting + PostgreSQL (Supabase) + Redis
- **LLM por ejecución de agente** (OpenAI/Anthropic) — el costo marginal que crece con el uso
- **Equipo** (backend/frontend/agent/mobile)
- **Onboarding/normalización de cada pyme nueva** (setup de procesos, datos, agentes) — debe bajar con cada cliente o el modelo no escala (ver condición #5). ⚠️ Hipótesis para bajarlo: que Koda guíe la configuración por conversación; capacidad nueva, sin verificar
- **Demostraciones por prospecto** (hipótesis): tenant temporal con datos ficticios y créditos de IA limitados (72 h a probar) — consumo de IA por prospecto que no se convierte
- **Control de calidad del agente proactivo** — revisar/gobernar lo que el agente dice por iniciativa propia; costo del pilar Acompañamiento que no aparece en la infraestructura

---

## 8. MÉTRICAS CLAVE ⚠️ (mejor hipótesis disponible — pendiente validar contigo)

> "Si las métricas no capturan la elección consciente de una persona, están mal."

Atadas a los objetos reales del sistema (caso, actividad, outcome):
- **Calificación y opinión del cliente al cierre de cada caso** — al cerrarse un proceso, el sistema pide retroalimentación inmediata (califica + opina). Es la métrica que mejor cumple la regla de arriba: captura la elección consciente de una persona. Complementa la medición de SLA (el SLA mide si se cumplió el tiempo; el feedback mide si valió la pena). **Estado verificado (2026-11-04):** spec canónica aprobada (D-135, `backend/.../case-evaluation.md`, 2026-08-02) y trigger disponible (`case.completed.v1`); implementación (tabla, canal, API, UI) en Backlog, sin código.
- **% de outcomes de agente aceptados por el motor sin corrección humana** — mide autonomía real, no solo actividad
- **Tiempo de ciclo por caso** — eficiencia operativa del Process Engine
- **Cuentas (tenants) activas con al menos un caso en curso** — tracción comercial
- ⚠️ **Contención por proceso** (candidata): % de casos de un proceso resueltos por el agente sin derivar a un humano — mide resultado del proceso, no calidad de una conversación
- ⚠️ **Costo por caso resuelto** (candidata): costo LLM + infraestructura vs. costo humano equivalente; exige línea base

- ⚠️ **Métricas comerciales del tenant propio** (candidatas, desde que TRESICLOS opere como su propio tenant): demostraciones iniciadas/completadas y conversión a cliente · CAC · ingreso recurrente · consumo de IA por prospecto y por cliente adquirido · tiempo humano por venta e implementación · % de actividades comerciales ejecutadas por agentes · tiempo hasta el primer resultado útil del cliente

Las candidatas de contención y costo vienen del nivel "valor empresarial" del marco de medición de Salesforce (eficacia · rendimiento · interacción · valor empresarial) — ver `notas-lean-canvas.md` §5. Se adoptan solo si el piloto confirma que se pueden medir.

Este feedback no es solo métrica: es **insumo para los agentes** — la fuente con la que revisan qué está pasando en la operación (cierra el loop de "capacidad de aprender").

---

## 9. VENTAJA COMPETITIVA ⚠️ (hoy: lo técnico está construido en dev; nada demostrado en producción)

**Construido 🔧:** el agente IA razona pero **no autoriza solo**: el motor de procesos valida outcomes y el backend es la fuente de verdad. Difícil de replicar con un chatbot suelto o un CRM + bot sin gobierno, porque combina motor de procesos propio + gobierno de agentes + multi-tenant real.

**Apuesta ⚠️:** el motor de mejora continua ya existe en código (MCA V1), pero no está demostrado que cambie resultados reales — pasar de "otro SaaS" a "consultoría escalada por agentes" exige datos de clientes: no hay producción, el feedback del cliente no está construido y la proactividad del agente apenas empieza (Roy). La ventaja completa solo existe si el piloto demuestra que una pyme sobre TRESICLOS mejora métricas que la misma pyme con un stack genérico (CRM-WhatsApp tipo Kommo/HighLevel, suite tipo Monday/Zoho/Bitrix24, o CRM vertical inmobiliario tipo Wasi/Tokko) no puede mejorar.

**Evidencia por uso propio ⚠️:** si TRESICLOS vende con TRESICLOS, la ventaja deja de ser solo afirmación: el propio proceso comercial es la demostración. Límite: eso prueba que ejecuta trabajo comercial, no que mejore a *otras* empresas; la validación completa exige clientes distintos con procesos distintos.

En un gestor de tareas genérico (Asana/ClickUp/Notion), una tarea vinculada a un proceso sigue siendo una tarjeta aislada. En TRESICLOS conserva el caso, el proceso que la originó, responsables, SLA e historial auditable — el contexto no se pierde al pasar de "proceso formal" a "trabajo del día a día".

Ningún competidor genérico (Notion, Asana/ClickUp, Zapier/Make, un CRM suelto) resuelve las 4 barreras a la vez — son solo tech. TRESICLOS combina tech + framework de gestión probado (Kaplan & Norton) + acompañamiento activo de agentes: no ordena tareas, construye la capacidad de la empresa de aprender.

---

## ALTERNATIVAS EXISTENTES

No compite contra "otro CRM" o "otro chatbot" sueltos, ni contra suites genéricas de trabajo (Notion como wiki, Asana/ClickUp como gestor de tareas, Zapier/Make como automatización con cientos de conectores) — foco deliberado en el dominio de negocio, no en cobertura genérica. Compite contra:
- Hojas de cálculo + WhatsApp manual
- Contratar más personas para "acordarse" del proceso
- Herramientas sueltas (CRM + Zapier + chatbot) sin gobierno ni trazabilidad
- Seguir aguantando el caos operativo

---

**Modelo (hipótesis central):** Sistema operativo con agentes de responsabilidad delimitada — no chatbots sueltos.
