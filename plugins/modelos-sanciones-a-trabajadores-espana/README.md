# Cartas de sanción y expediente disciplinario · España

> Plugin de Claude Code `modelos-sanciones-a-trabajadores-espana` · **29 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para sancionar con garantías: cartas de sanción por cada tipo de falta, apercibimientos, pliego de cargos y expediente contradictorio (con aviso a los representantes), y cancelación de antecedentes.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 29 está al final):

- **Cartas y comunicaciones a la plantilla** (12). Por ejemplo: Cancelar antecedentes por sanción: comunicación del trabajador; Sanción por faltas de asistencia o puntualidad: carta; Sanción por transgresión de la buena fe y abuso de confianza: carta.
- **Escritos y solicitudes** (4). Por ejemplo: Pedir la cancelación de antecedentes por sanción; Diligencias en el expediente sancionador; Aceptación del cargo en el expediente sancionador.
- **Expediente disciplinario** (13). Por ejemplo: Ficha de antecedentes por sanción; Sobreseimiento del expediente sancionador: propuesta; Sanción propuesta en el expediente disciplinario.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Carta de sanción por faltas de asistencia o puntualidad»
   - «Aviso a los representantes de la apertura de un expediente sancionador»
   - «Carta de apercibimiento sin sanción»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-sanciones-a-trabajadores-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-sanciones-a-trabajadores-espana:cancelar-antecedentes-sancion-comunicacion-trabajador-308`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él.
   Todos los datos jurídicos del escrito (artículos vigentes, sentencias con su ECLI, convenios, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las correcciones y avisos de la revisión del 17-11-2026 (reformas legales, órganos, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el escrito; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te indica el plazo y ante quién se presenta, y te entrega el escrito en Word con un resumen de lo que queda pendiente.

El resultado es un borrador para que lo revise un profesional antes de presentarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-sanciones-a-trabajadores-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-sanciones-a-trabajadores-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-sanciones-a-trabajadores-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-sanciones-a-trabajadores-espana:<skill>`.

### Cartas y comunicaciones a la plantilla (12)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 308 | Cancelar antecedentes por sanción: comunicación del trabajador | 2017 | `cancelar-antecedentes-sancion-comunicacion-trabajador-308` |
| 311 | Sanción por faltas de asistencia o puntualidad: carta | 2017 | `sancion-faltas-asistencia-puntualidad-carta-311` |
| 312 | Sanción por transgresión de la buena fe y abuso de confianza: carta | 2017 | `sancion-transgresion-buena-fe-abuso-confianza-carta-312` |
| 313 | Sanción por ofensas verbales o físicas: carta | 2017 | `sancion-ofensas-verbales-fisicas-carta-313` |
| 314 | Sanción por indisciplina o desobediencia: carta | 2017 | `sancion-indisciplina-desobediencia-carta-314` |
| 315 | Sanción por otras infracciones del convenio: carta | 2017 | `sancion-otras-infracciones-convenio-carta-315` |
| 317 | Sanción por reincidencia o reiteración de faltas: carta | 2017 | `sancion-reincidencia-reiteracion-faltas-carta-317` |
| 318 | Sanción por bajo rendimiento: carta | 2017 | `sancion-bajo-rendimiento-carta-318` |
| 319 | Sanción por embriaguez habitual o toxicomanía: carta | 2017 | `sancion-embriaguez-habitual-toxicomania-carta-319` |
| 321 | Sanción impuesta: aviso a la representación de los trabajadores en el expediente sancionador | 2017 | `sancion-impuesta-aviso-representacion-trabajadores-321` |
| 322 | Apertura de expediente sancionador: aviso a representantes, sindicato y delegado de prevención | 2017 | `apertura-expediente-sancionador-aviso-representantes-322` |
| 343 | Apercibimiento sin sanción: carta | 2017 | `apercibimiento-sin-sancion-carta-343` |

### Escritos y solicitudes (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 310 | Pedir la cancelación de antecedentes por sanción | 2017 | `pedir-cancelacion-antecedentes-sancion-310` |
| 338 | Diligencias en el expediente sancionador | 2017 | `diligencias-expediente-sancionador-338` |
| 339 | Aceptación del cargo en el expediente sancionador | 2017 | `aceptacion-cargo-expediente-sancionador-339` |
| 340 | Nombramiento en el expediente sancionador | 2017 | `nombramiento-expediente-sancionador-340` |

### Expediente disciplinario (13)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 309 | Ficha de antecedentes por sanción | 2017 | `ficha-antecedentes-sancion-309` |
| 320 | Sobreseimiento del expediente sancionador: propuesta | 2017 | `sobreseimiento-expediente-sancionador-propuesta-320` |
| 323 | Sanción propuesta en el expediente disciplinario | 2017 | `sancion-propuesta-expediente-disciplinario-323` |
| 324 | Cargos por reincidencia o reiteración de faltas: pliego | 2017 | `cargos-reincidencia-reiteracion-faltas-pliego-324` |
| 325 | Cargos por otras infracciones del convenio: pliego | 2017 | `cargos-otras-infracciones-convenio-pliego-325` |
| 327 | Descargos del trabajador: pliego | 2017 | `descargos-trabajador-pliego-327` |
| 328 | Cargos por embriaguez habitual o toxicomanía: pliego | 2017 | `cargos-embriaguez-habitual-toxicomania-pliego-328` |
| 329 | Actuaciones no disciplinarias: propuesta | 2017 | `actuaciones-no-disciplinarias-propuesta-329` |
| 330 | Cargos por transgresión de la buena fe y abuso de confianza: pliego | 2017 | `cargos-transgresion-buena-fe-abuso-confianza-pliego-330` |
| 331 | Cargos por bajo rendimiento: pliego | 2017 | `cargos-bajo-rendimiento-pliego-331` |
| 332 | Cargos por ofensas verbales o físicas: pliego | 2017 | `cargos-ofensas-verbales-fisicas-pliego-332` |
| 336 | Cargos por indisciplina o desobediencia: pliego | 2017 | `cargos-indisciplina-desobediencia-pliego-336` |
| 337 | Cargos por faltas de asistencia o puntualidad: pliego | 2017 | `cargos-faltas-asistencia-puntualidad-pliego-337` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
