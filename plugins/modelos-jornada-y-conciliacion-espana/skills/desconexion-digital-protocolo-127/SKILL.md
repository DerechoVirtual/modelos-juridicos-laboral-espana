---
name: desconexion-digital-protocolo-127
description: "Redacta el escrito «Desconexión digital: protocolo» (formulario 127 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Desconexión digital: protocolo

> Formulario 0127 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ecnológicas. PROTOCOLO DE DESCONEXIÓN DE»; «… constituye una comisión, que se reunirá»; «…, a [FECHA]. Firmas:»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0127 · Desconexión digital: protocolo

- Año del modelo: 2022
- Revisión 17-11-2026: 1 párrafos repetibles señalados; 6 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Documento en el que se recoge la política interna de la entidad para garantizar el respeto de su tiempo de descanso, permisos y vacaciones, así como de su intimidad personal y familiar.

El art. 88 de la LOPD establece que el protocolo de desconexión digital debe elaborarse previa audiencia con la representación legal de los trabajadores, y que en el mismo se definirán las modalidades de ejercicio del derecho a la desconexión y las acciones de formación y de sensibilización del personal sobre un uso razonable de las herramientas tecnológicas que evite el riesgo de fatiga informática. Y, en particular, se preservará el derecho a la desconexión digital en los supuestos de realización total o parcial del trabajo a distancia así como en el domicilio del empleado vinculado al uso con fines laborales de herramientas tecnológicas.

PROTOCOLO DE DESCONEXIÓN DE [COMPLETAR]

PRIMERO.- Las personas trabajadoras tienen derecho a no estar conectadas a fin de garantizar, fuera del tiempo de trabajo legal o convencionalmente establecido, el respeto de su tiempo de descanso, permisos y vacaciones, así como de su intimidad personal y familiar. La regulación de este derecho se regirá por la negociación colectiva o, en su defecto, por lo acordado entre la empresa y los representantes de las personas trabajadoras.

SEGUNDO.- Con el fin de garantizar el cumplimiento de este derecho y regular sus posibles excepciones y previo acuerdo con los órganos de representación de las personas trabajadores, se han acordado los criterios y medidas que más adelante se relacionan.

I. La política de desconexión digital se aplicará a la totalidad de las personas trabajadoras de la empresa, estén o no incluidas en el Convenio Colectivo aplicable e independientemente de si realizan su función habitual presencialmente en cualquiera de los centros de trabajo de la empresa o mediante la modalidad de trabajo a distancia.
II. La empresa garantiza a todo el personal el derecho a la desconexión digital una vez finalizada la jornada laboral.
III. Las personas trabajadoras tendrán derecho a no responder a ninguna comunicación, fuere cual fuere el medio utilizado (correo electrónico, WhatsApp, teléfono, etc.), una vez finalizada su jornada laboral, salvo que concurran excepciones justificadas que supongan un grave o evidente perjuicio empresarial, cuya urgencia temporal necesite de una respuesta inmediata.
IV. En caso de enviar una comunicación que pueda suponer respuesta fuera del horario establecido al efecto, el remitente asumirá expresamente que la respuesta podrá esperar a la jornada laboral siguiente.
V. Con carácter general, no se realizarán llamadas, ni se enviarán mails o mensajes instantáneos entre las [Nº] horas y las [Nº] horas, de lunes a viernes, salvo casos de fuerza mayor o circunstancias excepcionales.
VI. En ningún caso se enviarán mails, mensajes instantáneos o se realizarán llamadas durante los fines de semanas, festivos ni periodos de vacaciones del personal, salvo excepciones por necesidades de negocio justificadas e ineludibles.
VII. Si alguna persona envía el correo fuera de las horas habituales de trabajo, deberá configurar el envío diferido del correo.
VIII. Serán aplicables, asimismo, las medidas anteriores, a las personas trabajadoras que realicen viajes de trabajo, tanto dentro como fuera del territorio nacional, debiéndose respetar la desconexión digital una vez finalizada la jornada de trabajo.
IX. En caso de distintos husos horarios, se tratarán de mantener las comunicaciones en los horarios de solape entre las distintas personas o en el momento más próximo posible a dicho solape.
X. Las personas trabajadoras se comprometen al uso adecuado de los medios informáticos y tecnológicos puestos a disposición por la empresa, evitando en la medida de lo posible su empleo fuera de la jornada estipulada.
XI. Los managers que tengan la responsabilidad de un equipo deberán ser referentes en la aplicación de esta política.
XII. La convocatoria y asistencia a reuniones de trabajo, presenciales o por videoconferencia, tanto a nivel interno como las que se lleven a cabo con clientes, se hará dentro de los límites de la jornada de trabajo, no pudiendo extenderse su duración más allá de la finalización de la jornada de trabajo.
XIII. No serán de aplicación las medidas que garantizan el derecho a la desconexión digital en los casos en que concurran circunstancias de causa de fuerza mayor o que supongan un grave, inminente o evidente perjuicio empresarial o del negocio, cuya urgencia requiera una respuesta inmediata. La acreditación de las circunstancias excepcionales se realizará mediante correo electrónico dirigido al trabajador al que se requiere fuera de su jornada laboral, indicando los motivos, las posibles consecuencias de las circunstancias y concretando desde qué momento se le requiere. Al término de la situación de excepción, el trabajador recibirá un correo electrónico en el que se le comunicará la finalización de las circunstancias y la reanudación de la jornada laboral ordinaria. Los tiempos que excedan de la jornada laboral como consecuencia de dichas circunstancias serán compensados, mediante días de libre disposición o abono de horas extraordinarias.

TERCERO.- La empresa implementará las medidas de sensibilización sobre las que se ampara el derecho a la desconexión digital. Para lo cual se informará y formará a las personas trabajadoras sobre la necesaria protección de este derecho, teniendo en cuenta las circunstancias, tanto laborales como personales de todas las personas trabajadoras.

CUARTO.- A los efectos de seguimiento y supervisión del cumplimiento de este acuerdo se constituye una comisión, que se reunirá [COMPLETAR] veces al año, formada por:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

QUINTO.- Este acuerdo entrará en vigor desde su firma.

En [LUGAR], a [FECHA].

Firmas: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
