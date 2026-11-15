# Las 5 condiciones para que TRESICLOS sea una empresa real

> Criterios verificables, no aspiraciones. Cada uno tiene una prueba binaria: se cumplió o no.
> Derivan del análisis competitivo del 2026-08-01 (ver [`notas-lean-canvas.md`](./notas-lean-canvas.md)).

## 1. El piloto demuestra mejora medible que un stack genérico no logra

Vecina Inmobiliaria operando un proceso real end-to-end en producción sobre el motor, con **una métrica operativa que mejora contra su línea base** (casos perdidos, tiempo de respuesta, % seguimientos cumplidos). No "usamos el sistema": mejoró X% algo que dolía.

**Prueba:** línea base documentada antes + medición después, mismo proceso, ≥3 meses.

## 2. El pilar diferencial funciona con datos reales

Un ciclo completo de mejora continua ejecutado por `agente_mejora_continua` con al menos una lente (BSC o 4DX) sobre datos reales del tenant: detecta desviación → propone → humano valida → se mide el resultado. Sin esto, TRESICLOS es la parte no diferencial (tech) prometiendo la diferencial. (El agente ya existe en código desde MCA V1; lo que falta es cerrar un ciclo con datos reales.)

**Prueba:** un ciclo real cerrado con un empresario real, trazable en `Event Occurrence`.

## 3. El acompañamiento es proactivo, no reactivo

Iniciativa proactiva mínima funcionando (hoy se construye desde el backend, no con el modo Autonomous del Agent): el agente inicia contacto por cron/evento (ej. "esta semana no se cumplió la medida predictiva, hablemos"). Es lo que separa "consultoría escalada" de "chatbot que espera preguntas" — y lo que ninguna herramienta genérica hace.

**Prueba:** ≥1 intervención/semana iniciada por el agente que el empresario califica como útil.

## 4. Alguien que no eres tú paga por ello

Un segundo tenant, fuera del ecosistema Vecina/Royal, que paga precio real (no cortesía) y llega a su primer ciclo de valor sin que el fundador haga consultoría manual intensiva. Esto valida que el valor es del producto, no de John acompañando en persona.

**Prueba:** contrato firmado + onboarding ≤4 semanas + renovación al mes 3.

## 5. La unidad económica cierra

El precio por tenant cubre costo LLM + infraestructura + costo de adquisición con margen, y el costo de "normalizar" una pyme nueva (setup de procesos, datos, agentes) baja con cada cliente en vez de repetirse completo (hipótesis de palanca: que Koda guíe la configuración por conversación; hoy no verificada).

**Prueba:** margen bruto positivo por tenant al mes 3 y tiempo de onboarding decreciente entre cliente 2 y cliente 3.

---

**Orden importa:** las condiciones 1 → 2 → 3 son secuenciales (validar motor, luego agente diferencial, luego proactividad); 4 y 5 solo tienen sentido después. Intentar el 4 antes del 1-2 es vender la promesa sin el producto — el error clásico.

**Secuencia de construcción canónica:** vive en [`plan-para-cumplir-el-claim.md`](./plan-para-cumplir-el-claim.md) (numeración propia de ese doc): feedback al cierre (ago 2026) → motor en producción (oct 2026) → agente de mejora continua alimentado con datos reales → iniciativa proactiva, con la línea base capturándose desde ya. La condición 1 de aquí se valida cuando ese plan llega a su paso 1; la condición 2, en su paso 3; la 3, en su paso 4.
