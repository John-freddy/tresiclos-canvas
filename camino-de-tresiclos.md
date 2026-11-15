# El camino de TRESICLOS

> Documento narrativo: de dónde parte TRESICLOS, por dónde pasa y en qué se convierte si cumple su promesa.
> Registrado el 2026-08-01. **Documento vivo:** se ajusta en cada hito según lo que la realidad confirme o niegue.
>
> Documentos hermanos: [canvas](./lean-canvas-tresiclos.md) (el qué) · [notas](./notas-lean-canvas.md) (la evidencia) · [condiciones](./condiciones-para-ser-empresa.md) (el validar) · [plan](./plan-para-cumplir-el-claim.md) (el construir) · [impacto](./impacto-de-tresiclos.md) (hecho vs. planeado)

---

## La tesis

Toda pyme vive dos desafíos en tensión: **administrar eficientemente** lo que existe y **emprender para crecer** hacia lo que no existe. No resuelve ninguno bien por 4 barreras: mindset, framework, tech y acompañamiento. La capacidad de fondo que TRESICLOS construye es la **capacidad de la empresa de aprender** — normalizar la operación es el medio, no el fin.

## El destino

Si el camino se cumple, TRESICLOS no será "mejor herramienta" que Kommo, Zoho o Wasi — cambiará el eje de comparación de features a resultados. Su comparable real será un **COO fraccional**: el director de operaciones que revisa el negocio, escucha a los clientes, llega con la mejora sin que se la pidan y acompaña la ejecución — trabajo que hoy cuesta miles de dólares al mes, no escala, y ninguna pyme LATAM puede pagar. TRESICLOS lo hace a precio de software y con memoria perfecta de cada caso.

**La promesa corta (📌 2026-11-15): "Ejecuta y aprende".** Personas y agentes ejecutan los procesos con control y trazabilidad; la empresa aprende de cada caso. *Ejecuta* se demuestra primero; *aprende* es lo que cierra la diferencia.

**El claim (versión larga):** "El único sistema que no solo ordena la operación de tu pyme, sino que aprende de cada caso que cierras — con la voz de tus clientes incluida — y viene a buscarte con la mejora antes de que tú la pidas."

## Las etapas

### Etapa 0 — Hoy (estado verificado 2026-11-04): lo construido
Motor de procesos, CRM, Channel Manager (WhatsApp), multi-tenant, gobierno de agentes (el agente razona, el motor valida, el humano supervisa), trazabilidad inmutable. **Lo vendible hoy es tranquilidad:** "tu operación deja de depender de la memoria de tu gente". La base de la parte diferencial (aprender, proactividad) ya está construida en dev (MCA V1, agente de mejora continua, Koda), pero sin datos reales ni clientes en producción; el feedback del cliente y la iniciativa proactiva siguen pendientes.

**Regla de esta etapa:** capturar la línea base de Vecina **ya** (casos perdidos, tiempos, quejas) — se mide antes del cambio, no después.

### Etapa 1 — La voz del cliente (fecha original: agosto 2026; sin cumplir al 2026-11-04, por re-fijar)
Feedback al cierre de cada caso (califica + opina), ligado al `Case`, consultable por agentes como fuente autorizada. Complementa el SLA: el SLA mide si se cumplió el tiempo; el feedback mide si valió la pena. Es la primera fuente de datos real del pilar "aprende" — y valor directo vendible: casi ninguna pyme mide esto.

### Etapa 2 — Producción v1 con Vecina (fecha original: ~octubre 2026; sin cumplir al 2026-11-04, por re-fijar)
Un proceso real end-to-end en producción, con casos reales. **El pitch de esta etapa no es el claim completo** — es tranquilidad + voz del cliente. La mejora proactiva se demuestra después, no se promete de entrada.

### Etapa 2b — TRESICLOS como su propio tenant (después de Vecina; fecha por fijar, la estrategia comercial apunta a 2027)
TRESICLOS opera su proceso comercial (leads, demostraciones, seguimiento, contratación) dentro de su propio tenant, conectado a Koda y a una web comercial, y se mide: conversión, CAC, tiempo humano por venta, % de actividades ejecutadas por agentes. Aporta datos reales al ciclo de mejora (Etapa 3) y la prueba de que la plataforma ejecuta trabajo. **No** sustituye la validación en otras empresas (Etapa 5). Necesita construir: Koda comercial, tenants de demostración aislados, cobro, web comercial. Detalle y fases (acompañado → asistido por IA → escala) en [notas](./notas-lean-canvas.md) §6.

### Etapa 3 — El pilar diferencial: el agente que aprende
Alimentar `agente_mejora_continua` (ya implementado en V1) con datos reales y cerrar un primer ciclo: detecta desviación → propone con evidencia → humano valida → se mide. Con las lentes Kaplan & Norton / 4DX acordadas en diseño (D-008/D-015).

### Etapa 4 — La proactividad: viene a buscarte
Iniciativa proactiva (hoy desde el backend: Roy, auto-followups; el modo Autonomous del Agent figura Won't do) + canal de salida + gobierno de lo que el agente dice por iniciativa propia. Un agente proactivo que dice tonterías destruye la confianza más rápido que no tener agente. Aquí el claim queda completo.

### Etapa 5 — Ser empresa, no producto
Segundo tenant fuera del ecosistema Vecina pagando precio real, onboarding sin consultoría manual del fundador, unidad económica cerrando (margen positivo por tenant, onboarding decreciente). Ver [condiciones](./condiciones-para-ser-empresa.md) 4 y 5.

### Anotado — sin etapa asignada todavía
**Agentes gestionando actividades del motor** (hoy también precondición de "ejecuta" y de Koda comercial) → procesos completos atendidos 100% por automatizaciones y agentes. El motor aún no ejecuta actividades por agente (`ai_task`, Blocked D-010); mientras tanto los agentes operan casos por tools en modo conversacional (Natalia). Falta definir qué etapa ocupa y cómo modifica el claim. Detalle y base técnica en [notas](./notas-lean-canvas.md) §2.

## Cómo se gana y cómo se pierde

**El moat no es el código** (copiable con tiempo): es el **dato acumulado por tenant** — cada ciclo de mejora cerrado hace que cambiarse de plataforma le cueste al cliente su historial de aprendizaje. Ventaja compuesta que las plataformas internacionales no tienen incentivo de construir para una pyme LATAM.

**Donde se pierde siempre** (aunque se cumpla todo): precio de entrada, marca, integraciones, self-serve. Lo compensa el canal: relación directa + red territorial (Vecina). El canal no es un detalle — es parte de la estrategia.

**El riesgo que no cambia:** en un demo de 10 minutos, la "IA con insights" de cualquier suite y la de TRESICLOS se ven iguales. La única diferenciación real son los números del piloto contra su línea base. Sin línea base, no hay historia que contar.

---

**Última actualización:** 2026-11-15 (promesa "ejecuta y aprende"; orden Vecina → tenant propio)
