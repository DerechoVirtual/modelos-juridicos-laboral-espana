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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-despidos-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-despidos-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-despidos-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-despidos-espana:<skill>`.

### Contratos, cláusulas y anexos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 126 | Recolocación en contrato adscrito a obra de construcción: cláusula | 2022 | `recolocacion-contrato-adscrito-obra-construccion-126` |

### Cartas y comunicaciones a la plantilla (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 19 | Aviso de audiencia previa al despido disciplinario | 2024 | `aviso-audiencia-previa-despido-disciplinario-19` |
| 94 | Extinción del contrato por circunstancias de la producción (tras el RDL 32/2021): comunicación | 2023 | `extincion-contrato-circunstancias-produccion-tras-rdl-32-94` |
| 125 | Respuesta del trabajador a la recolocación tras el fin de la obra de construcción | 2022 | `respuesta-trabajador-recolocacion-tras-fin-obra-125` |
| 128 | Propuesta de recolocación al trabajador tras el fin de la obra de construcción | 2022 | `propuesta-recolocacion-trabajador-tras-fin-obra-128` |
| 129 | Recolocación de obra de un indefinido adscrito a obra: propuesta de la empresa | 2022 | `recolocacion-obra-indefinido-adscrito-obra-propuesta-129` |
| 134 | Baja voluntaria por jubilación: carta del trabajador | 2022 | `baja-voluntaria-jubilacion-carta-trabajador-134` |
| 142 | Extinción del contrato por edad de jubilación: carta de la empresa | 2022 | `extincion-contrato-edad-jubilacion-carta-empresa-142` |
| 159 | Respuesta a la baja voluntaria del trabajador: carta | 2021 | `respuesta-baja-voluntaria-trabajador-carta-159` |
| 242 | Aviso al trabajador del fin de la excedencia | 2019 | `aviso-trabajador-fin-excedencia-242` |
| 333 | Dimisión o baja voluntaria del trabajador: carta | 2017 | `dimision-baja-voluntaria-trabajador-carta-333` |
| 341 | Despido disciplinario: carta | 2017 | `despido-disciplinario-carta-341` |
| 344 | Despido por causas objetivas: carta | 2017 | `despido-causas-objetivas-carta-344` |
| 348 | Desistimiento del alto directivo: comunicación a la empresa | 2017 | `desistimiento-alto-directivo-comunicacion-empresa-348` |
| 349 | Extinción del contrato de empleada del hogar: comunicación del empleador | 2017 | `extincion-contrato-empleada-hogar-comunicacion-empleador-349` |
| 350 | Desistimiento de la empresa frente al alto directivo: comunicación | 2017 | `desistimiento-empresa-frente-alto-directivo-comunicacion-350` |
| 354 | Resolución del contrato de TRADE: comunicación | 2017 | `resolucion-contrato-trade-comunicacion-354` |

### Demandas, papeletas y reclamaciones previas (14)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 65 | Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda | 2023 | `despido-nulo-negar-reincorporacion-tras-excedencia-65` |
| 107 | Despido nulo por discriminación por enfermedad o estado de salud: demanda | 2023 | `despido-nulo-discriminacion-enfermedad-estado-salud-107` |
| 123 | Despido de empleada del hogar: demanda | 2022 | `despido-empleada-hogar-demanda-123` |
| 140 | Despido nulo por vulneración de derechos fundamentales: demanda | 2022 | `despido-nulo-vulneracion-derechos-fundamentales-demanda-140` |
| 168 | Despido y reconocimiento de relación laboral: demanda | 2021 | `despido-reconocimiento-relacion-laboral-demanda-168` |
| 228 | Extinción por impago o retrasos de salario: papeleta de conciliación del trabajador | 2019 | `extincion-impago-retrasos-salario-papeleta-conciliacion-228` |
| 255 | Indemnización por extinción por causas objetivas: demanda | 2013 | `indemnizacion-extincion-causas-objetivas-demanda-255` |
| 257 | Despido verbal: demanda | 2013 | `despido-verbal-demanda-257` |
| 369 | Despido nulo por vulnerar derechos de conciliación: demanda | 2016 | `despido-nulo-vulnerar-derechos-conciliacion-demanda-369` |
| 370 | Despido improcedente: demanda | 2016 | `despido-improcedente-demanda-370` |
| 402 | Extinción por incumplimientos graves del empresario: demanda del trabajador | 2015 | `extincion-incumplimientos-graves-empresario-demanda-402` |
| 403 | Extinción a instancia del trabajador por el art. 41.3 ET: demanda | 2015 | `extincion-instancia-trabajador-art-41-3-et-demanda-403` |
| 406 | TRADE: demanda de extinción por incumplimiento de la empresa cliente | 2015 | `trade-demanda-extincion-incumplimiento-empresa-cliente-406` |
| 408 | Extinción del contrato de artista por incumplimiento del empresario: demanda | 2015 | `extincion-contrato-artista-incumplimiento-empresario-408` |

### Escritos y solicitudes (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 33 | Renuncia del fijo discontinuo al llamamiento | 2024 | `renuncia-fijo-discontinuo-llamamiento-33` |
| 119 | Ejecución del auto de readmisión irregular: escrito | 2023 | `ejecucion-auto-readmision-irregular-escrito-119` |
| 377 | Opción tras despido improcedente: escrito de la parte actora o representación | 2013 | `opcion-tras-despido-improcedente-escrito-parte-actora-377` |

### Actas, acuerdos, planes y protocolos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 241 | Transacción sobre el despido: acuerdo | 2019 | `transaccion-sobre-despido-acuerdo-241` |

### Documentos, certificados y modelos oficiales (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 352 | Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada | 2017 | `futbol-sala-inicio-procedimiento-abreviado-resolucion-352` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
