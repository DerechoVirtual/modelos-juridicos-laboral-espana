---
name: prorroga-excedencia-voluntaria-demanda-reconocimiento-176
description: "Redacta el escrito «Prórroga de excedencia voluntaria: demanda de reconocimiento» (formulario 176 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prórroga de excedencia voluntaria: demanda de reconocimiento

> Formulario 0176 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] NIF
- [ ] FECHA (8 veces)
- [ ] IMPORTE
- [ ] PLAZO
- [ ] Nº (5 veces)
- [ ] ÓRGANO
- [ ] LUGAR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…iones en el Despacho del/de la Letrado/a»; «… excedencia voluntaria contra la Empresa»; «…, incluido en el grupo profesional»; «…s y en el art. del Convenio Colectivo de»; «…omienzo del disfrute de la excedencia el»; «….- Que el art. del Convenio Colectivo de»; «…omunique a la empresa con un preaviso de»; «… excedencia voluntaria contra la Empresa»; «…erá ser citado en el domicilio social de»

## Elecciones que hay que hacer

- sin avenencia / sin efecto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

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

### Formulario 0176 · Prórroga de excedencia voluntaria: demanda de reconocimiento

- Año del modelo: 2020
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 31 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (DNI/NIE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
Firmas

La prórroga de la excedencia voluntaria vendrá regulada en el convenio colectivo

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], con D.N.I. núm. [DNI/NIE] y domicilio a efectos de notificaciones en el Despacho del/de la Letrado/a [COMPLETAR] sito en [LOCALIDAD], ante el Tribunal comparezco y, como mejor proceda en Derecho DIGO:

Que mediante el presente escrito vengo a interponer demanda de RECONOCIMIENTO DE DERECHO a la prórroga de excedencia voluntaria contra la Empresa [COMPLETAR], con domicilio social en [LOCALIDAD] y NIF [NIF], en la persona de su representante legal.

Se basa la presente demanda en los siguientes:

HECHOS

PRIMERO.- Que esta parte viene prestando sus servicios en la Empresa demandada desde el [FECHA], incluido en el grupo profesional [COMPLETAR], en el centro de trabajo sito en [LOCALIDAD] y percibiendo un salario bruto mensual de [IMPORTE] euros incluida la prorrata de pagas extraordinarias.

SEGUNDO.- Que con fecha [FECHA], solicité una excedencia voluntaria en virtud de lo establecido en el art. 46.2 del Estatuto de los trabajadores y en el art. del Convenio Colectivo de [COMPLETAR], por un periodo de [PLAZO].

La Empresa me contestó por carta de fecha [FECHA], siendo la fecha de efectos del comienzo del disfrute de la excedencia el [COMPLETAR].

Se acompañan las citadas comunicaciones como DOCS. Nº 1 y 2.

TERCERO.- Que con fecha [Nº], [Nº] días antes de la fecha de finalización de la excedencia, solicité por escrito a la Empresa una prórroga de la misma por un período de [Nº] meses, esto es, hasta el [FECHA], solicitud que me ha sido denegada por comunicación de la demandada de fecha [FECHA].

Se acompañan a esta demanda las cartas citadas como DOCS. Nº 3 y 4.

CUARTO.- Que el art. del Convenio Colectivo de [COMPLETAR], de aplicación, establece que la persona trabajadora tendrá derecho a una prórroga de la excedencia voluntaria que estuviese disfrutando, por una sola vez y por un período máximo de [Nº] meses, siempre y cuando se comunique a la empresa con un preaviso de [COMPLETAR].

Que cumpliendo todos los requisitos convencionalmente establecidos, y habiendo preavisado a la empresa con [Nº] días de antelación, entiendo que la empresa no puede negarme el derecho a disfrutar de la prórroga de la excedencia voluntaria solicitada.

QUINTO.-

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Que con fecha [FECHA] se celebró ante [ÓRGANO], el preceptivo acto de conciliación, de conformidad con los artículos 63 y siguientes de la Ley reguladora de la jurisdicción social, con el resultado de [ELEGIR: sin avenencia / sin efecto], según se acredita con la copia certificada del acta, que en la presente demanda se acompaña como DOC. Nº 3.

Se acompaña certificación del Servicio de Mediación, Arbitraje y Conciliación, justificativa de haber presentado la preceptiva demanda de conciliación y tener por concluido y cumplido el trámite legalmente establecido (DOC Nº 3).

En apoyo de la presente demanda se formularán en el acto del juicio oral los oportunos Fundamentos de Derecho

Por lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA que, teniendo por presentado este escrito con sus copias y documentos que se adjuntan, se digne admitirlo, tenga por formulada la presente demanda de reconocimiento de derecho a la prórroga de mi excedencia voluntaria contra la Empresa [COMPLETAR] y proceda a convocar a las partes para los actos de conciliación y, en su caso, juicio, en la debida forma, por el que, seguido de todos sus trámites legales oportunos, se dicte en su día sentencia estimando íntegramente la presente demanda y se declare el derecho del/de la demandante a prorrogar su excedencia voluntaria hasta el día [FECHA], condenando a la empresa demandada a estar y pasar por dicha declaración.

Por ser de justicia que se pide en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO, que acudiré al acto del juicio oral representado/a por Letrado/a.

SEGUNDO OTROSÍ DIGO: Que interesa al derecho de esta parte, y sin perjuicio de ampliación en su día, que se practiquen los siguientes MEDIOS DE PRUEBA:

- INTERROGATORIO del representante legal de la Empresa que deberá ser citado en el domicilio social de [COMPLETAR], para que bajo juramento indecisorio absuelva las posiciones que se le formularán en su momento, y con el apercibimiento de tenerlo por confesos en caso de incomparecencia.

SUPLICO AL TRIBUNAL DE INSTANCIA, admita y declare pertinentes las pruebas que se dejan propuestas, y acuerde cuanto sea preciso para llevarlas a efecto.

Por ser de Justicia que se reitera en el lugar y fecha «ut supra»

════════════════════════════════════════════════════════════════════════
