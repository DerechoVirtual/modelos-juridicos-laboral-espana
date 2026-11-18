---
name: demanda-reconocimiento-accidente-trabajo-dana-28-octubre-25
description: "Redacta el escrito «Demanda de reconocimiento de accidente de trabajo por la DANA (28 octubre a 4 noviembre de 2024)» (formulario 25 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda de reconocimiento de accidente de trabajo por la DANA (28 octubre a 4 noviembre de 2024)

> Formulario 0025 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Demanda inicial: sin número de plaza. El art. 25 RDL 6/2024 asimila a accidente de trabajo solo a efectos de la prestación económica de IT (procesos iniciados entre el 28-10 y el 31-12-2024) y del cálculo de la cuantía de IP y de muerte y supervivencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…mero de afiliación a la Seguridad Social»; «…apacidad temporal y baja médica entre el»; «…y el»; «…como consecuencia de la DANA acaecida en»; «…los días»; «…P SEGUNDO.- Que el médico facultativo de»; «…, expediente»; «…, en la localidad de»; «…acredita con la siguiente documentación:»

## Elecciones que hay que hacer

- INCAPACIDAD TEMPORAL / INCAPACIDAD PERMANENTE
- daños personales / lesiones / accidente
- Incapacidad Temporal / Incapacidad Permanente
- temporal / permanente

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 25 del Real Decreto-ley 6/2024
- artículo 71 de la Ley 36/2011
- artículos 1, 2, 6 y 10 de la Ley 36/2011
- art. 25 del Real Decreto-ley 6/2024
- Ley 6/2024
- Real Decreto-ley 8/2024

## Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero el «Texto del formulario» del final de este fichero, con su cabecera, y la parte de `../indice/marco.md` que afecte al caso (plazos, órgano, procedimiento, conciliación o mediación previa, reclamación previa o vía administrativa, según el caso).
3. Pide los datos de la lista. Lo que el usuario no sepa se queda como hueco visible.
4. Decide las elecciones y los párrafos opcionales según los hechos. Redacta las partes que el original no traía.
5. Aplica los avisos y las notas de revisión. Comprueba con `buscar_articulo` cada norma citada y, si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Indica el plazo y el cauce: desde cuándo cuenta, cuándo vence y ante qué órgano se presenta.
7. Antes de entregarlo, pasa `verificar_escrito` con las frases del escrito que citan normas o sentencias y corrige lo que señale.
8. Entrega el escrito en **Word (.docx)** con formato de escrito (usa la skill de Word disponible) y, si es corto, también en el chat.
9. Cierra con: datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator y, si algún dato sale de internet, cuál es y su enlace.

## Texto del formulario

### Formulario 0025 · Demanda de reconocimiento de accidente de trabajo por la DANA (28 octubre a 4 noviembre de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 21 campos de relleno marcados en blanco
- Avisos de la revisión: Demanda inicial: sin número de plaza. El art. 25 RDL 6/2024 asimila a accidente de trabajo solo a efectos de la prestación económica de IT (procesos iniciados entre el 28-10 y el 31-12-2024) y del cálculo de la cuantía de IP y de muerte y supervivencia.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
MEDIOS DE PRUEBA
Firmas

El artículo 25 del Real Decreto-Ley 6/2024 expresa que los procesos de incapacidad temporal producidos en los municipios afectados por la DANA que se inicien desde el 28 de octubre hasta el 31 de diciembre de 2024 como consecuencia de los siniestros tendrán (excepcionalmente) la consideración de situación asimilada a accidente de trabajo, exclusivamente a efectos de la prestación económica de incapacidad temporal del sistema de Seguridad Social. Asimismo, las pensiones de incapacidad permanente, muerte y supervivencia, así como la prestación económica por incapacidad permanente parcial tendrán la consideración, con carácter excepcional, de situación asimilada a accidente de trabajo a los exclusivos efectos del cálculo de su cuantía económica.

Formulario actualizado conforme a las novedades introducidas por el Real Decreto-ley 8/2024, de 28 de noviembre

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: Es una demanda: aún no hay plaza asignada; basta la Sección de lo Social del Tribunal de Instancia de la sede. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE], y número de afiliación a la Seguridad Social [COMPLETAR], y con domicilio a efectos de notificaciones en el Despacho del Letrado/a D./Dña. [NOMBRE Y APELLIDOS], sito en [LOCALIDAD], teléfono [TELÉFONO], correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho, DICE:

Que por medio del presente escrito formula DEMANDA DE DECLARACIÓN DE CONTINGENCIA COMO ACCIDENTE DE TRABAJO, causante de los períodos de incapacidad temporal y baja médica entre el [COMPLETAR] y el [COMPLETAR] y, por tanto, del derecho de este demandante a beneficiarse de las prestaciones de [ELEGIR: INCAPACIDAD TEMPORAL / INCAPACIDAD PERMANENTE] correspondientes a dicha contingencia contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, en la persona de su representante legal, todo ello en base a los siguientes hechos y fundamentos de Derecho:

HECHOS

PRIMERO.- Que como consecuencia de la DANA acaecida en [COMPLETAR] los días [COMPLETAR], sufrí una serie de [ELEGIR: daños personales / lesiones / accidente] que determinaron mi situación de [ELEGIR: Incapacidad Temporal / Incapacidad Permanente] con efectos desde el día o una IT que posteriormente derivó en IP

SEGUNDO.- Que

el médico facultativo de [COMPLETAR]

el Equipo de Valoración de Incapacidades determinó que la contingencia de la que derivaba mi patología era enfermedad común y no accidente de trabajo.

TERCERO.- Que, al no estar conforme con dicha calificación de la contingencia, este demandante solicitó la determinación de la contingencia como accidente de trabajo, que fue denegada por resolución de fecha [FECHA], contra la que se formuló reclamación previa a la vía judicial que, asimismo fue denegada por resolución de fecha [FECHA], expediente [COMPLETAR].

Se acompañan como DOCS. N.º [NÚMERO] copia de las citadas resoluciones y la reclamación previa.

CUARTO.- Que el hecho causante se produjo el día [FECHA], en la localidad de [COMPLETAR] y fue consecuencia directa de un siniestro ocasionado por la DANA que azotó a diferentes municipios de España, como se acredita con la siguiente documentación: [COMPLETAR], por lo que debe considerarse la contingencia derivada de accidente de trabajo en virtud de lo establecido en el artículo 25 del Real Decreto-ley 6/2024, de 5 de noviembre, por el que se adoptan medidas urgentes de respuesta ante los daños causados por la Depresión Aislada en Niveles Altos (DANA) en diferentes municipios entre el 28 de octubre y el 4 de noviembre de 2024.

Asimismo, y en aplicación de lo establecido en el apartado 1 del citado artículo, como consecuencia de la asimilación a accidente de trabajo, no se requiere para su percepción, período mínimo de cotización.

QUINTO.- Que, por lo anteriormente expuesto y no encontrando conforme a Derecho la referida Resolución en cuanto a la contingencia de la que deriva la incapacidad reconocida, por medio del presente escrito, dentro del plazo legalmente establecido y de conformidad con lo señalado por el artículo 71 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, vengo a interponer DEMANDA ante la Sección de lo Social del Tribunal de Instancia.

A los anteriores hechos les son de aplicación los siguientes,

FUNDAMENTOS DE DERECHO

I.- Es competente el Tribunal al que me dirijo en virtud de lo dispuesto en los artículos 1, 2, 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social.

II.- Son de aplicación el artículo 71 de la Ley 36/2011, que regula la reclamación previa, y los artículos 140 a 146 de la misma, reguladores de los procesos seguidos ante Seguridad Social.

III.- En cuanto al fondo del asunto, resulta de aplicación el art. 25 del Real Decreto-ley 6/2024, de 5 de noviembre, por el que se adoptan medidas urgentes de respuesta ante los daños causados por la Depresión Aislada en Niveles Altos (DANA) en diferentes municipios entre el 28 de octubre y el 4 de noviembre de 2024.

Por lo expuesto,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA, que teniendo por presentado este escrito en tiempo y forma, con los documentos que se acompañan, se sirva admitirlo y, en su virtud, tenga por interpuesta demanda sobre DETERMINACIÓN DE CONTINGENCIAS contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, tramitando la misma conforme a Derecho, citando a las partes para los trámites previos de conciliación y, en su caso, de juicio, concluyendo las actuaciones con una sentencia estimatoria de la demanda, con los efectos legales que se deriven de tal pronunciamiento, en la que se acuerde declarar que mi situación de incapacidad [ELEGIR: temporal / permanente] deriva de accidente de trabajo.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO que se solicita la reclamación de oficio al INSS del expediente y antecedentes que posea en relación con el contenido de la demanda.

SEGUNDO OTROSI DIGO que esta parte acudirá al acto del juicio oral representada de Letrado/a.

TERCER OTROSI DIGO que interesa al Derecho de esta parte que se practiquen en el acto del juicio oral los siguientes

MEDIOS DE PRUEBA

- DOCUMENTAL, TESTIFICAL Y PERICIAL: la aportada con la demanda y la que esta parte aportará en el acto del juicio.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones y por propuesta la prueba, la admita y la estime pertinente.

Por ser de Justicia que reitero en el lugar y fecha "ut supra"

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
