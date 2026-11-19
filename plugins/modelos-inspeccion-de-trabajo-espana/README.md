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

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 5.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-inspeccion-de-trabajo-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-inspeccion-de-trabajo-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-inspeccion-de-trabajo-espana:<skill>`). Son 55, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Demandas, papeletas y reclamaciones previas (1)

- **Impugnar la sanción de Seguridad Social a un empresario: demanda** (`impugnar-sancion-seguridad-social-empresario-demanda-345`). Demanda del empresario ante el orden social contra una sanción de Seguridad Social, una vez agotada la vía administrativa con el recurso de alzada. Hay que comprobar cuantía y reglas de graduación.

### Recursos (23)

- **Alzada contra sanción a empresas colaboradoras en la gestión de la Seguridad Social** (`alzada-contra-sancion-empresas-colaboradoras-gestion-268`). Recurso de alzada contra una sanción impuesta a empresas colaboradoras en la gestión de la Seguridad Social, dirigido al órgano superior del que dictó la resolución.
- **Alzada contra sanción a empresas de inserción** (`alzada-contra-sancion-empresas-insercion-282`). Recurso de alzada de una empresa de inserción contra la sanción impuesta por la Administración laboral, para pedir ante el órgano superior que se anule la resolución o se rebaje la cuantía.
- **Alzada contra sanción a empresas de trabajo temporal** (`alzada-contra-sancion-empresas-trabajo-temporal-285`). Recurso de alzada de una empresa de trabajo temporal contra la resolución sancionadora de la Administración laboral, dirigido al órgano superior para solicitar su revocación o la minoración de la multa.
- **Alzada contra sanción a empresas usuarias** (`alzada-contra-sancion-empresas-usuarias-286`). Recurso de alzada de una empresa usuaria contra la sanción impuesta por la Administración laboral, que se presenta ante el órgano superior para pedir su anulación o la reducción de la multa.
- **Alzada contra sanción a las Mutuas de AT y EP** (`alzada-contra-sancion-mutuas-at-ep-278`). Recurso de alzada del sancionado contra la resolución que impone una sanción administrativa laboral a una mutua colaboradora de la Seguridad Social, dirigido al órgano superior jerárquico para pedir su anulación o reducción.
- **Alzada contra sanción a trabajadores** (`alzada-contra-sancion-trabajadores-287`). Recurso de alzada del trabajador sancionado por una infracción administrativa laboral, dirigido al órgano superior jerárquico para pedir que se deje sin efecto la resolución o se reduzca la sanción.
- **Alzada contra sanción de la Inspección por prevención de riesgos** (`alzada-contra-sancion-inspeccion-prevencion-riesgos-293`). Recurso de alzada de la empresa contra la sanción impuesta tras un acta de la Inspección por infracción en prevención de riesgos laborales, para pedir ante el órgano superior su anulación o rebaja.
- **Alzada contra sanción de Seguridad Social (empresarios, entidades de formación y autónomos)** (`alzada-contra-sancion-seguridad-social-empresarios-281`). Recurso de alzada del empresario, la entidad de formación o el trabajador autónomo contra una sanción de Seguridad Social, dirigido al órgano superior para que anule la resolución o reduzca la multa.
- **Alzada contra sanción de Seguridad Social a trabajadores y beneficiarios de prestaciones** (`alzada-contra-sancion-seguridad-social-trabajadores-277`). Recurso de alzada contra una sanción de Seguridad Social a trabajadores o beneficiarios de prestaciones. Hay que comprobar si la vía correcta es otra, según sea leve, grave o muy grave.
- **Alzada contra sanción en materia de cooperativas** (`alzada-contra-sancion-materia-cooperativas-270`). Recurso de alzada contra una sanción impuesta en materia de cooperativas, dirigido al órgano superior del que dictó la resolución sancionadora.
- **Alzada contra sanción en materia de empleo y fomento del empleo** (`alzada-contra-sancion-materia-empleo-fomento-empleo-291`). Recurso de alzada contra una sanción en materia de empleo y fomento del empleo, dirigido al órgano superior de quien resolvió, para pedir la anulación de la resolución o la reducción de la multa.
- **Alzada contra sanción en materia de movimientos migratorios** (`alzada-contra-sancion-materia-movimientos-migratorios-269`). Recurso de alzada contra una sanción en materia de movimientos migratorios, dirigido al órgano superior del que dictó la resolución sancionadora.
- **Alzada contra sanción en materia de relaciones laborales individuales y colectivas** (`alzada-contra-sancion-materia-relaciones-laborales-305`). Recurso de alzada contra una sanción en materia de relaciones laborales individuales y colectivas, dirigido al órgano superior jerárquico para pedir que se anule la resolución o se reduzca la multa.
- **Alzada contra sanción muy grave por autorización de trabajo de extranjeros** (`alzada-contra-sancion-muy-grave-autorizacion-trabajo-271`). Recurso de alzada contra una sanción muy grave por infracciones relativas a la autorización de trabajo de extranjeros, dirigido al órgano superior del que dictó la resolución.
- **Alzada contra sanción por actividad transnacional de empresas de trabajo temporal** (`alzada-contra-sancion-actividad-transnacional-empresas-295`). Recurso de alzada de la empresa de trabajo temporal sancionada por su actividad transnacional, dirigido al órgano superior para pedir que se anule la resolución o se reduzca la multa impuesta.
- **Alzada contra sanción por incumplir las normas sobre desplazamiento de trabajadores a España** (`alzada-contra-sancion-incumplir-normas-sobre-297`). Recurso de alzada contra la sanción por incumplir las normas sobre desplazamiento de trabajadores a España, dirigido al órgano superior para solicitar la anulación de la resolución o la rebaja de la multa.
- **Alzada contra sanción por información y consulta en empresas y grupos de dimensión comunitaria** (`alzada-contra-sancion-informacion-consulta-empresas-301`). Recurso de alzada contra la sanción por incumplir las obligaciones de información y consulta en empresas y grupos de dimensión comunitaria, presentado ante el órgano superior para pedir su anulación o rebaja.
- **Alzada contra sanción por información y consulta en sociedades anónimas y cooperativas europeas** (`alzada-contra-sancion-informacion-consulta-sociedades-298`). Recurso de alzada contra la sanción por incumplir las obligaciones de información y consulta en sociedades anónimas y cooperativas europeas, dirigido al órgano superior para pedir su anulación o reducción.
- **Alzada contra sanción por obstrucción a la labor inspectora** (`alzada-contra-sancion-obstruccion-labor-inspectora-267`). Recurso de alzada contra una sanción por obstrucción a la labor inspectora, dirigido al órgano superior del que dictó la resolución. Hay que comprobar el plazo y la vía de impugnación.
- **Alzada por caducidad de las actuaciones de comprobación de la Inspección** (`alzada-caducidad-actuaciones-comprobacion-inspeccion-263`). Recurso de alzada contra una sanción de la Inspección de Trabajo cuando han caducado las actuaciones de comprobación por superar el plazo máximo legal, dirigido al órgano superior del que dictó la resolución.
- **Alzada por concurrencia de sanciones** (`alzada-concurrencia-sanciones-265`). Recurso de alzada contra una sanción por concurrencia de sanciones por los mismos hechos, dirigido al órgano superior del que dictó la resolución sancionadora.
- **Alzada por prescripción de infracciones** (`alzada-prescripcion-infracciones-264`). Recurso de alzada contra una sanción de la Inspección de Trabajo y Seguridad Social por haber prescrito las infracciones, dirigido al órgano superior del que dictó la resolución.
- **Contencioso contra actas de la Inspección de Trabajo** (`contencioso-contra-actas-inspeccion-trabajo-246`). Recurso contencioso-administrativo contra una liquidación de cuotas de Seguridad Social y el acta de infracción por los mismos hechos, ante la Sección de lo Contencioso-Administrativo del Tribunal de Instancia.

### Escritos y solicitudes (28)

- **Alegaciones al acta de infracción de empresas colaboradoras en la gestión de la Seguridad Social** (`alegaciones-acta-infraccion-empresas-colaboradoras-273`). Alegaciones de la empresa colaboradora en la gestión de la Seguridad Social frente al acta de infracción de la Inspección, dirigidas al órgano instructor para rebatirla y pedir el archivo o la reducción.
- **Alegaciones al acta de infracción de empresas de inserción** (`alegaciones-acta-infraccion-empresas-insercion-284`). Alegaciones de la empresa de inserción frente al acta de infracción levantada por la Inspección, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción de empresas de trabajo temporal** (`alegaciones-acta-infraccion-empresas-trabajo-temporal-290`). Alegaciones de la empresa de trabajo temporal frente al acta de infracción de la Inspección, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la reducción de la sanción propuesta.
- **Alegaciones al acta de infracción de empresas usuarias** (`alegaciones-acta-infraccion-empresas-usuarias-288`). Alegaciones de la empresa usuaria frente al acta de infracción de la Inspección, dirigidas al órgano instructor para rebatir los hechos y la calificación y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción de las Mutuas de AT y EP** (`alegaciones-acta-infraccion-mutuas-at-ep-280`). Alegaciones de la mutua colaboradora de la Seguridad Social frente al acta de infracción de la Inspección, dirigidas al órgano instructor para rebatirla y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción de movimientos migratorios** (`alegaciones-acta-infraccion-movimientos-migratorios-272`). Escrito de alegaciones de la empresa frente al acta de infracción por movimientos migratorios levantada por la Inspección, dirigido al órgano instructor para pedir el archivo o la rebaja de la propuesta.
- **Alegaciones al acta de infracción de prevención de riesgos laborales** (`alegaciones-acta-infraccion-prevencion-riesgos-laborales-294`). Alegaciones de la empresa frente al acta de infracción en prevención de riesgos laborales, dirigidas al órgano instructor para rebatir los hechos y la calificación y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción de relaciones laborales individuales y colectivas** (`alegaciones-acta-infraccion-relaciones-laborales-306`). Alegaciones frente al acta de infracción en materia de relaciones laborales individuales y colectivas, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción de Seguridad Social (trabajadores, beneficiarios y solicitantes)** (`alegaciones-acta-infraccion-seguridad-social-279`). Alegaciones del trabajador, beneficiario o solicitante frente al acta de infracción de Seguridad Social, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción de trabajadores** (`alegaciones-acta-infraccion-trabajadores-289`). Alegaciones del trabajador frente al acta de infracción que se le imputa, dirigidas al órgano instructor del procedimiento sancionador para rebatir los hechos y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción en materia de cooperativas** (`alegaciones-acta-infraccion-materia-cooperativas-275`). Alegaciones de la cooperativa frente al acta de infracción de la Inspección en materia de cooperativas, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción en materia de empleo y fomento del empleo** (`alegaciones-acta-infraccion-materia-empleo-fomento-292`). Alegaciones frente al acta de infracción en materia de empleo y fomento del empleo, dirigidas al órgano instructor del procedimiento sancionador para rebatir los hechos y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción muy grave por autorización de trabajo de extranjeros** (`alegaciones-acta-infraccion-muy-grave-autorizacion-274`). Alegaciones de la empresa frente al acta de infracción muy grave por irregularidades en la autorización de trabajo de extranjeros, dirigidas al órgano instructor para pedir su archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción por actividad transnacional de empresas de trabajo temporal** (`alegaciones-acta-infraccion-actividad-transnacional-296`). Alegaciones de la empresa de trabajo temporal frente al acta de infracción por su actividad transnacional, dirigidas al órgano instructor para rebatirla y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción por desplazamiento de trabajadores a España** (`alegaciones-acta-infraccion-desplazamiento-trabajadores-299`). Alegaciones de la empresa frente al acta de infracción por incumplir las normas sobre desplazamiento de trabajadores a España, dirigidas al órgano instructor para pedir su archivo o la reducción de la sanción.
- **Alegaciones al acta de infracción por información y consulta en grupos de dimensión comunitaria** (`alegaciones-acta-infraccion-informacion-consulta-grupos-302`). Alegaciones frente al acta de infracción por incumplir la información y consulta en grupos de dimensión comunitaria, dirigidas al órgano instructor para rebatirla y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción por información y consulta en sociedades europeas** (`alegaciones-acta-infraccion-informacion-consulta-300`). Alegaciones frente al acta de infracción por incumplir las obligaciones de información y consulta en sociedades europeas, dirigidas al órgano instructor para rebatirla y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de infracción por obstrucción a la labor inspectora** (`alegaciones-acta-infraccion-obstruccion-labor-inspectora-276`). Alegaciones del sujeto responsable frente al acta de infracción por obstrucción a la labor inspectora, dirigidas al órgano instructor para negar los hechos y pedir el archivo o la rebaja de la sanción.
- **Alegaciones al acta de Seguridad Social (empresarios, entidades de formación y autónomos)** (`alegaciones-acta-seguridad-social-empresarios-entidades-283`). Alegaciones del empresario, la entidad de formación o el autónomo frente al acta de Seguridad Social, dirigidas al órgano instructor para rebatir los hechos y pedir el archivo o la rebaja de la sanción.
- **Alegaciones negando la relación laboral y pidiendo comunicación de oficio (art. 151 LJS)** (`alegaciones-negando-relacion-laboral-pidiendo-399`). Alegaciones de quien niega la existencia de relación laboral en un procedimiento de oficio ante la jurisdicción social, para pedir que se comunique de oficio; el modelo tiene base normativa desfasada y debe revisarse antes de usarlo.
- **Autorización para representar ante la Inspección de Trabajo** (`autorizacion-representar-ante-inspeccion-trabajo-221`). Autorización por la que una persona o empresa apodera a un representante para actuar en su nombre ante la Inspección de Trabajo y Seguridad Social en las actuaciones y trámites que se indiquen.
- **Caducidad de las actuaciones de comprobación de la Inspección: alegaciones** (`caducidad-actuaciones-comprobacion-inspeccion-261`). Alegaciones del interesado en un procedimiento sancionador laboral para sostener que han caducado las actuaciones de comprobación de la Inspección y pedir, por ello, el archivo del expediente.
- **Caducidad de las actuaciones previas de la ITSS: declaración** (`caducidad-actuaciones-previas-itss-declaracion-396`). Declaración del interesado en un procedimiento sancionador laboral para que se reconozca la caducidad de las actuaciones previas de la Inspección de Trabajo y se archive el expediente derivado de ellas.
- **Concurrencia de sanciones: alegaciones** (`concurrencia-sanciones-alegaciones-266`). Alegaciones del interesado en un procedimiento sancionador laboral para denunciar la concurrencia de sanciones por los mismos hechos y pedir que no se le sancione dos veces o se archive el expediente.
- **Pedir ampliación del plazo del requerimiento de la Inspección de Trabajo** (`pedir-ampliacion-plazo-requerimiento-inspeccion-trabajo-30`). Escrito del empresario que ha recibido un requerimiento de la Inspección de Trabajo para solicitar que se amplíe el plazo concedido para cumplirlo o aportar la documentación pedida.
- **Pedir certificado de silencio administrativo** (`pedir-certificado-silencio-administrativo-358`). Solicitud a la Administración de un certificado que acredite que ha transcurrido el plazo para resolver sin respuesta expresa, para poder acreditar el silencio administrativo y, en su caso, reclamar o recurrir.
- **Prescripción de infracciones: alegaciones** (`prescripcion-infracciones-alegaciones-262`). Alegaciones del interesado en un procedimiento sancionador laboral para sostener que la infracción imputada ha prescrito y pedir el archivo del expediente sin imposición de sanción.
- **Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección** (`reconocer-responsabilidad-pagar-voluntariamente-sancion-152`). Escrito por el que el presunto infractor reconoce su responsabilidad y paga voluntariamente la sanción propuesta por la Inspección de Trabajo, para beneficiarse de la reducción y poner fin al procedimiento.

### Documentos, certificados y modelos oficiales (3)

- **Citación oficial del Inspector de Trabajo y Seguridad Social** (`citacion-oficial-inspector-trabajo-seguridad-social-393`). Modelo de citación oficial por la que el Inspector de Trabajo y Seguridad Social convoca a la empresa o a la persona interesada a comparecer y aportar la documentación necesaria en una actuación inspectora.
- **Citación oficial del Subinspector Laboral de Empleo y Seguridad Social** (`citacion-oficial-subinspector-laboral-empleo-seguridad-394`). Modelo de citación oficial por la que el Subinspector Laboral de Empleo y Seguridad Social convoca a la empresa o persona interesada a comparecer y aportar documentación en una actuación de comprobación.
- **Requerimiento normalizado de la ITSS** (`requerimiento-normalizado-itss-395`). Modelo normalizado de requerimiento por el que la Inspección de Trabajo y Seguridad Social exige a la empresa subsanar un incumplimiento o aportar documentación en un plazo determinado.
