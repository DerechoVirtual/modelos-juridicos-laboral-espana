# Alegaciones y recursos ante la Inspección de Trabajo · España

> Plugin de Claude Code `modelos-inspeccion-de-trabajo-espana` · **55 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para defenderse en las actuaciones de la Inspección de Trabajo: alegaciones a las actas de infracción (por materias), recursos de alzada contra las sanciones, caducidad y prescripción, y sanciones de la LISOS con la reducción por pago voluntario.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 55 está al final):

- **Demandas, papeletas y reclamaciones previas** (1). Por ejemplo: Impugnar la sanción de Seguridad Social a un empresario: demanda.
- **Recursos** (23). Por ejemplo: Contencioso contra actas de la Inspección de Trabajo; Alzada por caducidad de las actuaciones de comprobación de la Inspección; Alzada por prescripción de infracciones.
- **Escritos y solicitudes** (28). Por ejemplo: Pedir ampliación del plazo del requerimiento de la Inspección de Trabajo; Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección; Autorización para representar ante la Inspección de Trabajo.
- **Documentos, certificados y modelos oficiales** (3). Por ejemplo: Citación oficial del Inspector de Trabajo y Seguridad Social; Citación oficial del Subinspector Laboral de Empleo y Seguridad Social; Requerimiento normalizado de la ITSS.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Alegaciones a un acta de infracción de Seguridad Social»
   - «Alegaciones por caducidad de las actuaciones de la Inspección»
   - «Recurso de alzada contra una sanción por obstrucción a la labor inspectora»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-inspeccion-de-trabajo-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-inspeccion-de-trabajo-espana:pedir-ampliacion-plazo-requerimiento-inspeccion-trabajo-30`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-inspeccion-de-trabajo-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-inspeccion-de-trabajo-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-inspeccion-de-trabajo-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-inspeccion-de-trabajo-espana:<skill>`.

### Demandas, papeletas y reclamaciones previas (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 345 | Impugnar la sanción de Seguridad Social a un empresario: demanda | 2013 | `impugnar-sancion-seguridad-social-empresario-demanda-345` |

### Recursos (23)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 246 | Contencioso contra actas de la Inspección de Trabajo | 2018 | `contencioso-contra-actas-inspeccion-trabajo-246` |
| 263 | Alzada por caducidad de las actuaciones de comprobación de la Inspección | 2017 | `alzada-caducidad-actuaciones-comprobacion-inspeccion-263` |
| 264 | Alzada por prescripción de infracciones | 2017 | `alzada-prescripcion-infracciones-264` |
| 265 | Alzada por concurrencia de sanciones | 2017 | `alzada-concurrencia-sanciones-265` |
| 267 | Alzada contra sanción por obstrucción a la labor inspectora | 2017 | `alzada-contra-sancion-obstruccion-labor-inspectora-267` |
| 268 | Alzada contra sanción a empresas colaboradoras en la gestión de la Seguridad Social | 2017 | `alzada-contra-sancion-empresas-colaboradoras-gestion-268` |
| 269 | Alzada contra sanción en materia de movimientos migratorios | 2017 | `alzada-contra-sancion-materia-movimientos-migratorios-269` |
| 270 | Alzada contra sanción en materia de cooperativas | 2017 | `alzada-contra-sancion-materia-cooperativas-270` |
| 271 | Alzada contra sanción muy grave por autorización de trabajo de extranjeros | 2017 | `alzada-contra-sancion-muy-grave-autorizacion-trabajo-271` |
| 277 | Alzada contra sanción de Seguridad Social a trabajadores y beneficiarios de prestaciones | 2017 | `alzada-contra-sancion-seguridad-social-trabajadores-277` |
| 278 | Alzada contra sanción a las Mutuas de AT y EP | 2017 | `alzada-contra-sancion-mutuas-at-ep-278` |
| 281 | Alzada contra sanción de Seguridad Social (empresarios, entidades de formación y autónomos) | 2017 | `alzada-contra-sancion-seguridad-social-empresarios-281` |
| 282 | Alzada contra sanción a empresas de inserción | 2017 | `alzada-contra-sancion-empresas-insercion-282` |
| 285 | Alzada contra sanción a empresas de trabajo temporal | 2017 | `alzada-contra-sancion-empresas-trabajo-temporal-285` |
| 286 | Alzada contra sanción a empresas usuarias | 2017 | `alzada-contra-sancion-empresas-usuarias-286` |
| 287 | Alzada contra sanción a trabajadores | 2017 | `alzada-contra-sancion-trabajadores-287` |
| 291 | Alzada contra sanción en materia de empleo y fomento del empleo | 2017 | `alzada-contra-sancion-materia-empleo-fomento-empleo-291` |
| 293 | Alzada contra sanción de la Inspección por prevención de riesgos | 2017 | `alzada-contra-sancion-inspeccion-prevencion-riesgos-293` |
| 295 | Alzada contra sanción por actividad transnacional de empresas de trabajo temporal | 2017 | `alzada-contra-sancion-actividad-transnacional-empresas-295` |
| 297 | Alzada contra sanción por incumplir las normas sobre desplazamiento de trabajadores a España | 2017 | `alzada-contra-sancion-incumplir-normas-sobre-297` |
| 298 | Alzada contra sanción por información y consulta en sociedades anónimas y cooperativas europeas | 2017 | `alzada-contra-sancion-informacion-consulta-sociedades-298` |
| 301 | Alzada contra sanción por información y consulta en empresas y grupos de dimensión comunitaria | 2017 | `alzada-contra-sancion-informacion-consulta-empresas-301` |
| 305 | Alzada contra sanción en materia de relaciones laborales individuales y colectivas | 2017 | `alzada-contra-sancion-materia-relaciones-laborales-305` |

### Escritos y solicitudes (28)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 30 | Pedir ampliación del plazo del requerimiento de la Inspección de Trabajo | 2024 | `pedir-ampliacion-plazo-requerimiento-inspeccion-trabajo-30` |
| 152 | Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección | 2021 | `reconocer-responsabilidad-pagar-voluntariamente-sancion-152` |
| 221 | Autorización para representar ante la Inspección de Trabajo | 2019 | `autorizacion-representar-ante-inspeccion-trabajo-221` |
| 261 | Caducidad de las actuaciones de comprobación de la Inspección: alegaciones | 2017 | `caducidad-actuaciones-comprobacion-inspeccion-261` |
| 262 | Prescripción de infracciones: alegaciones | 2017 | `prescripcion-infracciones-alegaciones-262` |
| 266 | Concurrencia de sanciones: alegaciones | 2017 | `concurrencia-sanciones-alegaciones-266` |
| 272 | Alegaciones al acta de infracción de movimientos migratorios | 2017 | `alegaciones-acta-infraccion-movimientos-migratorios-272` |
| 273 | Alegaciones al acta de infracción de empresas colaboradoras en la gestión de la Seguridad Social | 2017 | `alegaciones-acta-infraccion-empresas-colaboradoras-273` |
| 274 | Alegaciones al acta de infracción muy grave por autorización de trabajo de extranjeros | 2017 | `alegaciones-acta-infraccion-muy-grave-autorizacion-274` |
| 275 | Alegaciones al acta de infracción en materia de cooperativas | 2017 | `alegaciones-acta-infraccion-materia-cooperativas-275` |
| 276 | Alegaciones al acta de infracción por obstrucción a la labor inspectora | 2017 | `alegaciones-acta-infraccion-obstruccion-labor-inspectora-276` |
| 279 | Alegaciones al acta de infracción de Seguridad Social (trabajadores, beneficiarios y solicitantes) | 2017 | `alegaciones-acta-infraccion-seguridad-social-279` |
| 280 | Alegaciones al acta de infracción de las Mutuas de AT y EP | 2017 | `alegaciones-acta-infraccion-mutuas-at-ep-280` |
| 283 | Alegaciones al acta de Seguridad Social (empresarios, entidades de formación y autónomos) | 2017 | `alegaciones-acta-seguridad-social-empresarios-entidades-283` |
| 284 | Alegaciones al acta de infracción de empresas de inserción | 2017 | `alegaciones-acta-infraccion-empresas-insercion-284` |
| 288 | Alegaciones al acta de infracción de empresas usuarias | 2017 | `alegaciones-acta-infraccion-empresas-usuarias-288` |
| 289 | Alegaciones al acta de infracción de trabajadores | 2017 | `alegaciones-acta-infraccion-trabajadores-289` |
| 290 | Alegaciones al acta de infracción de empresas de trabajo temporal | 2017 | `alegaciones-acta-infraccion-empresas-trabajo-temporal-290` |
| 292 | Alegaciones al acta de infracción en materia de empleo y fomento del empleo | 2017 | `alegaciones-acta-infraccion-materia-empleo-fomento-292` |
| 294 | Alegaciones al acta de infracción de prevención de riesgos laborales | 2017 | `alegaciones-acta-infraccion-prevencion-riesgos-laborales-294` |
| 296 | Alegaciones al acta de infracción por actividad transnacional de empresas de trabajo temporal | 2017 | `alegaciones-acta-infraccion-actividad-transnacional-296` |
| 299 | Alegaciones al acta de infracción por desplazamiento de trabajadores a España | 2017 | `alegaciones-acta-infraccion-desplazamiento-trabajadores-299` |
| 300 | Alegaciones al acta de infracción por información y consulta en sociedades europeas | 2017 | `alegaciones-acta-infraccion-informacion-consulta-300` |
| 302 | Alegaciones al acta de infracción por información y consulta en grupos de dimensión comunitaria | 2017 | `alegaciones-acta-infraccion-informacion-consulta-grupos-302` |
| 306 | Alegaciones al acta de infracción de relaciones laborales individuales y colectivas | 2017 | `alegaciones-acta-infraccion-relaciones-laborales-306` |
| 358 | Pedir certificado de silencio administrativo | 2017 | `pedir-certificado-silencio-administrativo-358` |
| 396 | Caducidad de las actuaciones previas de la ITSS: declaración | 2015 | `caducidad-actuaciones-previas-itss-declaracion-396` |
| 399 | Alegaciones negando la relación laboral y pidiendo comunicación de oficio (art. 151 LJS) | 2012 | `alegaciones-negando-relacion-laboral-pidiendo-399` |

### Documentos, certificados y modelos oficiales (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 393 | Citación oficial del Inspector de Trabajo y Seguridad Social | 2015 | `citacion-oficial-inspector-trabajo-seguridad-social-393` |
| 394 | Citación oficial del Subinspector Laboral de Empleo y Seguridad Social | 2015 | `citacion-oficial-subinspector-laboral-empleo-seguridad-394` |
| 395 | Requerimiento normalizado de la ITSS | 2015 | `requerimiento-normalizado-itss-395` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
