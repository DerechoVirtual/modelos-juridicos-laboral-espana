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

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-sanciones-a-trabajadores-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-sanciones-a-trabajadores-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-sanciones-a-trabajadores-espana:<skill>`). Son 29, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Cartas y comunicaciones a la plantilla (12)

- **Apercibimiento sin sanción: carta** (`apercibimiento-sin-sancion-carta-343`). Carta de la empresa al trabajador con un apercibimiento o llamada de atención, sin sanción, por incumplimientos leves como el horario, el registro de jornada o la baja atención al público.
- **Apertura de expediente sancionador: aviso a representantes, sindicato y delegado de prevención** (`apertura-expediente-sancionador-aviso-representantes-322`). Carta de la empresa al comité, delegados y sindicato para avisarles de la apertura de un expediente sancionador, de modo que informen, aleguen y propongan pruebas antes de imponer la sanción.
- **Cancelar antecedentes por sanción: comunicación del trabajador** (`cancelar-antecedentes-sancion-comunicacion-trabajador-308`). Carta de la empresa al trabajador para comunicarle que se han cancelado sus antecedentes disciplinarios por una sanción anterior, que dejan de tener efecto.
- **Sanción impuesta: aviso a la representación de los trabajadores en el expediente sancionador** (`sancion-impuesta-aviso-representacion-trabajadores-321`). Carta de la empresa a la representación de las personas trabajadoras para avisarles de la sanción impuesta a un trabajador y cumplir su derecho de información en el expediente sancionador.
- **Sanción por bajo rendimiento: carta** (`sancion-bajo-rendimiento-carta-318`). Carta de sanción de la empresa al trabajador por disminución del rendimiento o por ejecución deficiente de una tarea con daño a personas o cosas, con los motivos a elegir.
- **Sanción por embriaguez habitual o toxicomanía: carta** (`sancion-embriaguez-habitual-toxicomania-carta-319`). Carta de sanción de la empresa al trabajador por embriaguez habitual o toxicomanía que repercute negativamente en el trabajo, en el ejercicio del poder disciplinario de la empresa.
- **Sanción por faltas de asistencia o puntualidad: carta** (`sancion-faltas-asistencia-puntualidad-carta-311`). Carta de sanción de la empresa al trabajador por faltas de asistencia o puntualidad, con motivos a elegir como impuntualidad o abandono injustificado del puesto, en el ejercicio del poder disciplinario.
- **Sanción por indisciplina o desobediencia: carta** (`sancion-indisciplina-desobediencia-carta-314`). Carta de sanción de la empresa al trabajador por indisciplina o desobediencia, como no usar protecciones de seguridad o incumplir órdenes del empresario, con los motivos a elegir.
- **Sanción por ofensas verbales o físicas: carta** (`sancion-ofensas-verbales-fisicas-carta-313`). Carta de sanción de la empresa al trabajador por ofensas verbales o físicas en el trabajo contra el empresario, compañeros o terceros, con los motivos a elegir según el caso.
- **Sanción por otras infracciones del convenio: carta** (`sancion-otras-infracciones-convenio-carta-315`). Carta de sanción de la empresa al trabajador por infracciones tipificadas en el convenio colectivo que no encajan en los demás modelos, en el ejercicio del poder disciplinario de la empresa.
- **Sanción por reincidencia o reiteración de faltas: carta** (`sancion-reincidencia-reiteracion-faltas-carta-317`). Carta de sanción de la empresa al trabajador que reincide o reitera faltas ya sancionadas, para que la nueva sanción tenga en cuenta su historial disciplinario.
- **Sanción por transgresión de la buena fe y abuso de confianza: carta** (`sancion-transgresion-buena-fe-abuso-confianza-carta-312`). Carta de sanción de la empresa al trabajador por transgresión de la buena fe o abuso de confianza, con motivos a elegir como fraude, apropiación de bienes o uso indebido de medios de la empresa.

### Escritos y solicitudes (4)

- **Aceptación del cargo en el expediente sancionador** (`aceptacion-cargo-expediente-sancionador-339`). Escrito por el que la persona designada por la empresa acepta el cargo de instructor, o de encargado de abrir el expediente, en un expediente contradictorio contra un trabajador.
- **Diligencias en el expediente sancionador** (`diligencias-expediente-sancionador-338`). Conjunto de diligencias del instructor en el expediente sancionador de la empresa, como notificaciones, citaciones y actas de declaración del trabajador y de testigos, para documentar las actuaciones.
- **Nombramiento en el expediente sancionador** (`nombramiento-expediente-sancionador-340`). Escrito por el que quien dirige el expediente contradictorio nombra instructor o secretario del mismo, en el procedimiento sancionador de la empresa contra un trabajador.
- **Pedir la cancelación de antecedentes por sanción** (`pedir-cancelacion-antecedentes-sancion-310`). Escrito del trabajador a la empresa para solicitar que se cancelen los antecedentes de una sanción ya cumplida, de modo que no cuente en su historial disciplinario.

### Expediente disciplinario (13)

- **Actuaciones no disciplinarias: propuesta** (`actuaciones-no-disciplinarias-propuesta-329`). Propuesta del instructor de que, tras el expediente contradictorio, se adopten medidas no disciplinarias respecto al trabajador, sin imponer sanción, por entender que no procede una medida disciplinaria.
- **Cargos por bajo rendimiento: pliego** (`cargos-bajo-rendimiento-pliego-331`). Pliego de cargos de la empresa que imputa al trabajador una falta grave o muy grave por disminución del rendimiento, con audiencia a los representantes y plazo para descargos.
- **Cargos por embriaguez habitual o toxicomanía: pliego** (`cargos-embriaguez-habitual-toxicomania-pliego-328`). Pliego de cargos de la empresa que imputa al trabajador embriaguez habitual o toxicomanía con perjuicio para la empresa y le concede plazo para formular descargos en el expediente.
- **Cargos por faltas de asistencia o puntualidad: pliego** (`cargos-faltas-asistencia-puntualidad-pliego-337`). Pliego de cargos de la empresa que imputa al trabajador faltas de asistencia o puntualidad y le concede plazo para alegaciones, descargos y prueba, con audiencia a los representantes.
- **Cargos por indisciplina o desobediencia: pliego** (`cargos-indisciplina-desobediencia-pliego-336`). Pliego de cargos de la empresa que imputa al trabajador indisciplina o desobediencia, como no usar medidas de seguridad, y le concede plazo para descargos en el expediente contradictorio.
- **Cargos por ofensas verbales o físicas: pliego** (`cargos-ofensas-verbales-fisicas-pliego-332`). Pliego de cargos de la empresa que imputa al trabajador ofensas verbales o físicas, le concede plazo para alegaciones, descargos y prueba, y da audiencia a los representantes de los trabajadores.
- **Cargos por otras infracciones del convenio: pliego** (`cargos-otras-infracciones-convenio-pliego-325`). Pliego de cargos de la empresa que imputa al trabajador infracciones del convenio colectivo, abre el expediente contradictorio y le concede plazo para presentar descargos y proponer prueba.
- **Cargos por reincidencia o reiteración de faltas: pliego** (`cargos-reincidencia-reiteracion-faltas-pliego-324`). Pliego de cargos de la empresa que imputa al trabajador la reincidencia o reiteración de faltas, abre el expediente contradictorio y le concede plazo para formular descargos.
- **Cargos por transgresión de la buena fe y abuso de confianza: pliego** (`cargos-transgresion-buena-fe-abuso-confianza-pliego-330`). Pliego de cargos de la empresa que imputa al trabajador transgresión de la buena fe o abuso de confianza, con los motivos a elegir, y le abre plazo de alegaciones y descargos en el expediente.
- **Descargos del trabajador: pliego** (`descargos-trabajador-pliego-327`). Pliego de descargos del trabajador en el expediente disciplinario, en el que justifica su conducta, niega o matiza los hechos que se le imputan y propone las pruebas que le convengan.
- **Ficha de antecedentes por sanción** (`ficha-antecedentes-sancion-309`). Ficha de registro de las sanciones de un trabajador, con la falta, la sanción, su calificación, el precepto, las fechas de comunicación y ejecución y la caducidad, para controlar los antecedentes disciplinarios.
- **Sanción propuesta en el expediente disciplinario** (`sancion-propuesta-expediente-disciplinario-323`). Propuesta del instructor a la empresa, al cierre del expediente contradictorio, de imponer una sanción concreta al trabajador, con los hechos probados y su calificación.
- **Sobreseimiento del expediente sancionador: propuesta** (`sobreseimiento-expediente-sancionador-propuesta-320`). Propuesta del instructor, tras la tramitación del expediente contradictorio, de sobreseerlo y archivarlo sin sanción al trabajador por no haberse acreditado los hechos imputados.
