---
name: demanda-efectos-economicos-incapacidad-temporal-tras-139
description: "Redacta el escrito «Demanda por efectos económicos de la incapacidad temporal tras un proceso anterior» (formulario 139 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda por efectos económicos de la incapacidad temporal tras un proceso anterior

> Formulario 0139 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- El art. 60 TRLGSS es el complemento para la reducción de la brecha de género: para el nacimiento del subsidio de IT, art. 173 LGSS; el art. 174.3 citado sigue vigente (red. Ley 2/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (9 veces)
- [ ] NÚMERO
- [ ] DESCRIBIR
- [ ] Nº DE EXPEDIENTE
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…abajadora por cuenta ajena de la empresa»; «…, con la categoría de»; «…propias de dicha actividad, entre otras,»; «… temporal con las siguientes patologías:»; «…ticia que pido para principal y otrosíes»; «…,en»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 2.o), 6 y 10 de la Ley 36/2011
- art. 80 de la LJS
- arts. 71 y 140 de la LJS
- art. 174.3 de la LGSS

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

### Formulario 0139 · Demanda por efectos económicos de la incapacidad temporal tras un proceso anterior

- Año del modelo: 2022
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 26 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: El art. 60 TRLGSS es el complemento para la reducción de la brecha de género: para el nacimiento del subsidio de IT, art. 173 LGSS; el art. 174.3 citado sigue vigente (red. Ley 2/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
Digo
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Otrosí digo I
Otrosí digo II
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS],mayor de edad, provista de D.N.I. nº [Nº], con domicilio en [LOCALIDAD], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA EN RECLAMACIÓN DE LOS EFECTOS ECONÓMICOS DE LA PRESTACIÓN DE INCAPACIDAD TEMPORAL, amparada en el art. 174 del TRLGSS, contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], y TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], que deberá tramitarse por la modalidad procesal de prestaciones de Seguridad Social, a fin de que sean condenadas en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

HECHOS

PRIMERO.- La persona demandante nació el día [FECHA], estando afiliada y en alta en el Régimen General de la Seguridad Social con el número [NÚMERO], en su condición de persona trabajadora por cuenta ajena de la empresa [COMPLETAR], con la categoría de [COMPLETAR], siendo las funciones propias de dicha actividad, entre otras, [COMPLETAR].

En fecha [FECHA] inició proceso por incapacidad temporal con las siguientes patologías: [COMPLETAR].

En fecha [FECHA], una vez agotada la duración máxima establecida para la prestación de incapacidad temporal y su prórroga, que venía percibiendo la parte actora, el INSS resolvió iniciar un expediente de incapacidad permanente que fue denegado por resolución de fecha [FECHA].

SEGUNDO.- En fecha [FECHA], la actora causó nueva baja médica por la patología consistente en [DESCRIBIR], dentro de los ciento ochenta días siguientes a la resolución denegatoria de la incapacidad permanente antes mencionada.

Por resolución de fecha [FECHA], el INSS consideró que dicha baja se produjo por la misma o similar patología que el proceso anterior ya agotado, por lo que acordó dejar sin efectos económicos la citada baja médica, sin realizar ningún tipo de valoración, examen o revisión sobre la posibilidad de que la actora pueda recuperar su capacidad laboral.

TERCERO.- Como se ha expuesto, tras el agotamiento del plazo máximo de la primera incapacidad temporal sin declaración de incapacidad permanente, la actora presentó una posterior baja médica antes del transcurso del plazo de más de 180 días naturales, que la entidad gestora considera que se produce por la misma o similar patología, lo cual se niega por cuanto que, tal como ha quedado expuesto, las patologías traen causa de distintos motivos.

En cualquier caso, el INSS no ha realizado ninguna valoración ni alega ningún motivo ni dato objetivo que permita considerar si la persona demandante podía o no recuperar su capacidad laboral.

CUARTO.- Disconforme con dicha resolución, la persona demandante interpuso reclamación previa alegando dichos motivos con invocación de la doctrina jurisprudencial establecida en las SSTS de 6 de noviembre de 2019, de 4 febrero de 2021 y de 23 noviembre de 2021, que afirma que la potestad del INSS no es, en absoluto, discrecional y que la resolución administrativa debe basarse en criterios objetivos que justifiquen la denegación, lo cual exige que la resolución se pronuncie sobre el estado de salud de la persona trabajadora que ha obtenido de los servicios médicos de salud una nueva baja médica y, al objeto de denegarle los correspondientes efectos económicos, el INSS debe pronunciarse fundadamente sobre las posibilidades de recuperar su capacidad laboral, atendidos los órganos competentes para evaluar, calificar y revisar la situación de incapacidad permanente de la persona trabajadora, lo que no se cumple en este caso conforme ha quedado expuesto.

QUINTO.- La citada reclamación previa planteada ante el INSS, ha sido desestimada por resolución expresa de fecha [FECHA], notificada en fecha [FECHA], la cual se acompaña como documento número 1.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- Es competente el Tribunal, tanto por razón de la condición de los litigantes, como por la materia y territorio, de conformidad a lo que determinan los artículos 2.o), 6 y 10 de la Ley 36/2011 [NOTA DE REVISIÓN: El art. 1 LRJS no tiene apartados; las prestaciones de Seguridad Social son la letra o) del art. 2 (la «b)» venía de la LPL de 1995). Fuente: arts. 1, 2.o) y 10.2.a) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], Reguladora de la Jurisdicción Social (LJS).

SEGUNDO.- Se han hecho constar en la presente demanda todos los requisitos formales exigidos por el art. 80 de la LJS, debiendo tramitarse el procedimiento por la modalidad procesal de prestaciones de Seguridad Social.

TERCERO.- Los arts. 71 y 140 de la LJS, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad gestora codemandada.

CUARTO.- En cuanto al fondo del asunto, el art. 174.3 de la LGSS establece, en su párrafo tercero, que, aun cuando se trate de la misma o similar patología y no hubiesen transcurrido ciento ochenta días naturales desde la denegación de la incapacidad permanente, podrá iniciarse un nuevo proceso de incapacidad temporal, por una sola vez, cuando el Instituto Nacional de la Seguridad Social, a través de los órganos competentes para evaluar, calificar y revisar la situación de incapacidad permanente de la persona trabajadora, considere que la persona trabajadora puede recuperar su capacidad laboral. Para ello, el Instituto Nacional de la Seguridad Social acordará la baja a los exclusivos efectos de la prestación económica por incapacidad temporal.

Las SSTS de 6 de noviembre de 2019 STS núm. 158/2021, de 4 febrero; STS núm. 1143/2021, de 23 noviembre exigen que, para que sea válida la denegación de los efectos económicos de la prestación de IT, el INSS debe pronunciarse necesariamente sobre el estado de salud de la persona trabajadora que ha obtenido de los servicios médicos de salud una nueva baja médica y sobre las posibilidades de recuperar su capacidad laboral, atendidos los órganos competentes para evaluar, calificar y revisar la situación de incapacidad permanente de la persona trabajadora.

QUINTO.- En cuanto a los efectos, es de aplicación el art. 60 del TRLGSS, debiendo reconocerse los efectos económicos [NOTA DE REVISIÓN (comprobar): El art. 60 LGSS es el complemento para la reducción de la brecha de género. El nacimiento del subsidio de IT está en el art. 173 LGSS (y la retroactividad de tres meses, en el 53.1). Propuesta: «art. 173 del TRLGSS». Fuente: arts. 53, 60 y 173 LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.] de la prestación desde el inicio del proceso de baja, así como el abono de las cantidades atrasadas con más los intereses legales correspondientes.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentada esta demanda en reclamación de los efectos económicos de la prestación de incapacidad temporal, contra el INSS y TGSS, con sus respectivas copias y documentos que se adjuntan, se sirva admitirla, darle el turno que corresponda, citar a las partes para la celebración del acto del juicio y, en definitiva, dictar sentencia por la que estimando la presente demanda se reconozca el derecho de la demandante a la percepción de las cantidades correspondientes a la prestación de IT durante el periodo de baja iniciado el día [FECHA], condenando a las demandadas al abono de las cantidades atrasadas con más los intereses legales correspondientes.

PRIMER OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por Letrado/a (o Graduado/a Social) en ejercicio, designando a D./D.ª [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], el cual se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes

SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, interesa al derecho de esta parte la verificación de los siguientes medios de prueba:

- DOCUMENTAL consistente en que se remita el correspondiente expediente tramitado con el número [Nº DE EXPEDIENTE] referente a la solicitud de pago de la prestación de incapacidad temporal.

- Otros medios de prueba: testifical, pericial, etc.

SUPLICO tenga por propuestos los medios de prueba solicitados y acuerde lo conducente para su práctica.

Por ser Justicia que pido para principal y otrosíes [COMPLETAR],en [COMPLETAR]

(firma)

════════════════════════════════════════════════════════════════════════
