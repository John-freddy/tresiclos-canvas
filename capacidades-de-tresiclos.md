# Capacidades de TRESICLOS — lo que se hace por una empresa

> **Borrador v0.1 (2026-11-04).** Una capacidad es lo que TRESICLOS hace *por* la empresa, no una funcionalidad. Se agrupan por los retos que enfrenta una pyme.
> Estado verificado contra los `STATUS.md` del repo, **en dev**: ninguna empresa lo usa todavía en producción. Las funcionalidades que sostienen cada capacidad están en el anexo [`impacto-de-tresiclos.md`](./impacto-de-tresiclos.md) §1.
>
> **Lente de las 4 barreras** (columna "Barrera"): **T** tecnología · **F** framework · **M** mindset · **A** acompañamiento.
> **Estado:** Hecho · Parcial · Planeado.

---

## Reto 1 — Administrar eficientemente
*Que el negocio funcione sin depender de la memoria de nadie. Cubre por igual los procesos operativos, el servicio al cliente y los procesos comerciales.*

| # | TRESICLOS hace por la empresa | Barrera | Estado |
|---|---|---|---|
| 1 | Estandariza cómo se hace el trabajo: el mismo resultado sin importar quién lo haga | T · F | Hecho |
| 2 | Garantiza que nada se quede sin atender: plazos, alertas y un responsable por cada cosa | T | Hecho |
| 3 | Atiende al cliente en el momento y por el canal donde está, y pasa el caso a una persona cuando hace falta | T | Hecho en dev |
| 4 | Hace avanzar el proceso comercial sin perder oportunidades: del primer contacto a la derivación y el seguimiento | T | Hecho en dev; asignación y derivación por IA en código, prueba pendiente |
| 5 | Coordina el trabajo entre personas y agentes, en un solo lugar | T | Hecho |
| 6 | Conserva el conocimiento de la empresa para que no viva solo en la cabeza de la gente | T | Hecho |
| 7 | Muestra cómo va el negocio sin tener que preguntar | T · F | Hecho |
| 8 | Deja constancia de qué se hizo, quién lo hizo y por qué | T | Hecho |

## Reto 2 — Aprender y mejorar
*Que la empresa aprenda de lo que le pasa y mejore de forma sistemática. Es la capacidad de fondo de TRESICLOS.*

| # | TRESICLOS hace por la empresa | Barrera | Estado |
|---|---|---|---|
| 9 | Escucha al cliente al cerrar cada caso (calificación y opinión) | M · F | Planeado (spec aprobada, sin código) |
| 10 | Detecta qué conviene mejorar y lo sustenta con evidencia | F | Hecho en V1, con indicadores cargados a mano |
| 11 | Convierte la mejora en acciones, las ejecuta y comprueba si funcionó | F | Hecho en V1; la medición de impacto, parcial |
| 12 | Recuerda lo aprendido: cada ciclo cerrado queda como memoria de la empresa | F | Parcial: se guardan actas; el uso del historial para decidir, sin verificar |

## Reto 3 — Emprender para crecer
*Que la empresa pase de administrar lo que tiene a construir lo que todavía no existe.*

| # | TRESICLOS hace por la empresa | Barrera | Estado |
|---|---|---|---|
| 13 | Traduce la estrategia en metas con responsables y seguimiento | F | Parcial: metas comerciales e indicadores; modelo estratégico tipo Kaplan & Norton, sin verificar |
| 14 | Acompaña al empresario y a su equipo en la ejecución y en el cambio de hábitos | M · A | Parcial: acompañamiento bajo demanda (Koda) |
| 15 | Trae la mejora al empresario sin que la pida | A | Planeado |

## Cualidad transversal — Con control
*Cómo lo hace todo, no una capacidad aparte.* Los agentes actúan con permisos mínimos, una persona valida los resultados importantes y todo queda trazable (Hecho). Supervisar a los propios agentes con evidencia es **Parcial** (existe el ámbito Trazas; el centro de control y las pruebas sistemáticas están planeados).

## Fuera de alcance por ahora
Cuánto ayuda TRESICLOS a crecer a través del CRM (captar más clientes, vender más). Se decidió no abordarlo todavía; el CRM cuenta aquí solo como parte del proceso comercial del Reto 1.

---

## Lectura

- **Reto 1** está casi completo en dev; es lo que ya se puede mostrar funcionando.
- **Reto 2** tiene la máquina construida pero le faltan las entradas: la voz del cliente (9) y los indicadores automáticos.
- **Reto 3** es el menos avanzado, y justo ahí está la promesa más distintiva (15).
- Por barrera: **T** está cubierta; **F** tiene base construida; **M** y **A** son las más débiles.
- Sigue sin existir una línea base de Vecina; sin ella ninguna de estas capacidades se puede traducir en impacto medido.
