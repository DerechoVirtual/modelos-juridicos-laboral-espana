---
name: extinguir-contrato-modificacion-sustancial-condiciones-120
description: "Redacta el escrito «Extinguir el contrato por modificación sustancial de condiciones: demanda» (formulario 120 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Extinguir el contrato por modificación sustancial de condiciones: demanda

> Formulario 0120 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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

- Modificación sustancial: art. 41 ET sin cambios desde 2015 (rescisión con 20 días por año y máximo de nueve meses en las letras a, b, c, d y f; consultas de hasta 15 días; interlocutores del 41.4).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (3 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] NIF
- [ ] FECHA (7 veces)
- [ ] Nº
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a Jurisdicción Social, contra la empresa»; «…iguientes, HECHOS PRIMERO.- Trabajo para»; «…esde el [FECHA], en el centro de trabajo»; «…, mediante un contrato de carácter»; «…a tiempo»; «…tegoría profesional/grupo profesional de»; «…al aplicable es el Convenio Colectivo de»; «…ifica, por tanto, de forma sustancial mi»; «… vida familiar con la profesional ya que»; «…abajo con el cuidado de mis hijos ya que»; «…n de mi contrato de trabajo y, como DOC.»; «…e Mediación, Arbitraje y Conciliación de»; …

## Elecciones que hay que hacer

- El horario / Los turnos / Las funciones / El salario
- percibiendo / realizando
- del horario / de la jornada / de los turnos
- una carta / un burofax / un correo electrónico
- Dirección de la empresa / Dirección de Recursos Humanos
- horario / jornada / régimen de turnos / funciones / salario
- de sin avenencia / sin efecto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la persona trabajadora trabaja en horario partido o continuado / Si la persona trabajadora trabaja a turnos — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la empresa no ha constestado a la solicitud de la persona trabajadora / Si la empresa deniega la posibilidad de rescindir el contrato — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- INTERROGATORIO del representante legal de la empresa para que bajo juramento indecisorio absuelva las posicion…
- DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral los siguientes …
- DOCUMENTAL y TESTIFICAL, la que esta parte aportará al acto del juicio.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 41.3 del Estatuto de los Trabajadores
- art. 41.1 ET
- artículo 138 de la Ley 36/2011

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

### Formulario 0120 · Extinguir el contrato por modificación sustancial de condiciones: demanda

- Año del modelo: 2023
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 2 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 35 campos de relleno marcados en blanco
- Avisos de la revisión: Modificación sustancial: art. 41 ET sin cambios desde 2015 (rescisión con 20 días por año y máximo de nueve meses en las letras a, b, c, d y f; consultas de hasta 15 días; interlocutores del 41.4).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]
HECHOS

El artículo 41.3 del Estatuto de los Trabajadores reconoce a la persona trabajadora el derecho a rescindir su contrato de trabajo y percibir una indemnización de veinte días de salario por año de servicio, con un máximo de nueve meses, cuando, como consecuencia de una modificación sustancial de las condiciones de trabajo en las materias previstas en las letras a), b), c), d) y f) del art. 41.1 ET (jornada, horario, régimen de turnos, sistema de remuneración y cuantía salarial, y funciones que excedan de la movilidad funcional), resulte perjudicada por dicha modificación.

Para que prospere la demanda de extinción, deben concurrir los siguientes requisitos:

• Existencia de una modificación sustancial de las condiciones de trabajo en alguna de las materias legalmente previstas.

• Que dicha modificación cause un perjuicio real y relevante al trabajador.

• Que exista una relación de causalidad entre la modificación y el perjuicio alegado.

La demanda se presenta ante la jurisdicción social solicitando la extinción del contrato, alegando que la modificación sustancial de condiciones de trabajo resulta perjudicial y no se acepta. El procedimiento se tramita conforme a lo dispuesto en el artículo 138 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, que establece un proceso urgente y preferente,

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE], y con domicilio a efectos de notificación en el despacho del/la Letrado/a D./Dña. [NOMBRE Y APELLIDOS], Col. nº [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], sito en [LOCALIDAD], tel. y correo electrónico: ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito vengo a formular DEMANDA sobre EXTINCIÓN DE LA RELACIÓN LABORAL A INSTANCIA DEL TRABAJADOR derivada de la MODIFICACIÓN SUSTANCIAL DE SUS CONDICIONES DE TRABAJO, de conformidad con el artículo 138 de la Ley de la Jurisdicción Social, contra la empresa [COMPLETAR], con NIF nº [NIF] y domicilio en [LOCALIDAD], en la persona de su legal representante, en base a los siguientes,

HECHOS

PRIMERO.- Trabajo para [COMPLETAR] desde el [FECHA], en el centro de trabajo [COMPLETAR], mediante un contrato de carácter [COMPLETAR] a tiempo [COMPLETAR] y con la categoría profesional/grupo profesional de [COMPLETAR].

Mi jornada es de [Nº] horas de trabajo a la semana,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la persona trabajadora trabaja en horario partido o continuado / Si la persona trabajadora trabaja a turnos — el texto de cada opción no venía en el formulario original]

Mi salario es de [IMPORTE] euros brutos mensuales incluida la prorrata de pagas extraordinarias.

La norma convencional aplicable es el Convenio Colectivo de [COMPLETAR].

SEGUNDO.- Con fecha [FECHA] la empresa, mediante carta de esa misma fecha, me ha comunicado la modificación sustancial de mis condiciones de trabajo con efectos desde el día [FECHA].

La modificación consiste en que a partir de la citada fecha [FECHA]. Se modifica, por tanto, de forma sustancial mi [COMPLETAR].

La jornada [ELEGIR: El horario / Los turnos / Las funciones / El salario] que vengo [ELEGIR: percibiendo / realizando] hasta ahora me permite compaginar mi vida familiar con la profesional ya que [COMPLETAR].

Con la modificación impuesta por la empresa es imposible que compagine el trabajo con el cuidado de mis hijos ya que [COMPLETAR]. Por lo tanto, es un cambio absolutamente sustancial de mis condiciones laborales en cuanto al horario y la jornada que me causa un grave perjuicio.

Se acompaña como DOC. copia de la comunicación de modificación [ELEGIR: del horario / de la jornada / de los turnos].

TERCERO.- Ante los perjuicios que me causa esta modificación sustancial de mis condiciones laborales, con fecha [FECHA] envié [ELEGIR: una carta / un burofax / un correo electrónico] a la [ELEGIR: Dirección de la empresa / Dirección de Recursos Humanos] solicitando la extinción de mi contrato de trabajo,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la empresa no ha constestado a la solicitud de la persona trabajadora / Si la empresa deniega la posibilidad de rescindir el contrato — el texto de cada opción no venía en el formulario original]

Se acompaña como DOC. copia de la comunicación a la empresa solicitando la extinción de mi contrato de trabajo y, como DOC. [COMPLETAR], contestación de la empresa.

CUARTO.- Entiendo, por todo lo expuesto, que la modificación de mi [ELEGIR: horario / jornada / régimen de turnos / funciones / salario] es, sin lugar a dudas, sustancial y, causándome graves perjuicios, no tengo más remedio que optar por extinguir mi relación laboral en virtud de lo establecido en el art. 41.3 del Estatuto de los trabajadores.

QUINTO.- No ostento, ni he ostentado en el año anterior, cargo sindical alguno o de representación legal de los trabajadores.

SEXTO.- Con fecha [FECHA] se celebró el preceptivo acto de conciliación ante el Servicio de Mediación, Arbitraje y Conciliación de [COMPLETAR] con el resultado [ELEGIR: de sin avenencia / sin efecto].

Se acompaña copia del Acta de conciliación como DOC.

En apoyo de la presente demanda se formularán en el acto del juicio oral los oportunos FUNDAMENTOS DE DERECHO [COMPLETAR]

Por lo expuesto,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE], que teniendo por presentado este escrito con sus copias y documentos que lo acompañan, se sirva admitirlo y tenga por formulada DEMANDA sobre EXTINCIÓN DE LA RELACIÓN LABORAL A INSTANCIA DEL TRABAJADOR derivada de la MODIFICACIÓN SUSTANCIAL DE SUS CONDICIONES DE TRABAJO contra la empresa [COMPLETAR], señalando día y hora para la celebración del acto de conciliación o, en su caso, juicio, y en su día, previos los trámites procesales oportunos, dicte Sentencia por la que declare la extinción de mi relación laboral en virtud de lo establecido en el art. 41.3 del Estatuto de los trabajadores y condene a la demandada a abonarme la indemnización correspondiente a 20 días de salario por año de servicio, con lo demás que proceda en Derecho.

Por ser de justicia que se pide en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO, que acudiré al acto del juicio oral representado/a por Letrado/a.

SUPLICO AL TRIBUNAL que tenga por hecha la anterior manifestación.

SEGUNDO OTROSÍ DIGO, que interesa al derecho de esta parte que se practiquen en el acto del juicio oral los siguientes MEDIOS DE PRUEBA [COMPLETAR]:

[OPCIONAL — incluir si procede]

 INTERROGATORIO del representante legal de la empresa para que bajo juramento indecisorio absuelva las posiciones que se le formularán en su momento, y con el apercibimiento de tenerla por confesa en caso de incomparecencia, para lo que deberán ser citados en el domicilio indicado en el encabezamiento.

[OPCIONAL — incluir si procede]

 DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral los siguientes documentos:

[OPCIONAL — incluir si procede]

 DOCUMENTAL y TESTIFICAL, la que esta parte aportará al acto del juicio.

SUPLICO AL TRIBUNAL que tenga por propuesta la prueba, la admita y la declare pertinente y acuerde su práctica, así como las citaciones y requerimientos oportunos.

Es de Justicia que reitero en el lugar y fecha ut supra.

════════════════════════════════════════════════════════════════════════
