---
name: extincion-impago-retrasos-salario-papeleta-conciliacion-228
description: "Redacta el escrito «Extinción por impago o retrasos de salario: papeleta de conciliación del trabajador» (formulario 228 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Extinción por impago o retrasos de salario: papeleta de conciliación del trabajador

> Formulario 0228 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Extinción por voluntad del trabajador: el art. 50 ET fue redactado de nuevo por la LO 1/2025 (DF 26.ª, en vigor el 3-4-2025); indemnización de despido improcedente (33 días por año, máximo 24 mensualidades, art. 56.1 ET sin cambios).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] ACTO O RESOLUCIÓN
- [ ] NIF
- [ ] FECHA (4 veces)
- [ ] Nº
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…cumplimiento contractual del empresario.»; «…E MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE»; «…O.- Presto mis servicios para la empresa»; «…horas, de»; «…horas, de [COMPLETAR] a»; «… al grupo profesional de la categoría de»; «…, desempeñando el puesto de trabajo de»; «…elación laboral el convenio colectivo de»; «…y publicado en el Boletín Oficial de»; «…, a [FECHA]. Fdo.:»

## Elecciones que hay que hacer

- impago de salarios / retrasos continuados en el pago de salarios
- temporal / indefinida
- completo / parcial
- impagos de salarios / retrasos continuados en el pago de salarios

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de impago de salarios / En caso de retrasos continuados en el pago de salarios — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 49.1.j) ET
- art. 50.1.b) ET
- art. 63 LRJS
- artículo 83 ET
- art. 65.1 LRJS
- Ley Orgánica 1/2025

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

### Formulario 0228 · Extinción por impago o retrasos de salario: papeleta de conciliación del trabajador

- Año del modelo: 2019
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 25 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Extinción por voluntad del trabajador: el art. 50 ET fue redactado de nuevo por la LO 1/2025 (DF 26.ª, en vigor el 3-4-2025); indemnización de despido improcedente (33 días por año, máximo 24 mensualidades, art. 56.1 ET sin cambios).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
Firmas

En virtud del art. 49.1.j) ET, el contrato de trabajo puede extinguirse por voluntad del trabajador, fundamentada en un incumplimiento contractual del empresario. [COMPLETAR]. Entre otras, será justa causa para que el trabajador pueda solicitar la extinción del contrato, la falta de pago o retrasos continuados en el abono del salario pactado (art. 50.1.b) ET) [NOTA DE REVISIÓN: Desde la LO 1/2025 (en vigor el 3-4-2025) el art. 50.1.b) ET precisa que hay retraso cuando se supera en quince días la fecha de pago y que concurre la causa si se adeudan, en un año, tres mensualidades completas aun no consecutivas o hay retraso durante seis meses aun no consecutivos. Fuente: ET (RDLeg 2/2015), BOE-A-2015-11430, art. 50.1.b) (redacción LO 1/2025, DF 26.ª, BOE-A-2025-76).].

El presente formulario acumula la solicitud de extinción de la relación laboral a la reclamación de los salarios debidos. De acuerdo con el art. 63 LRJS, deberá plantearse intento de conciliación o, en su caso, de mediación ante el servicio administrativo correspondiente o ante el órgano que asuma estas funciones, que podrá constituirse mediante los acuerdos interprofesionales o los convenios colectivos a los que se refiere el artículo 83 ET, así como mediante los acuerdos de interés profesional a los que se refiere la Ley del Estatuto del Trabajo Autónomo.

La presentación de la solicitud de conciliación o de mediación interrumpirá la prescripción o suspenderá la caducidad de acciones desde la fecha de dicha presentación, reiniciándose o reanudándose respectivamente el cómputo de los plazos al día siguiente de intentada la conciliación o mediación o transcurridos quince días hábiles desde su presentación sin que se haya celebrado. (art. 65.1 LRJS)

La papeleta de conciliación ante el Servicio de Mediación, Arbitraje y Conciliación (SMAC) se podrá presentar telemáticamente a través de las oficinas virtuales o sedes electrónicas de las correspondientes Comunidades Autónomas. Cuando se presenta de esta forma se cumplimenta en línea el impreso de solicitud al que se puede anexa cualquier documentación complementaria, entre la que se recomienda adjuntar la papeleta de conciliación redactada con detalle.

Actualizado según las modificaciones realizadas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de DNI nº [DNI/NIE], con domicilio a efectos de notificaciones el sito en [LOCALIDAD], teléfono [TELÉFONO], correo electrónico [CORREO ELECTRÓNICO], ante el Servicio de Mediación, Arbitraje y Conciliación comparezco y, como mejor proceda en Derecho, DIGO:

Que por medio del presente escrito formulo PAPELETA DE CONCILIACIÓN sobre EXTINCIÓN CAUSAL DE LA RELACIÓN LABORAL por [ELEGIR: impago de salarios / retrasos continuados en el pago de salarios] y RECLAMACIÓN DE CANTIDAD contra [ACTO O RESOLUCIÓN]; empresa sita en [LOCALIDAD], provista de NIF nº [NIF] en la persona de su representante legal.

Se funda la presente papeleta en los siguientes:

HECHOS

PRIMERO.- Presto mis servicios para la empresa [COMPLETAR] desde el [FECHA] en el centro de trabajo que la empresa tiene sito en [LOCALIDAD] mediante una relación laboral [ELEGIR: temporal / indefinida] a tiempo [ELEGIR: completo / parcial], realizando una jornada de trabajo semanal de [Nº] horas, de [COMPLETAR] a [COMPLETAR] con el siguiente horario.

SEGUNDO.- Que dichos servicios los presto adscrito al grupo profesional de la categoría de [COMPLETAR], desempeñando el puesto de trabajo de [COMPLETAR], percibiendo una retribución mensual con prorrateo de pagas extraordinarias de [IMPORTE] €.

TERCERO-

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de impago de salarios / En caso de retrasos continuados en el pago de salarios — el texto de cada opción no venía en el formulario original]

CUARTO.- A la relación laboral el convenio colectivo de [COMPLETAR] aprobado por Resolución de [FECHA] y publicado en el Boletín Oficial de [COMPLETAR] de fecha [FECHA].

QUINTO.- Que no he sido ni soy representante de los trabajadores y no estoy afiliado a ningún sindicato.

En su virtud,

SUPLICO AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN que teniendo por presentado este escrito junto con sus copias, se sirva admitirlo, por realizadas las manifestaciones en él contenidas y, en méritos del mismo, se tenga por formulada PAPELETA DE CONCILIACIÓN DE EXTINCIÓN DE LA RELACIÓN LABORAL Y RECLAMACIÓN DE CANTIDAD por la que la que se proceda a señalar día y hora, previa citación de las partes, para la celebración del oportuno acto de conciliación en el que la empresa reclamada:

a) Se avenga a reconocer la EXTINCIÓN DE LA RELACIÓN LABORAL por [ELEGIR: impagos de salarios / retrasos continuados en el pago de salarios] como si de un despido improcedente se tratara, abonando la correspondiente indemnización en base a la antigüedad y salario postulado en esta papeleta.
b) Me abone la cantidad total de [IMPORTE] € por los conceptos que constan en el cuerpo de la presente papeleta, más el 10% sobre dicha cantidad en concepto de interés por mora.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Fdo.: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
