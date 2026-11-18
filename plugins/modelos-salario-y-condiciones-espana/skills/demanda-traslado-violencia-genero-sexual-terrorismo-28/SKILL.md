---
name: demanda-traslado-violencia-genero-sexual-terrorismo-28
description: "Redacta el escrito «Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge» (formulario 28 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge

> Formulario 0028 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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

- Art. 40.4 ET (redacción LO 2/2024, vigente 22-8-2024): incluye a víctimas de violencia de género, sexual y de terrorismo, reserva de puesto de 6 a 12 meses y opción por la extinción con 20 días por año.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] CORREO ELECTRÓNICO
- [ ] NIF
- [ ] IMPORTE
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…caciones en el despacho del/la Letrado/a»; «…contra la empresa»; «…jo para la empresa demandada, dedicada a»; «…ya que a esta parte le consta que existe»; «…ía ocupar, en concreto en los puestos de»; «…to de la existencia de estos puestos por»; «… misma ofrecerme la ocupación del puesto»; «…contra la empresa»; «…entro de trabajo que la empresa tiene en»; «…-»

## Elecciones que hay que hacer

- MI PROTECCIÓN / MI DERECHO A LA ASISTENCIA SOCIAL INTEGRAL / MI DERECHO A LA PROTECCIÓN DE LA SALUD / MI DERECHO POR TRASLADO DE MI CÓNYUGE

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Seleccionar en caso de ser víctima de violencia de género, de violencia sexual o de terrorismo, o para hacer efectivo el derecho a la salud / Seleccionar en caso de traslado de mi cónyuge — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- - INTERROGATORIO del representante legal de la parte demandada para que bajo juramento indecisorio absuelva la…
- - DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral la siguiente …
- - [COMPLETAR].…
- - DOCUMENTAL y TESTIFICAL, la que se aporta con la demanda y la que se aportará en el acto del juicio oral.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 40.4 y 40.5 ET
- art. 40.3 ET

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

### Formulario 0028 · Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge

- Año del modelo: 2024
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 22 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: Art. 40.4 ET (redacción LO 2/2024, vigente 22-8-2024): incluye a víctimas de violencia de género, sexual y de terrorismo, reserva de puesto de 6 a 12 meses y opción por la extinción con 20 días por año.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
MEDIOS DE PRUEBA
Firmas

En el artículo 40.4 y 40.5 ET se establecen los supuestos de traslado de víctimas de violencia de género, de víctimas de violencia sexual y de víctimas del terrorismo y de trabajadores con discapacidad que acrediten la necesidad de recibir fuera de su localidad un tratamiento de habilitación o rehabilitación médico-funcional o atención, tratamiento u orientación psicológica relacionado con su discapacidad.

Asimismo, el art. 40.3 ET establece que, si por traslado uno de los cónyuges cambia de residencia, el otro, si fuera trabajador de la misma empresa, tendrá derecho al traslado a la misma localidad, si hubiera puesto de trabajo.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], y con domicilio a efectos de notificaciones en el despacho del/la Letrado/a [COMPLETAR], Col. nº [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], sito en [LOCALIDAD], tel. y correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo DEMANDA DE RECONOCIMIENTO DEL DERECHO AL TRASLADO DE CENTRO DE TRABAJO PARA PODER HACER EFECTIVA [ELEGIR: MI PROTECCIÓN / MI DERECHO A LA ASISTENCIA SOCIAL INTEGRAL / MI DERECHO A LA PROTECCIÓN DE LA SALUD / MI DERECHO POR TRASLADO DE MI CÓNYUGE] contra la empresa [COMPLETAR], con NIF [NIF], y domicilio en [LOCALIDAD], en la persona de su legal representante

Se basa esta demanda en los siguientes

HECHOS

PRIMERO.- Trabajo para la empresa demandada, dedicada a [COMPLETAR], con las siguientes condiciones laborales:

• Tipo de contrato:
• Antigüedad:
• Jornada:
• Grupo profesional:
• Centro de trabajo:
• Salario: [IMPORTE] euros brutos anuales
• Convenio colectivo de aplicación:
[ELEGIR UNA OPCIÓN Y REDACTARLA: Seleccionar en caso de ser víctima de violencia de género, de violencia sexual o de terrorismo, o para hacer efectivo el derecho a la salud / Seleccionar en caso de traslado de mi cónyuge — el texto de cada opción no venía en el formulario original]

CUARTO.- Con fecha [FECHA] la empresa me envió una carta en la que me comunicaba que no era posible mi traslado ya que no existen vacantes de mi grupo profesional en el centro de trabajo al que solicité mi traslado, lo cual no es cierto ya que a esta parte le consta que existe [COMPLETAR] vacante/s que podría ocupar, en concreto en los puestos de [COMPLETAR]. El actor ha tenido conocimiento de la existencia de estos puestos por [COMPLETAR].

Por lo tanto, no son ciertas las razones alegadas por la empresa, debiendo la misma ofrecerme la ocupación del puesto [COMPLETAR] de forma preferente a cualquier otro candidato.

Se acompaña como DOC nº 4 Copia de dicha carta.

En apoyo de la presente demanda se formularán en el acto del juicio oral los oportunos Fundamentos de Derecho.

Por lo expuesto,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA que teniendo por presentado este escrito con sus copias y documentos que lo acompañan, se sirva admitirlo y tenga por formulada DEMANDA DE RECONOCIMIENTO DEL DERECHO AL TRASLADO DE CENTRO DE TRABAJO PARA PODER HACER EFECTIVA [ELEGIR: MI PROTECCIÓN / MI DERECHO A LA ASISTENCIA SOCIAL INTEGRAL / MI DERECHO A LA PROTECCIÓN DE LA SALUD / MI DERECHO POR TRASLADO DE MI CÓNYUGE] contra la empresa [COMPLETAR], señalando día y hora para la celebración del acto de conciliación o, en su caso, juicio, y en su día, previos los trámites procesales oportunos, dicte Sentencia por la que se declare el derecho del actor a su traslado al centro de trabajo que la empresa tiene en [COMPLETAR] en un puesto de igual o similar categoría o grupo profesional al que ocupa actualmente.

Por ser de justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO, que acudiré al acto del juicio oral asistido/a de Letrado/a.

SEGUNDO OTROSÍ DIGO, que interesa al derecho de esta parte que se practiquen en el acto del juicio oral los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

- INTERROGATORIO del representante legal de la parte demandada para que bajo juramento indecisorio absuelva las posiciones que se le formularán en su momento, y con el apercibimiento de tenerlo por confeso en caso de incomparecencia, para lo que debe ser citado oportunamente en el domicilio de la empresa indicado en el encabezamiento.

[OPCIONAL — incluir si procede]

- DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral la siguiente documentación:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR].

[OPCIONAL — incluir si procede]

- DOCUMENTAL y TESTIFICAL, la que se aporta con la demanda y la que se aportará en el acto del juicio oral.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones, por propuesta la prueba, la admita y la declare pertinente y acuerde su práctica, así como las citaciones y requerimientos oportunos.

Es de Justicia que reitero en el lugar y fecha ut supra.

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
