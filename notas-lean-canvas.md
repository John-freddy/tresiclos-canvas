# Notas y hallazgos — Lean Canvas TRESICLOS

> Bitácora de evidencia para [`lean-canvas-tresiclos.md`](./lean-canvas-tresiclos.md).
> Regla: si algo se verifica como falso o desactualizado, se corrige en el canvas y **no queda documentado aquí**. Este archivo solo guarda lo que sostiene una sección del canvas (con evidencia) o lo que sigue abierto.
> Estado hecho vs. planeado (verificado en el repo): [`impacto-de-tresiclos.md`](./impacto-de-tresiclos.md).

---

## 1. Hallazgos incorporados al canvas (con evidencia)

| Hallazgo | Evidencia | Dónde se incorporó |
|---|---|---|
| Cada actividad conserva el contexto completo del caso (proceso, responsables, SLA, historial inmutable) — no es una tarjeta aislada | `backend/prisma/schema.prisma:1127` (`Case`), `:1191` (`ActivityInstance`), `:1251` (`EventOccurrence`) | §3 PUV, §4 Solución, §9 Ventaja Competitiva |
| Posicionamiento deliberado: no competir con Notion/Asana/ClickUp/Zapier/Make/CRM genérico, foco en el dominio de negocio | Documento de análisis previo (2026-08-01) + coherente con foco actual (piloto Vecina Inmobiliaria) | Alternativas Existentes, §3 PUV (palabras clave) |
| Principio de construcción: cambios pequeños y validados por paso. Desde agosto el repo avanzó mucho (Task/Project Manager, MCA V1, Bodega, Content Library, Natalia en dev); lo pendiente es la validación en producción real con un caso | `governance/CLAUDE.md` (reglas Karpathy); estado en [`impacto-de-tresiclos.md`](./impacto-de-tresiclos.md) | §4 Solución (nota de fase) |
| Segmento resuelto: pymes en general, inmobiliaria = piloto/puerta de entrada, no el límite del mercado | Tesis del fundador (2026-08-01): 4 barreras de crecimiento pyme (mindset, framework, tech, acompañamiento) observadas empíricamente, no específicas de inmobiliaria | §2 Segmento MDO |
| "Framework" (Kaplan & Norton / BSC) ya es decisión de diseño acordada, no solo idea del fundador | `agent/documentation/DECISIONS.md` D-008/D-015 (acordada): BSC es una "lente metodológica" de `agente_mejora_continua`, junto a 4DX/PDCA/Kaizen/Six Sigma/coaching . **Implementado en V1** (`agent/documentation/STATUS.md:52`, oleadas 9–10.5; MCA cerrado 2026-09-19) — `SPEC/canonical/improvement-continuous-agent.md` | §4 Solución (pilar Framework y Mindset) |
| Feedback del cliente al cierre de caso (califica + opina) como complemento del SLA e insumo para los agentes | Plan del fundador (2026-08-01): se construye en **agosto 2026**; cierra el loop de "capacidad de aprender" — primera fuente de datos real para que los agentes revisen la operación. **Verificado 2026-11-04:** spec canónica aprobada D-135 (`backend/documentation/SPEC/canonical/case-evaluation.md`, CE-01..CE-11: evaluación al `completed`, tabla `case_evaluations`, WhatsApp, una pregunta 1–5 + texto opcional, agentes/MCA consumen solo vía API); trigger `case.completed.v1` existe; DDL/canal/API/UI en **Backlog** (`backend/documentation/STATUS.md:629`), sin rastro de feedback/CSAT en `schema.prisma` | §8 Métricas Clave |
| La línea base es el error clásico que el propio whitepaper de Salesforce lista: "falta de datos de referencia" (obstáculo) y "marca tu rendimiento actual" (checklist de planificación) — validación externa del ítem 5 del plan | Whitepaper Salesforce 2026, PDF pp. 6 (numeración impresa 05–06): [`referencias/Operating-Agents-Whitepaper-_-_es_MX.pdf`](./referencias/Operating-Agents-Whitepaper-_-_es_MX.pdf) | [`plan-para-cumplir-el-claim.md`](./plan-para-cumplir-el-claim.md) (ítem 5), sin cambio de contenido |
| Agentes ya avanzan/derivan casos hoy por **tools en modo conversacional** (Natalia: `avanzar_oportunidad`, `derivar_oportunidad`), aunque el modo **engine/`ai_task`** sigue sin ejecutar (listener vacío) | `backend/documentation/STATUS.md` (cabecera: D-180, D-197; líneas 608 y 625 para `ai_task`) | §4 Solución — precisa el matiz de "agentes gestionando actividades" (ver §2) |

**Contexto de fase (2026-08-01):** el canvas y las 5 condiciones son provisionales — el producto está terminando de construirse; producción v1 para Vecina estimada ~octubre 2026. *(Al 2026-11-04 esa fecha no se cumplió; ver §2, fechas.)*

---

## 2. Insights en investigación (sin concluir — no llevar al canvas todavía)

| Insight | Por qué no está cerrado | Qué falta para concluir |
|---|---|---|
| "Inbox universal" completo (actividades del motor + tareas libres + conversaciones) como north star de producto | Ya existe el combinado actividades + tareas libres: `/workbox` (D-170/D-171, Task/Project Manager implementado). Las conversaciones viven en su propio Inbox; el "inbox universal" que las una sigue como aspiracional (`frontend/documentation/DECISIONS.md`, FE-A02) | Decidir si unir conversaciones al workbox es la tesis de producto o se descarta |
| Modelo de permisos granular (`Department`, `OrganizationalRole`, `UserRoleAssignment`, `DataVisibilityGrant`) ya existe en el schema | `schema.prisma:455,478,509,531`; aparece en el mapa de permisos de `backend/documentation/STATUS.md:222` — no se verificó cuánto está cableado end-to-end (endpoints, UI) | Auditar madurez real antes de asumir que "falta enriquecer el modelo de roles" |
| Modelo de ingresos | Sin pricing definido en código ni docs | Definir estructura y cifras con el fundador |
| Canal de adquisición principal | Hipótesis de fases registrada en §6 (acompañado → Koda asiste → escala); el segmento inicial sigue sin definir | Definir segmento inicial; medir fuentes reales de tráfico con el tenant propio |
| Métrica north star (de las propuestas en §8 del canvas) | No se ha elegido cuál es la prioritaria; podría sumarse una atada a "capacidad de aprender" (ciclos de mejora continua cerrados por cuenta). Con la estrategia comercial (§6) aparecen candidatas de negocio (CAC, tiempo humano por venta) | Elegir al validar el motor con el caso real piloto |
| `agente_mejora_continua` — alimentación con datos reales | Implementado en V1 (lectura, hallazgos, acta con confirmación; `agent/documentation/STATUS.md:52`). El plan V1 dejó los indicadores `api_interna` como captura manual (`mca-implementation-plan.md` §2.3; por confirmar contra el estado actual). La lente BSC como contenido no aparece en el código del agente (puede vivir como dato en el backend; sin verificar) | Confirmar qué datos lee hoy el agente y si la lente BSC opera; conectar la evaluación del cliente (D-135) cuando exista |
| Iniciativa proactiva del agente ("acompañamiento por iniciativa propia") | El modo Autonomous del Agent Service figura **Won't do** (`agent/documentation/STATUS.md`). La iniciativa se resuelve desde el backend: Roy (D-194, primer contacto al derivar; spec en borrador, en desarrollo) y auto-followups (D-164, Backlog). Ninguna equivale todavía a "traer la mejora al empresario" | Decidir si la proactividad de mejora (no de ventas) usa el mismo mecanismo desde el backend o necesita otro |
| **Agentes gestionando actividades del motor** → procesos atendidos 100% por automatizaciones y agentes (anotado 2026-08-01; John empieza a trabajarlo a inicios de agosto 2026) | Aún no está incorporado al camino ni al canvas. Base técnica existente: el motor ya crea actividades (`human_task`, `system_task`, `wait_event`) y el tipo `ai_task` está previsto, pero la integración motor ↔ Agent Service está **no implementada** (`backend/documentation/CONTEXT.md` §Límites: listener `ai_task` pendiente; modo **Engine** del Agent Service no implementado, `agent/documentation/CONTEXT.md:73`) | Cuando el trabajo arranque: definir qué etapa del camino ocupa (¿entre Etapa 2 y 3?) y qué cambia en el claim — un proceso 100% autónomo es una promesa distinta a "acompañar" |
| **"Planta de agentes de IA al servicio de la empresa"** — término para definir la IA dentro de TRESICLOS (anotado 2026-08-01) | Doble lectura en español que favorece la tesis: fábrica que produce a escala + "planta de personal" (plantilla), coherente con el framing ya existente en `agent/documentation/CONTEXT.md` ("trabajadores digitales por responsabilidad operativa, no chatbots genéricos"). Riesgo: suena industrial/frío, puede chocar con el pilar Mindset/Acompañamiento (coaching, calidez) si carga toda la frase del PUV. Variante en prueba para §3 del canvas: "TRESICLOS opera una planta de agentes de IA al servicio de la empresa: trabajadores digitales que ejecutan actividades del proceso bajo permisos acotados y validación del motor. Sobre esa planta se apoyan framework, mindset y acompañamiento, que le dan criterio y calidez a lo que la planta produce." | **No comprometer en el canvas todavía.** Validar diciéndola en una conversación real con alguien de Vecina esta semana — ver si "planta" hace sentido en boca de un empresario o suena raro. Si valida, entra a §3 PUV como frase del núcleo técnico (no como resumen de todo el claim, que sí carga el acompañamiento). |
| **Hipótesis de diferencial vs. Salesforce:** Salesforce gestiona el ciclo de vida del **agente** (ADLC: planificar · generar · probar · evaluar · observar · mejorar); TRESICLOS podría gestionar el ciclo de vida del **proceso** ejecutado por agentes y personas (anotado 2026-11-04) | Sale del análisis externo sobre el whitepaper, que él mismo la marca "por validar". El whitepaper no cubre rediseño organizacional ni coordinación de procesos completos humano+agente (verificado en el PDF completo) — eso es consistente con la hipótesis, pero no la prueba: no se ha comparado contra Agentforce ni otros proveedores | Comparar con capacidades actuales de Agentforce y de otros (parte del mapa competitivo de abajo) antes de llevarla al canvas §9 |
| **AI Control Tower** / centro de control de agentes (operativo, económico, comercial) | Existe en `agent/documentation/SPEC/canonical/agents-catalog.md` §2.2 como "Visión / no implementado"; en frontend figura como aspiracional (FE-A03 / STATUS). Depende del modo engine y del listener `ai_task` (vacío). Material parcial ya construido: ámbito **Trazas** del workbench `/agents`, trazas runtime persistidas en BD (backend-mode), `activity_instance` + `event_occurrence` | Decidir si es etapa propia del camino; auditar qué cubren hoy las Trazas antes de especificar |
| **Evaluación sistemática de agentes** (el whitepaper insiste en pruebas masivas, datos realistas y permisos reales) | Hoy hay guías de prueba **manuales** por dominio (`backend/documentation/evaluations/domains/`, ej. `natalia.md`: checklist + matriz, con rol y evidencia); no se encontró generación/ejecución automatizada de escenarios | Investigar si hace falta una capa de pruebas automáticas antes de ampliar el número de agentes; relevante para Roy y los siguientes |
| **Cinco funciones del whitepaper** (director de IA, generador, evaluador, control de calidad, supervisor) aplicadas a una pyme | Son roles pensados para una organización de TI grande; la interpretación de que en una pyme se concentran en 1–2 personas + agentes es razonable pero no está validada. En TRESICLOS el "supervisor" sería el producto mismo (Control Tower) | Definir quién cumple cada función en Vecina y cuáles asume el producto |
| **Fechas del camino vs. estado real** (pendiente de confirmar con John) | Los documentos asumen feedback en ago 2026 y v1 con Vecina ~oct 2026. Al 2026-11-04: feedback en Backlog sin código; la memoria del proyecto indica que solo se usa la BD de desarrollo (sin prod en uso) | Re-fijar fechas del camino con John; no se asume retraso ni causa |
| Mapa competitivo real (no solo "Monday" como sinécdoque) | En las comparaciones se usó Monday como atajo de "SaaS genérico"; el set relevante para pymes LATAM es más amplio: CRM-WhatsApp (Kommo, HighLevel, Clientify), suites pyme (Zoho, Bitrix24, Odoo), y para el vertical piloto los CRM inmobiliarios (Wasi, Tokko Broker, EasyBroker) — nombres de memoria del modelo, **sin verificar precios/features actuales** | Investigar y armar tabla comparativa real (features vs. 4 barreras, pricing) antes de definir el pitch de octubre 2026 |

---

## 3. Conclusión de auditoría (2026-08-01) — guía para ajustar durante la implementación

**Hallazgo central:** el componente emocional del canvas (tranquilidad, "bajar ansiedad") corresponde a la parte **construida**; el claim ("aprende y viene a buscarte") corresponde a la parte **no construida**. La secuencia de valor está invertida respecto a la venta.

**Valor para el empresario, ordenado por solidez de evidencia hoy:**
1. **"Tu operación deja de depender de la memoria de tu gente"** (motor + trazabilidad + WhatsApp) — construido, dolor semanal real. **Lo vendible hoy.**
2. **La voz del cliente en cada cierre** (ago 2026) — casi ninguna pyme lo mide; barato y de "wow" inmediato. Subestimado: no es solo métrica/insumo, es valor directo vendible.
3. **IA confiable** (gobierno agente-motor-humano) — construido, pero es habilitador de confianza, no motivo de compra.
4. **El agente que viene a buscarte con la mejora** — el valor más alto si se cumple (saca a TRESICLOS de competir con SaaS genérico y lo pone a competir con consultores), pero hoy sin evidencia.

**Implicación:** el claim es la visión correcta a ~12 meses, **no el pitch de octubre 2026**. Vender primero tranquilidad (existe), feedback del cliente segundo (agosto), y la mejora proactiva se *demuestra* después — no se promete de entrada. Revisar esta sección en cada hito del plan y ajustar el canvas según lo que la realidad confirme o niegue.

---

## 4. Posición frente a plataformas internacionales — si el claim se cumple (2026-08-01)

Análisis condicionado: asume el claim cumplido **con evidencia** (mejora medida en el piloto, no prometida).

| Categoría | Posición resultante | Riesgo / advertencia |
|---|---|---|
| **CRM-WhatsApp** (Kommo, HighLevel, Clientify) | Categoría superior, no "lo mismo mejorado": ellos ordenan conversaciones; TRESICLOS cierra el ciclo proceso → feedback → agente → mejora proactiva. Su bot responde; nuestro agente revisa el negocio. | En un demo de 10 min su "IA con insights" se ve igual. La diferencia solo es visible con números del piloto — la línea base lo es todo. |
| **Suites pyme** (Zoho, Bitrix24, Monday, Odoo) | La tesis de las 4 barreras favorece: son cajas de herramientas horizontales (solo tech, autoconfiguración). TRESICLOS = sistema opinionado + acompañamiento. | Ganan siempre en precio, marca, integraciones, pulido — no competir ahí. Todos montan "AI agents": la ventana no es tener IA sino la **profundidad del loop** (motor + gobierno + feedback + proactividad cableados juntos), que no se agrega con un plugin. |
| **CRM inmobiliarios** (Wasi, Tokko, EasyBroker) | Comparación menos cómoda del piloto: ganan en lo vertical (inventario, portales). Jobs distintos → a corto plazo **coexistir más que competir**. | Si se quiere el vertical a fondo: integrar o replicar lo inmobiliario-específico. Decisión pendiente, no urgente. |

**Síntesis:** cumplido el claim, TRESICLOS no es "mejor herramienta" en ninguna categoría — cambia el eje de comparación de features a resultados. El comparable real deja de ser un SaaS y pasa a ser un **COO fraccional / consultora de mejora continua a precio de software** — categoría vacía en pymes hispanohablantes.

**Defensa real (moat):** no el código (copiable con tiempo) sino el **dato acumulado por tenant** — cada ciclo de mejora cerrado hace que cambiar de plataforma le cueste al cliente su historial de aprendizaje. Ventaja compuesta que las internacionales no tienen incentivo de construir para una pyme LATAM.

**Donde se sigue perdiendo aunque se cumpla todo:** precio de entrada, confianza de marca, ecosistema de integraciones, self-serve. El canal (relación directa + red territorial) no es un detalle: es lo que compensa exactamente esas debilidades.

---

## 5. Fuentes externas

**Salesforce — "Guía definitiva para la gestión de compañías agénticas" (2026, 27 págs.)** · [`referencias/Operating-Agents-Whitepaper-_-_es_MX.pdf`](./referencias/Operating-Agents-Whitepaper-_-_es_MX.pdf)

- **Idea central:** el reto ya no es construir agentes sino operarlos, medirlos y mejorarlos (ciclo ADLC de 6 fases, 5 funciones, marco de medición de 4 niveles: eficacia · rendimiento · interacción · valor empresarial).
- **Lo que se tomó:** el marco de 4 niveles (como lente para §8 del canvas, solo candidatas) y la validación externa de la línea base.
- **Precauciones:** es documento comercial de Agentforce; está sesgado a agentes de servicio al cliente (contención, derivaciones, CSAT) y a organizaciones grandes con equipo de TI. Los umbrales (>95 % fidelidad, >90 % relevancia, >85 % integridad, <2 s P90) son **sugeridos por Salesforce, no estándares**: no se adoptan como metas de TRESICLOS sin línea base propia.
- **Resumen previo recibido:** coincide en lo esencial con el PDF. Ajustes: la quinta función se llama "director de control de calidad de agentes", y el resumen traía un marcador de posición en lugar de las 6 fases del ADLC.

---

## 6. Estrategia comercial: TRESICLOS como su propio primer tenant (recibida 2026-11-15)

**Decisiones del fundador 📌 (2026-11-15):**
- Promesa central: **"Ejecuta y aprende"** (aplicada en canvas §3 y camino).
- Orden: **primero Vecina en producción; después TRESICLOS como tenant de sí mismo.**
- Segmento inicial: **se define después.**

**Lo que aporta el documento:**
- Propuesta: operar la empresa con procesos donde personas y agentes trabajan coordinados, con control, trazabilidad y mejora continua; no "otro CRM con IA ni bot de WhatsApp". Un mismo valor en tres lenguajes (dueño, director comercial, operaciones) → canvas §3.
- Salida al mercado en tres fases superpuestas (10–20 clientes acompañados → Koda asiste → escala) → canvas §5.
- Embudo con Koda: atracción → conversación/diagnóstico → demostración personalizada → seguimiento y venta → activación del tenant → medición y mejora. Separación de web pública, Koda comercial/demo/operativo, tenant comercial y entornos de demo aislados (tenant temporal, datos ficticios, créditos de IA limitados, 72 h como hipótesis).
- Seis preguntas a validar: procesos, agentes, Koda, ventas, implementación, economía; indicadores → canvas §8 (candidatas).
- Hito ambicioso, no requisito de V1: alguien descubre, prueba, contrata y empieza a usar sin intervención comercial humana.

**Qué resuelve de lo que teníamos abierto:** da datos reales (embudo, CAC, tiempo humano) sin esperar a que Vecina esté en producción plena, y puede alimentar el primer ciclo de `agente_mejora_continua` con datos reales (plan, ítem 3). El propio documento reconoce el límite: demuestra ejecución comercial, no que otras empresas mejoren (condición 4 sigue en pie).

**Dependencias y salvedades (sin verificar en código salvo lo indicado):**
- "Las actividades se ejecutan automáticamente" necesita `ai_task`, Blocked (D-010).
- Koda hoy es el copilot del MCA; el perfil comercial/demo no existe. En la documentación del repo no aparecen cobro/facturación automatizada, tenants temporales de demostración ni web comercial conectada.
- El documento apunta a 2027 para el tenant propio; las fechas del camino siguen por re-fijar (ver §2).
- La frase "ese cliente eres tú" solo funciona si el flujo corre de punta a punta; si falla en público, el costo reputacional es mayor.
- El feedback del cliente al cierre (D-135) no figura en el embudo comercial; podría aplicarse a las demos y reforzar el pilar "aprende".
- Dos frentes (Vecina y tenant propio) compiten por el mismo equipo: el orden acordado lo mitiga, no lo elimina.

**Por decidir:** segmento inicial; qué actividades comerciales puede ejecutar el agente sin humano; condiciones comerciales que Koda podría ofrecer sola; duración y costo de la demo.

---

## 7. Retos de la pyme que el proyecto no considera (investigación 2026-11-15)

> Calidad de fuentes: prensa, blogs y proveedores; las cifras varían mucho entre fuentes (ej. la caja como causa de fracaso va de ~35 % a ~82 %). Orientativas, no citables.

**Lo que coincide con la tesis:** planificación débil, poca capacitación o gerencia profesional, baja digitalización y "barreras mentales" — respaldan las 4 barreras.

**Candidatas a capacidad (aún sin incorporar a `capacidades-de-tresiclos.md`):**
1. **Caja y cobranza** — la causa de fracaso más citada; cobros tardíos generalizados (Coface/IDC: 77 % de empresas con retrasos; México ~66 días de cobro). Encaja con motor + WhatsApp + automatizaciones. Hipótesis a confirmar: si Vecina administra arriendos, la cartera de cánones es el caso natural.
2. **Gente: inducción, rotación, capacitación** — falta de procesos estandarizados para gestionar personal. Hoy se conserva conocimiento (cap. 6); no está planteado como "que alguien nuevo rinda rápido".
3. **Dependencia del dueño y continuidad** — delegar con control está implícito en el JTBD, no es capacidad explícita (cifra de sucesión ~30 %: fuente secundaria).

**Decisiones del fundador pendientes:**
4. **Visión financiera** (precios, márgenes, inventario, flujo proyectado): ¿fuera de alcance o integración con la contabilidad del cliente?
5. **Cumplimiento y protección de datos:** TRESICLOS procesa datos personales vía WhatsApp y proveedores de LLM; es oportunidad y obligación. No se verificó cómo lo cubre hoy el repo.

**Riesgo propio:** las barreras a la adopción de IA en pymes (talento, infraestructura, confianza) hacen que implementar cueste casi como construir → toca el costo de onboarding de la condición 5.

**Descartados por ahora:** acceso a financiamiento (solo indirecto) y captación de clientes vía CRM (ya fuera de alcance).

---

**Última actualización:** 2026-11-15
