# Cartas de despido y extinción del contrato · España

> Plugin de Claude Code `modelos-despidos-espana` · **36 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para el final de la relación laboral: cartas de despido disciplinario y objetivo, despido nulo, dimisión del trabajador, jubilación, y extinción por incumplimiento de la empresa (art. 50 ET).

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 36 está al final):

- **Contratos, cláusulas y anexos** (1). Por ejemplo: Recolocación en contrato adscrito a obra de construcción: cláusula.
- **Cartas y comunicaciones a la plantilla** (16). Por ejemplo: Aviso de audiencia previa al despido disciplinario; Extinción del contrato por circunstancias de la producción (tras el RDL 32/2021): comunicación; Respuesta del trabajador a la recolocación tras el fin de la obra de construcción.
- **Demandas, papeletas y reclamaciones previas** (14). Por ejemplo: Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda; Despido nulo por discriminación por enfermedad o estado de salud: demanda; Despido de empleada del hogar: demanda.
- **Escritos y solicitudes** (3). Por ejemplo: Renuncia del fijo discontinuo al llamamiento; Ejecución del auto de readmisión irregular: escrito; Opción tras despido improcedente: escrito de la parte actora o representación.
- **Actas, acuerdos, planes y protocolos** (1). Por ejemplo: Transacción sobre el despido: acuerdo.
- **Documentos, certificados y modelos oficiales** (1). Por ejemplo: Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Carta de despido disciplinario»
   - «Carta de despido por causas objetivas»
   - «Demanda de extinción del contrato por incumplimientos graves de la empresa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-despidos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-despidos-espana:aviso-audiencia-previa-despido-disciplinario-19`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-despidos-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-despidos-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-despidos-espana:<skill>`). Son 36, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (1)

- **Recolocación en contrato adscrito a obra de construcción: cláusula** (`recolocacion-contrato-adscrito-obra-construccion-126`). Cláusula del contrato adscrito a obra de construcción que regula la recolocación del trabajador en otra obra de la empresa cuando termina aquella a la que estaba vinculado.

### Cartas y comunicaciones a la plantilla (16)

- **Aviso al trabajador del fin de la excedencia** (`aviso-trabajador-fin-excedencia-242`). Aviso de la empresa al trabajador para comunicarle que su excedencia está a punto de terminar y requerirle para que se incorpore o solicite el reingreso.
- **Aviso de audiencia previa al despido disciplinario** (`aviso-audiencia-previa-despido-disciplinario-19`). Escrito de la empresa para comunicar al trabajador la audiencia previa antes de un despido disciplinario, con los hechos imputados, y para darle plazo de alegaciones. Hay que unificar la calificación de la falta.
- **Baja voluntaria por jubilación: carta del trabajador** (`baja-voluntaria-jubilacion-carta-trabajador-134`). Carta con la que el trabajador comunica a la empresa su decisión de dejar voluntariamente el trabajo para acogerse a la jubilación, indicando la fecha de efectos.
- **Desistimiento de la empresa frente al alto directivo: comunicación** (`desistimiento-empresa-frente-alto-directivo-comunicacion-350`). Comunicación de la empresa al alto directivo por la que desiste de su contrato de alta dirección, con o sin respeto del preaviso, y con la indemnización que corresponda.
- **Desistimiento del alto directivo: comunicación a la empresa** (`desistimiento-alto-directivo-comunicacion-empresa-348`). Comunicación del alto directivo a la empresa por la que da por extinguido su contrato de alta dirección, con o sin respeto del preaviso pactado o legal.
- **Despido disciplinario: carta** (`despido-disciplinario-carta-341`). Carta de despido disciplinario que la empresa entrega al trabajador, con los hechos imputados, su calificación y la fecha de efectos. Hay que revisar el planteamiento de la audiencia previa.
- **Despido por causas objetivas: carta** (`despido-causas-objetivas-carta-344`). Carta que la empresa entrega al trabajador para comunicar su despido por causas objetivas, con la causa, la indemnización puesta a su disposición y la fecha de efectos.
- **Dimisión o baja voluntaria del trabajador: carta** (`dimision-baja-voluntaria-trabajador-carta-333`). Carta con la que el trabajador comunica a la empresa su dimisión o baja voluntaria, con la fecha de efectos y respetando el preaviso del convenio o la costumbre.
- **Extinción del contrato de empleada del hogar: comunicación del empleador** (`extincion-contrato-empleada-hogar-comunicacion-empleador-349`). Comunicación del empleador a la empleada del hogar para extinguir su relación laboral, con la causa invocada y la fecha de efectos, conforme al régimen especial del servicio doméstico.
- **Extinción del contrato por circunstancias de la producción (tras el RDL 32/2021): comunicación** (`extincion-contrato-circunstancias-produccion-tras-rdl-32-94`). Comunicación de la empresa al trabajador para extinguir su contrato por circunstancias de la producción, tras la reforma laboral de 2021, con los datos del contrato y la causa de la extinción.
- **Extinción del contrato por edad de jubilación: carta de la empresa** (`extincion-contrato-edad-jubilacion-carta-empresa-142`). Carta de la empresa que comunica al trabajador la extinción de su contrato por haber alcanzado la edad de jubilación, con fecha de efectos y datos del contrato.
- **Propuesta de recolocación al trabajador tras el fin de la obra de construcción** (`propuesta-recolocacion-trabajador-tras-fin-obra-128`). Propuesta de la empresa al trabajador para recolocarle en otra obra al terminar aquella a la que estaba adscrito en el sector de la construcción, con las condiciones de la nueva obra.
- **Recolocación de obra de un indefinido adscrito a obra: propuesta de la empresa** (`recolocacion-obra-indefinido-adscrito-obra-propuesta-129`). Propuesta de la empresa a un trabajador indefinido adscrito a obra para recolocarle en otra obra, con las condiciones del nuevo destino, al terminar la anterior.
- **Resolución del contrato de TRADE: comunicación** (`resolucion-contrato-trade-comunicacion-354`). Comunicación de la empresa cliente al trabajador autónomo económicamente dependiente para resolver el contrato que les une, indicando la causa de la resolución.
- **Respuesta a la baja voluntaria del trabajador: carta** (`respuesta-baja-voluntaria-trabajador-carta-159`). Carta de la empresa en respuesta a la baja voluntaria del trabajador, acusando recibo, fijando la fecha de efectos y, en su caso, el preaviso aplicable y la liquidación.
- **Respuesta del trabajador a la recolocación tras el fin de la obra de construcción** (`respuesta-trabajador-recolocacion-tras-fin-obra-125`). Escrito con el que el trabajador contesta a la propuesta de recolocación de la empresa al terminar la obra de construcción, aceptándola o rechazándola.

### Demandas, papeletas y reclamaciones previas (14)

- **Despido de empleada del hogar: demanda** (`despido-empleada-hogar-demanda-123`). Demanda de la empleada del hogar ante la Sección de lo Social del Tribunal de Instancia contra el despido o desistimiento de su empleador, con pretensión de improcedencia o nulidad.
- **Despido improcedente: demanda** (`despido-improcedente-demanda-370`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia para que se declare el despido improcedente, con opción entre readmisión o indemnización y salarios de tramitación.
- **Despido nulo por discriminación por enfermedad o estado de salud: demanda** (`despido-nulo-discriminacion-enfermedad-estado-salud-107`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia contra un despido que considera nulo por discriminación debida a su enfermedad o estado de salud.
- **Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda** (`despido-nulo-negar-reincorporacion-tras-excedencia-65`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia contra un despido que declara nulo por no haberle readmitido tras una excedencia por cuidado de su pareja de hecho.
- **Despido nulo por vulneración de derechos fundamentales: demanda** (`despido-nulo-vulneracion-derechos-fundamentales-demanda-140`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia contra un despido que vulnera sus derechos fundamentales, para pedir la nulidad, la readmisión y la indemnización.
- **Despido nulo por vulnerar derechos de conciliación: demanda** (`despido-nulo-vulnerar-derechos-conciliacion-demanda-369`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia contra un despido que vulnera sus derechos de conciliación de la vida familiar y laboral, para pedir su nulidad.
- **Despido verbal: demanda** (`despido-verbal-demanda-257`). Demanda del trabajador contra un despido comunicado solo de palabra, sin carta, que pide que se declare improcedente o nulo y las consecuencias de ello.
- **Despido y reconocimiento de relación laboral: demanda** (`despido-reconocimiento-relacion-laboral-demanda-168`). Demanda que reclama a la vez que se declare la existencia de una relación laboral encubierta y que el cese del trabajador sea calificado como despido, ante el orden social.
- **Extinción a instancia del trabajador por el art. 41.3 ET: demanda** (`extincion-instancia-trabajador-art-41-3-et-demanda-403`). Demanda del trabajador que, tras una modificación sustancial de sus condiciones que le perjudica, pide extinguir el contrato con la indemnización prevista para ese supuesto.
- **Extinción del contrato de artista por incumplimiento del empresario: demanda** (`extincion-contrato-artista-incumplimiento-empresario-408`). Demanda del artista para extinguir su contrato por incumplimiento del empresario y reclamar la indemnización, con atención al régimen especial de artistas en espectáculos públicos.
- **Extinción por impago o retrasos de salario: papeleta de conciliación del trabajador** (`extincion-impago-retrasos-salario-papeleta-conciliacion-228`). Papeleta de conciliación previa con la que el trabajador pide la extinción de su contrato por impago o retrasos reiterados en el salario y la indemnización correspondiente.
- **Extinción por incumplimientos graves del empresario: demanda del trabajador** (`extincion-incumplimientos-graves-empresario-demanda-402`). Demanda del trabajador para extinguir su contrato por incumplimientos graves de la empresa, como impagos o modificaciones lesivas, y obtener la indemnización del despido improcedente.
- **Indemnización por extinción por causas objetivas: demanda** (`indemnizacion-extincion-causas-objetivas-demanda-255`). Demanda del trabajador ante el orden social para reclamar la indemnización por una extinción por causas objetivas cuando la empresa no la ha puesto a su disposición o la ha abonado incompleta.
- **TRADE: demanda de extinción por incumplimiento de la empresa cliente** (`trade-demanda-extincion-incumplimiento-empresa-cliente-406`). Demanda del trabajador autónomo económicamente dependiente para que se extinga su contrato por incumplimiento grave de la empresa cliente y se le indemnice por ello.

### Escritos y solicitudes (3)

- **Ejecución del auto de readmisión irregular: escrito** (`ejecucion-auto-readmision-irregular-escrito-119`). Escrito de la parte ejecutante ante la Sección de lo Social del Tribunal de Instancia para pedir la ejecución de un auto que declara la readmisión irregular del trabajador despedido.
- **Opción tras despido improcedente: escrito de la parte actora o representación** (`opcion-tras-despido-improcedente-escrito-parte-actora-377`). Escrito del demandante o de su representación por el que, tras la sentencia que declara el despido improcedente, ejerce ante la Sección de lo Social la opción entre readmitir o indemnizar.
- **Renuncia del fijo discontinuo al llamamiento** (`renuncia-fijo-discontinuo-llamamiento-33`). Escrito del trabajador fijo discontinuo por el que renuncia al llamamiento a la actividad, lo que puede equivaler a una baja voluntaria con sus consecuencias.

### Actas, acuerdos, planes y protocolos (1)

- **Transacción sobre el despido: acuerdo** (`transaccion-sobre-despido-acuerdo-241`). Acuerdo entre empresa y trabajador para poner fin a las discrepancias sobre un despido mediante una transacción, con la cantidad pactada y la renuncia a reclamar.

### Documentos, certificados y modelos oficiales (1)

- **Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada** (`futbol-sala-inicio-procedimiento-abreviado-resolucion-352`). Escrito del futbolista de fútbol sala para iniciar ante la comisión mixta del convenio el procedimiento abreviado que permite resolver anticipadamente su contrato con el club.
