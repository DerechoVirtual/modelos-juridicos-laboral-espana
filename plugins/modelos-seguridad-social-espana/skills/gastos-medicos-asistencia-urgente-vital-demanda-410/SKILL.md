---
name: gastos-medicos-asistencia-urgente-vital-demanda-410
description: "Redacta el escrito «Gastos médicos por asistencia urgente y vital: demanda de reintegro (modelo 1)» (formulario 410 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Gastos médicos por asistencia urgente y vital: demanda de reintegro (modelo 1)

> Formulario 0410 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Reintegro de gastos sanitarios: materia de prestaciones del art. 2.o) LRJS, no de la letra b).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO (3 veces)
- [ ] LOCALIDAD
- [ ] CALLE (3 veces)
- [ ] NÚMERO DE LA CALLE
- [ ] FECHA (7 veces)
- [ ] Nº (3 veces)
- [ ] HORA
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… Y VITAL, contra el SERVICIO DE SALUD de»; «…oras, acudió al Servicio de Urgencias de»; «…rendimiento de retina y se le remitió al»; «…horas, el actor acudió al citado»; «…médicos, se dirigió a la clínica privada»; «…ndante solicitó del Servicio de Salud de»; «… y vital, contra el Servicio de Salud de»; «…a presente demanda asistiré dirigido por»; «…ente en que, por el Servicio de Salud de»; «…e que por el Servicio de Oftalmología de»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 80 de la Ley 36/2011
- art. 9 de la Ley 16/2003
- art. 4.3 del Real Decreto 1030/2006

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

### Formulario 0410 · Gastos médicos por asistencia urgente y vital: demanda de reintegro (modelo 1)

- Año del modelo: 2015
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 35 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (HORA, NÚMERO DE LA CALLE)
- Avisos de la revisión: Reintegro de gastos sanitarios: materia de prestaciones del art. 2.o) LRJS, no de la letra b).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS] mayor de edad, provisto de D.N.I. nº [NÚMERO], con domicilio en [LOCALIDAD], c/ [CALLE], nº [NÚMERO], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho,

DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA EN RECLAMACIÓN DE REINTEGRO DE GASTOS MÉDICOS POR ASISTENCIA SANITARIA DE CARÁCTER URGENTE Y VITAL, contra el SERVICIO DE SALUD de [COMPLETAR], con domicilio en c/ [CALLE], nº [NÚMERO DE LA CALLE]

A fin de que sea condenado en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

HECHOS

El demandante está afiliado y en alta en el Régimen General de la Seguridad Social con el número [NÚMERO]

El día [FECHA] el demandante sufrió una pérdida de visión del ojo derecho por lo que, a las [Nº] horas, acudió al Servicio de Urgencias de [COMPLETAR], dependiente del Servicio de Salud demandado, donde se le diagnosticó desprendimiento de retina y se le remitió al [COMPLETAR] para valoración.

El mismo día, a las [HORA] horas, el actor acudió al citado [COMPLETAR], donde se le diagnosticó desprendimiento de retina con múltiples desgarros periféricos, se le indicó reposo absoluto y con la cabeza hacia el hombro izquierdo y se le citó para acudir al Servicio de Oftalmología el día [FECHA] a las [Nº] horas.

El Servicio de Oftalmología, tras examinar la paciente, prescribió intervención quirúrgica, y se le incluyó en lista de espera con carácter normal (no urgente ni preferente).

Dado que el demandante había perdido la visión del ojo y que las molestias iban en aumento, ante la insatisfactoria solución de los servicios médicos, se dirigió a la clínica privada [COMPLETAR], donde se emitió el informe que se acompaña como documento número [Nº DE DOCUMENTO], donde se prescribía la intervención quirúrgica del desprendimiento de retina con carácter de urgencia, dado que el paciente mantenía la mácula aplicada y estaba a punto de levantarse.

A la vista de la gravedad y riesgo que presentaba la patología, el demandante fue intervenido en la citada clínica en la misma fecha, con carácter de urgencia, realizándose cerclaje con banda de silicona de 360° y vitrectomía con intercambio del vítreo por C3F8 al 13%, tal como se acredita en el informe que acompaño como documento número

Como consecuencia de esta intervención, el demandante abonó la cantidad de [IMPORTE] euros, según consta en la factura que se acompaña como documento número [Nº DE DOCUMENTO]

En fecha [FECHA] el demandante solicitó del Servicio de Salud de [COMPLETAR] el reintegro de los gastos médicos que fue denegado por resolución de fecha [FECHA], notificada en fecha [FECHA], al considerar que la intervención no revestía los caracteres de asistencia urgente de carácter vital.

No obstante esta decisión administrativa, lo cierto es que es claro que concurren los requisitos necesarios para entender que existe urgencia vital en este caso, toda vez que el desprendimiento de retina estaba a punto de afectar a la mácula, por lo que resultaba evidente la perentoriedad de la solución quirúrgica al haber perdido la visión del ojo derecho. El retraso en la intervención que se derivaba de la inclusión en una lista de espera en todo caso era claramente peligrosa para la salud visual del paciente con riesgo patente de pérdida definitiva de visión.

Que planteada la preceptiva reclamación previa ante el referido Servicio de Salud, ha sido desestimada por resolución expresa de fecha [FECHA], notificada en fecha [FECHA],que se acompaña como documento número

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

Es competente el Tribunal, tanto por razón de la condición de los litigantes, como por la materia y territorio, de conformidad a lo que determinan los artículos 2.o), 6 y 10.2.a) de la Ley 36/2011 [NOTA DE REVISIÓN: La letra b) del art. 2 es la responsabilidad por daños; las prestaciones de Seguridad Social (asistencia sanitaria incluida) son la letra o). Fuente: art. 2.o) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], reguladora de la jurisdicción social.

Se han hecho constar en la presente demanda todos los requisitos formales exigidos por el art. 80 de la Ley 36/2011, reguladora de la jurisdicción social.

Los arts. 71 y 140 de la Ley reguladora de la jurisdicción social, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad gestora demandada.

En cuanto al fondo del asunto, son de aplicación: a) el art. 9 de la Ley 16/2003, de 28 de mayo, de cohesión y calidad del Sistema Nacional de Salud, que establece que las prestaciones sanitarias del Sistema Nacional de Salud únicamente se facilitarán por el personal legalmente habilitado, en centros y servicios, propios o concertados, del Sistema Nacional de Salud, salvo en situaciones de riesgo vital, cuando se justifique que no pudieron ser utilizados los medios de aquél, sin perjuicio de lo establecido en los convenios internacionales en los que España sea parte; y b) el art. 4.3 del Real Decreto 1030/2006, de 15 de septiembre, por el que se establece la cartera de servicios comunes del Sistema Nacional de Salud y el procedimiento para su actualización, que dispone que “la cartera de servicios comunes únicamente se facilitará por centros, establecimientos y servicios del Sistema Nacional de Salud, propios o concertados, salvo en situaciones de riesgo vital, cuando se justifique que no pudieron ser utilizados los medios de aquél. En esos casos de asistencia sanitaria urgente, inmediata y de carácter vital que hayan sido atendidos fuera del Sistema Nacional de Salud, se reembolsarán los gastos de la misma, una vez comprobado que no se pudieron utilizar oportunamente los servicios de aquél y que no constituye una utilización desviada o abusiva de esta excepción”.

Existe la situación de riesgo vital, al concurrir los requisitos expresados, entre otras, en la STS de 4 de julio de 2007 que afirma que "en la actualidad son cuatro los requisitos exigidos para que proceda el reintegro de gastos por asistencia sanitaria ajena al sistema público. Dos de ellos positivos, cuales son que se trate de urgencia inmediata y que sea de carácter vital; y dos negativos, consistentes en que no hubiera posibilidad de utilización de los servicios de la sanidad pública y que el caso no constituya una utilización abusiva de la excepción”, añadiendo dicha sentencia que "conforme a notoria literatura médica, el desprendimiento de retina es un problema urgente, hasta el punto de que si todavía no ha afectado a la mácula requiere atención sanitaria dentro de las 24 posteriores a los primeros síntomas, al objeto de evitar el deterioro o pérdida irreversible de la visión, en tanto que si la mácula ya se ha desprendido el grado de urgencia resulta menor, admitiendo que la intervención quirúrgica se demore de una semana a diez días".

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentada esta demanda de reintegro de gastos médicos por asistencia sanitaria urgente y vital, contra el Servicio de Salud de [COMPLETAR], con sus respectivas copias y documentos que se adjuntan, se sirva admitirla, darle el turno que corresponda, citar a las partes para la celebración del acto del juicio y, en definitiva, dictar sentencia por la que estimando la presente demanda se condene a la demandada al pago de la cantidad de [IMPORTE] euros con más los intereses correspondientes.

OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por [COMPLETAR] en ejercicio, designando a D./D.ª [NOMBRE Y APELLIDOS], con domicilio en c/ [CALLE], nº [Nº], el cual se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes

SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, interesa al derecho de esta parte la verificación de los siguientes medios de prueba:

- DOCUMENTAL consistente en que, por el Servicio de Salud de [COMPLETAR] se acompañe el correspondiente expediente tramitado referente al reintegro de los gastos médicos solicitados.

- MÁS DOCUMENTAL, a fin de que por el Servicio de Oftalmología de [COMPLETAR] se aporte el historial clínico del demandante derivado de la atención médica recibida en dicho centro en fecha

SUPLICO tenga por propuestos los medios de prueba solicitados y acuerde lo conducente para su práctica.

Por ser Justicia que pido para principal y otrosí en [LUGAR], a [DÍA] de [MES] de [AÑO].

(Firma)

================================================================================
