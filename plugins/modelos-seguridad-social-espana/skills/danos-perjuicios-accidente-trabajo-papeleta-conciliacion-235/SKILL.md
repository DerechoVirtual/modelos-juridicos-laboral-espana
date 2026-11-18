---
name: danos-perjuicios-accidente-trabajo-papeleta-conciliacion-235
description: "Redacta el escrito «Daños y perjuicios por accidente de trabajo: papeleta de conciliación» (formulario 235 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Daños y perjuicios por accidente de trabajo: papeleta de conciliación

> Formulario 0235 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Papeleta: a los treinta días hábiles sin celebrarse el acto se tiene por cumplido el trámite (art. 65.2 LRJS, LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO (2 veces)
- [ ] CALLE (2 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (6 veces)
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…E MEDIACION, ARBITRAJE Y CONCILIACION DE»; «…R ACCIDENTE DE TRABAJO contra la empresa»; «…contra la MUTUA DE ACCIDENTES DE TRABAJO»; «…sional correspondiente a la categoría de»; «…y realizando las funciones de»; «…ve por la Mutua de Accidentes de Trabajo»; «…ención de riesgos laborales, en concreto»; «…, a [FECHA]. Fdo.:»

## Elecciones que hay que hacer

- anuales / mensuales

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 83 ET
- art. 63 LRJS
- art. 65.1 LRJS
- art. 142.1 LRJS
- Ley Orgánica 1/2025
- Real Decreto Legislativo 5/2000

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

### Formulario 0235 · Daños y perjuicios por accidente de trabajo: papeleta de conciliación

- Año del modelo: 2019
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 25 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Papeleta: a los treinta días hábiles sin celebrarse el acto se tiene por cumplido el trámite (art. 65.2 LRJS, LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
ALEGACIONES
SUPLICO AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN
Firmas

Para reclamar una indemnización por accidente laboral, de forma previa a la interposición de la demanda deberemos presentar papeleta de conciliación ante el servicio administrativo correspondiente o ante el órgano que asuma estas funciones, que podrá constituirse mediante los acuerdos interprofesionales o los convenios colectivos a los que se refiere el artículo 83 ET, así como mediante los acuerdos de interés profesional a los que se refiere la Ley del Estatuto del Trabajo Autónomo (art. 63 LRJS).

La presentación de la solicitud de conciliación o de mediación interrumpirá la prescripción o suspenderá la caducidad de acciones desde la fecha de dicha presentación, reiniciándose o reanudándose respectivamente el cómputo de los plazos al día siguiente de intentada la conciliación o mediación o transcurridos quince días hábiles desde su presentación sin que se haya celebrado. (art. 65.1 LRJS)

El modelo se dirige contra una empresa y la mutua de accidentes de trabajo; si la reclamación desembocara en demanda y no se consignara en la misma el nombre de la mutua, el Letrado de la Administración de Justicia requerirá al empresario demandado para presentar el documento acreditativo de la cobertura de riesgo (art. 142.1 LRJS).

La papeleta de conciliación ante el Servicio de Mediación, Arbitraje y Conciliación (SMAC) se podrá presentar telemáticamente a través de las oficinas virtuales o sedes electrónicas de las correspondientes Comunidades Autónomas. Cuando se presenta de esta forma se cumplimenta en línea el impreso de solicitud al que se puede anexa cualquier documentación complementaria, entre la que se recomienda adjuntar la papeleta de conciliación redactada con detalle.

Actualizado según las modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

AL SERVICIO DE MEDIACION, ARBITRAJE Y CONCILIACION DE [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI. nº [NÚMERO] y domicilio en calle [CALLE], teléfono [TELÉFONO], correo electrónico [CORREO ELECTRÓNICO], ante este Organismo comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo expediente de CONCILIACIÓN en reclamación de INDEMNIZACIÓN POR DAÑOS Y PERJUICIOS OCASIONADOS POR ACCIDENTE DE TRABAJO contra la empresa [COMPLETAR], con domicilio en la calle [CALLE], en la persona de su legal representante y contra la MUTUA DE ACCIDENTES DE TRABAJO [COMPLETAR], con domicilio en [LOCALIDAD], en la persona de su legal representante.

Se apoya el presente escrito en las siguientes

ALEGACIONES

PRIMERA. He venido prestando servicios para la empresa citada desde el [FECHA] en el centro de trabajo sito en [LOCALIDAD], en el grupo profesional correspondiente a la categoría de [COMPLETAR] y realizando las funciones de [COMPLETAR].

Mi salario era de [IMPORTE] euros brutos [ELEGIR: anuales / mensuales], incluido el prorrateo de pagas extraordinarias.

SEGUNDA. Con fecha [FECHA], cuando realizaba funciones propias de mi categoría, sufrí un accidente de trabajo, calificado de grave por la Mutua de Accidentes de Trabajo [COMPLETAR], causando baja por Incapacidad Temporal desde el [FECHA], hasta que por Resolución del Instituto Nacional de la Seguridad Social de fecha [FECHA] se me reconoció una incapacidad permanente total para mi profesión habitual, con el siguiente cuadro residual:

Como consecuencia del accidente sufrido me han quedado las siguientes secuelas:

TERCERA. Tras la oportuna visita de la Inspección de Trabajo a la empresa, con fecha [FECHA] se levantó acta de infracción nº [NÚMERO], sancionando a la empresa por la comisión de una falta grave, tipificada en el art. de la Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, por incumplimiento de la normativa de prevención de riesgos laborales, en concreto [COMPLETAR].

CUARTA. Por lo tanto, y al existir una relación de causalidad directa entre el incumplimiento de las normas de seguridad y prevención de riesgos laborales y el accidente ocurrido, la empresa es responsable de los daños y perjuicios ocasionados, debiendo abonarme una indemnización de [IMPORTE] euros.

Por lo expuesto,

SUPLICO AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN

Que teniendo por presentado este escrito, junto con sus copias, se sirva admitirlo y, previos los trámites oportunos, tenga por instado acto de conciliación en reclamación de INDEMNIZACIÓN POR DAÑOS Y PERJUICIOS OCASIONADOS POR ACCIDENTE DE TRABAJO, para que en el mismo la empresa demandada me abone la cantidad de [IMPORTE] euros en concepto de daños y perjuicios.

Es de Justicia que pido en [LUGAR], a [FECHA].

Fdo.: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
