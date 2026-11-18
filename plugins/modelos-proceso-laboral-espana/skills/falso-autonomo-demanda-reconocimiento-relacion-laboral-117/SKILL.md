---
name: falso-autonomo-demanda-reconocimiento-relacion-laboral-117
description: "Redacta el escrito «Falso autónomo: demanda de reconocimiento de relación laboral» (formulario 117 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falso autónomo: demanda de reconocimiento de relación laboral

> Formulario 0117 del plugin **Proceso laboral** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Aportación anticipada de documental y pericial: art. 82.5 LRJS, diez días antes del juicio y en formato electrónico (LO 1/2025).
- Si a los treinta días hábiles de la papeleta no se ha celebrado la conciliación, el trámite se tiene por cumplido (art. 65.2 LRJS, LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (3 veces)
- [ ] IMPORTE (2 veces)
- [ ] Nº (3 veces)
- [ ] Nº DE DOCUMENTO
- [ ] ÓRGANO O PERSONA
- [ ] CORREO ELECTRÓNICO
- [ ] Otros 13 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…con domicilio en [LOCALIDAD], en»; «… ajena, la cual dirijo contra la empresa»; «…con domicilio en [LOCALIDAD], en»; «…s profesionales por cuenta de la empresa»; «…, en la sección»; «… trabajo las siguientes características:»; «…con sujeción a un horario determinado de»; «…, en su calidad de»; «…os recogidos en el convenio colectivo de»; «…con el resultado de»; «…conciliación previa preceptiva. QUINTO.-»; «…con despacho profesional en»; …

## Elecciones que hay que hacer

- Letrado/a / Graduado/a social colegiado/a / Procurador/a

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 10.1 de la LRJS
- art. 17 de la LRJS
- art. 63 de la LRJS
- arts. 1 y 8 del ET
- artículo 82.5 de la LRJS

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

### Formulario 0117 · Falso autónomo: demanda de reconocimiento de relación laboral

- Año del modelo: 2023
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 34 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: Aportación anticipada de documental y pericial: art. 82.5 LRJS, diez días antes del juicio y en formato electrónico (LO 1/2025). · Si a los treinta días hábiles de la papeleta no se ha celebrado la conciliación, el trámite se tiene por cumplido (art. 65.2 LRJS, LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
HECHOS
Fundamentos de derecho
Suplico
Otrosí 1. Representación
Otrosí 2. Documentos aportados
Otrosí 3. Prueba anticipada
Otrosí 4. Pruebas solicitadas
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, provisto de DNI [DNI/NIE] con domicilio en [LOCALIDAD], en [COMPLETAR], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA de reconocimiento de existencia de relación laboral por cuenta ajena, la cual dirijo contra la empresa [COMPLETAR] con domicilio en [LOCALIDAD], en [COMPLETAR] que deberá tramitarse por los trámites del proceso ordinario, a fin de que sea declarada la relación laboral del demandante con la empresa demandada, en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

HECHOS

PRIMERO.- La parte demandante viene prestando sus servicios profesionales por cuenta de la empresa [COMPLETAR], desde el día [FECHA] percibiendo una retribución de [IMPORTE] euros mensuales, y teniendo una jornada de [Nº] horas diarias durante [Nº] días a la semana.

La relación laboral se formalizó mediante un contrato de arrendamiento de servicios de fecha [FECHA] en el que la parte demandante figura como autónomo/a, si bien en todo momento ha prestado sus servicios por cuenta de la demandada en régimen de relación laboral común, como se relata a continuación.

SEGUNDO.- La parte demandante presta servicios en el centro de trabajo de la demandada, sito en [LOCALIDAD], en la sección [COMPLETAR] y dentro del círculo rector y organicista de la empleadora, recibiendo instrucciones como desempeñar su trabajo y teniendo el trabajo las siguientes características: [COMPLETAR].

TERCERO.- La empresa no reconoce el carácter laboral de la relación, al haberse formalizado por un arrendamiento de servicios, por lo que se ejercita esta acción al encubrirse un contrato de trabajo entre las partes.

En efecto, la relación que une a ambas partes es de carácter laboral, ya que la parte demandante presta sus servicios dentro del ámbito de organización y dirección de la empresa, con sujeción a un horario determinado de [COMPLETAR], realizando una jornada de [Nº] horas semanales.

En el desempeño de su trabajo, la parte demandante utiliza la maquinaria de la empresa, en las mismas condiciones o de manera indiferenciada a la de las otras personas trabajadoras que tienen contrato de trabajo, recibiendo las órdenes directamente de D./Dña. [NOMBRE Y APELLIDOS], en su calidad de [COMPLETAR], debiendo solicitar las vacaciones a la mencionada persona responsable, y recibiendo una retribución fija mensual de [IMPORTE] euros.

CUARTO.- La relación de la parte demandante con la empresa reúne las notas de ajenidad y dependencia, las cuales han sido fraudulentamente alteradas como si se tratara de una relación por cuenta propia, habiendo exigido la empresa la firma de un contrato de arrendamiento de servicios como autónomo para el desempeño del trabajo, cuando la parte demandante no reúne dichas características de autónomo, al no disponer de infraestructura productiva, ni material propio, utilizando para su actividad los medios de la empresa, con arreglo a los criterios organizativos fijados por la empresa y, como contraprestación a la prestación de servicios, el demandante percibe una cantidad fija mensual, que no está en función del resultado de su actividad, desempeñando las mismas funciones que las demás personas trabajadoras de la empresa en el referido centro de trabajo.

QUINTO.- En estas condiciones, la parte demandante solicitó a la dirección de la empresa la formalización de contrato de trabajo por cuenta ajena, de carácter indefinido, con el reconocimiento de los correspondientes derechos recogidos en el convenio colectivo de [COMPLETAR] así como su inclusión en el correspondiente Régimen General de la Seguridad Social, lo cual fue denegado por la empresa, manteniendo que era una relación de arrendamiento de servicios, que no tenía carácter laboral.

SEXTO.- En base a las circunstancias expuestas, concurren abrumadoramente todos los requisitos para el reconocimiento de existencia de relación laboral, puesto que se dan los requisitos de voluntariedad, retribución, ajenidad y dependencia, puesto que el demandante asiste al centro de trabajo del empleador con sometimiento a horario; desempeña personalmente su trabajo, entra en el turno de suplencias o sustituciones de los trabajadores del centro de trabajo; está inserto en la organización de trabajo del empleador o empresario, que se encarga de programar su actividad y recibe una remuneración periódica por su trabajo, sin el lucro especial que caracteriza la actividad del autónomo. Asimismo, la parte demandante no tiene organización propia, los productos elaborados son para la empleadora, quien adopta las decisiones concernientes a los precios o tarifas, y la selección de clientela, o personas a atender.

Por tanto, concurren las notas específicas de ajenidad del trabajo y de dependencia en el régimen de ejecución del mismo, por lo que existe un contrato de trabajo, sometido a la legislación laboral.

SÉPTIMO.- Que se presentó papeleta de demanda proponiendo acto de conciliación ante el correspondiente servicio administrativo, habiéndose celebrado el preceptivo acto, tal y como se acredita con el acta de dicha conciliación, el día [FECHA] con el resultado de [COMPLETAR] (acompaño como documento número [Nº DE DOCUMENTO] copia del acta).

Por lo expuesto, se ejercita acción para que se reconozca la existencia de relación laboral y se condene a la empresa a formalizar el correspondiente contrato de trabajo de carácter indefinido, en las condiciones laborales establecidas en el convenio colectivo de aplicación, con los demás pronunciamientos inherentes.

Fundamentos de derecho

PRIMERO.- Competencia. Es competente el Tribunal al que nos dirigimos por ser el lugar de prestación de servicios conforme al art. 10.1 de la LRJS.

SEGUNDO.- Legitimación e intervención del FOGASA. Están legitimados activa y pasivamente las partes conforme a lo dispuesto en el art. 17 de la LRJS.

TERCERO.- Procedimiento: El proceso debe seguir los trámites del juicio ordinario de los arts. 80 y siguientes de la LRJS.

CUARTO.- Requisitos procesales: El art. 63 de la LRJS en cuanto al cumplimiento del requisito de la conciliación previa preceptiva.

QUINTO.- [COMPLETAR]. En cuanto al fondo, son de aplicación los arts. 1 y 8 del ET, que establecen que se presumirá existente el contrato de trabajo entre todo el que presta un servicio por cuenta y dentro del ámbito de organización y dirección de otro y el que lo recibe a cambio de una retribución de aquél. La jurisprudencia ha reiterado que cuatro son los elementos constitutivos o notas características del contrato de trabajo: voluntariedad, retribución, ajenidad y dependencia, y que los contratos tienen la naturaleza jurídica que se deriva de su contenido obligacional, independientemente de la denominación que le otorguen los intervinientes, siendo así que la determinación del carácter laboral o no de la relación que une a las partes, no es algo que quede a la libre disposición de éstas, sino que es una calificación que debe surgir del contenido real de las prestaciones concertadas y de la concurrencia de los requisitos que legalmente delimitan el tipo contractual.

Por lo expuesto,

AL TRIBUNAL SUPLICA: Que teniendo por presentado este escrito se sirva admitirlo, con sus copias, tenga por formulada Demanda en ejercicio de la acción de reconocimiento de existencia de relación laboral y, previos los trámites legales, dicte sentencia por la que se que se reconozca la existencia de relación laboral entre las partes y se condene a la empresa a estar y pasar por dicha declaración, y a formalizar el correspondiente contrato de trabajo de carácter indefinido, con los demás pronunciamientos inherentes.

PRIMER OTROSI DIGO: A los efectos legales se manifiesta que acudiré al acto del Juicio representado por el [ÓRGANO O PERSONA] D./Dña [NOMBRE Y APELLIDOS] con despacho profesional en [COMPLETAR] correo electrónico [CORREO ELECTRÓNICO],designando este domicilio para las notificaciones que se deriven del procedimiento y firmando asimismo esta demanda.

Por lo que, SUPLICO AL TRIBUNAL Tenga por hecha esta manifestación a los efectos oportunos.

SEGUNDO OTROSÍ DIGO que se acompaña en anexo relación de documentos, debidamente foliados y con índice electrónico, para su debida localización y consulta.

Por lo que, SUPLICO AL TRIBUNAL tenga hecha esta manifestación a los efectos oportunos y por aportados los documentos relacionados en el anexo.

TERCER OTROSI DIGO: Que al amparo del artículo 82.5 de la LRJS [NOTA DE REVISIÓN: Tras la LO 1/2025 la aportación anticipada de documental y pericial está en el art. 82.5 y con diez días de antelación, en formato electrónico. Fuente: art. 82.5 LRJS (red. art. 24.5 LO 1/2025, vigente 3-4-2025); LRJS (Ley 36/2011), BOE-A-2011-15936; LO 1/2025, BOE-A-2025-76.] se interesa que se requiera a la demandada para que aporten anticipadamente al menos con diez días de antelación al acto de juicio, la siguiente prueba documental:

Por lo que, SUPLICO AL TRIBUNAL acuerde requerir a las codemandadas para la aportación anticipada de la documental que dejo señalada.

CUARTO OTROSÍ DIGO Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el art. 90.3 de la Ley reguladora de la jurisdicción social, interesa al derecho de esta parte que se practiquen las diligencias de citación de la siguiente prueba que esta parte pretende proponer en el juicio:

- INTERROGATORIO DE LA DEMANDADA: Del legal representante, que deberán ser citado bajo el apercibimiento de tener por reconocidos los hechos del interrogatorio que le sean perjudiciales si no compareciere.

- TESTIFICAL, de D./Dña [NOMBRE Y APELLIDOS] con domicilio en [LOCALIDAD], como [COMPLETAR] del centro de trabajo de la empresa demandada.

Por lo que, SUPLICO AL TRIBUNAL admita las diligencias de citación para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

Es justicia que pido, en L. y F.

Firma demandante Firma [ELEGIR: Letrado/a / Graduado/a social colegiado/a / Procurador/a]

════════════════════════════════════════════════════════════════════════
