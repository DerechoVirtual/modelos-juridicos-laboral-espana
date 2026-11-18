---
name: suplicacion-formalizacion-recurso-351
description: "Redacta el escrito «Suplicación: formalización del recurso» (formulario 351 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplicación: formalización del recurso

> Formulario 0351 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Formalización en diez días desde la puesta a disposición (art. 195.1 LRJS); impugnación en cinco días (art. 197.1); motivos del art. 193.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº (3 veces)
- [ ] LOCALIDAD (4 veces)
- [ ] COMUNIDAD AUTÓNOMA (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (3 veces)
- [ ] NÚMERO (2 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de»; «…en materia de»; «… Juez yerra al valorar la prueba, ya que»; «…equisito que igualmente se cumple ya que»; «…n recurrida, y en consecuencia condene a»; «…a»

## Elecciones que hay que hacer

- Letrado/a / Graduado/a social
- Ilustre Colegio de Abogados / Colegio de Graduados sociales
- NORMAS / GARANTÍAS DEL PROCEDIMIENTO
- ADICIONE / REVISE / MODIFIQUE
- DOCUMENTAL / PERICIAL

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Por no aportarse la prueba solicitada / Por no haber resuelto la sentencia sobre extremos fundamentales — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la modificación pretendida se basa en la prueba documental practicada / Si la modificación pretendida se basa en la prueba pericial practicada — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se pretende el examen de normativa aplicada en la sentencia / Si se pretende el examen de jurisprudencia aplicada en la sentencia — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 136 LRJS
- artículo 40 del ET
- artículo 41 del ET
- artículo 47 del ET
- artículo 139 LRJS
- artículo 24 de la Constitución
- artículo 24 CE
- artículo 191 de la Ley Reguladora de la Jurisdicción Social
- Ley Orgánica 1/2025
- Ley 36/2011

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

### Formulario 0351 · Suplicación: formalización del recurso

- Año del modelo: 2017
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 2 desplegables y casillas convertidos en elección en blanco; 4 desplegables convertidos en elección en blanco; 3 bloques de opciones sin texto dejados en blanco con sus rótulos; 20 campos de relleno marcados en blanco; 2 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 notas de revisión repetidas retiradas; 2 huecos del original que se habían perdido sin marca, marcados (Nº, Nº DE PROCEDIMIENTO)
- Avisos de la revisión: Formalización en diez días desde la puesta a disposición (art. 195.1 LRJS); impugnación en cinco días (art. 197.1); motivos del art. 193.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº] PARA ANTE LA SALA DE LO SOCIAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [LOCALIDAD]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
MOTIVOS DEL RECURSO
FUNDAMENTOS JURÍDICOS
Firmas

Son recurribles en suplicación las sentencias que dicten los Tribunales de Instancia en los procesos que ante ellos se tramiten, cualquiera que sea la naturaleza del asunto, salvo cuando la LRJS disponga lo contrario.

No procederá recurso de suplicación en los procesos relativos a las siguientes materias:

a) Impugnación de sanción por falta que no sea muy grave, así como por falta muy grave no confirmada judicialmente.

b) Procesos relativos a la fecha de disfrute de las vacaciones.

c) Materia electoral, salvo en el caso del artículo 136 LRJS.

d) Procesos de clasificación profesional, salvo en el caso previsto en el apartado 3 del artículo 137.

e) Procesos de movilidad geográfica distintos de los previstos en el apartado 2 del artículo 40 del ET,; en los de modificaciones sustanciales de condiciones de trabajo, salvo cuando tengan carácter colectivo de conformidad con el apartado 2 del artículo 41 del ET; en los de cambio de puesto o movilidad funcional, salvo cuando fuera posible acumular a estos otra acción susceptible de recurso de suplicación; y en las suspensiones y reducciones de jornada previstas en el artículo 47 del ET que afecten a un número de trabajadores inferior a los umbrales previstos en el apartado 1 del artículo 51.

f) Procedimientos relativos a los derechos de conciliación de la vida personal, familiar y laboral previstos en el artículo 139 LRJS, salvo cuando se haya acumulado pretensión de resarcimiento de daños y perjuicios que por su cuantía pudiera dar lugar a recurso de suplicación.

g) Reclamaciones cuya cuantía litigiosa no exceda de 3.000 euros. Tampoco procederá recurso en procesos de impugnación de alta médica cualquiera que sea la cuantía de las prestaciones de incapacidad temporal que viniere percibiendo el trabajador.

Si la resolución fuera recurrible en suplicación y la parte hubiera anunciado el recurso en tiempo y forma, el letrado de la Administración de Justicia tendrá por anunciado el recurso y acordará poner los autos a disposición del letrado o graduado social colegiado designado por la parte recurrente para que interponga el recurso, dentro de los diez días siguientes a que se notifique la puesta a disposición.

El recurso de suplicación tendrá por objeto:

a) Reponer los autos al estado en el que se encontraban en el momento de cometerse una infracción de normas o garantías del procedimiento que haya producido indefensión.

b) Revisar los hechos declarados probados, a la vista de las pruebas documentales y periciales practicadas.

c) Examinar las infracciones de normas sustantivas o de la jurisprudencia.

Actualizado según modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº] PARA ANTE LA SALA DE LO SOCIAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [COMUNIDAD AUTÓNOMA]

D./Dña. [NOMBRE Y APELLIDOS], [ELEGIR: Letrado/a / Graduado/a social] en ejercicio del [ELEGIR: Ilustre Colegio de Abogados / Colegio de Graduados sociales] de [COMPLETAR], en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en los autos núm. [Nº DE PROCEDIMIENTO] en materia de [COMPLETAR] que se siguen ante ese Tribunal, con domicilio profesional en [LOCALIDAD], ante el Tribunal comparezco y como mejor proceda en Derecho,

DIGO:

Que, en fecha [FECHA] me ha sido notificada diligencia de ordenación mediante la cual se tiene por anunciado el recurso de suplicación instado por esta parte contra la sentencia núm. dictada por esa Sección de lo Social del Tribunal de Instancia núm. [Nº] en fecha [FECHA], concediéndome el plazo legal para su formalización, por lo que, conforme a los artículos 190 y siguientes de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, mediante el presente escrito vengo a FORMALIZAR EL RECURSO DE SUPLICACIÓN, basándome para ello en los siguientes:

MOTIVOS DEL RECURSO

PRIMERO.- AL AMPARO DEL ARTÍCULO 193 A) DE LA LEY 36/2011, DE 10 DE OCTUBRE, REGULADORA DE LA JURISDICCIÓN SOCIAL, PARA QUE POR LA SALA SE REPONGAN LOS AUTOS AL ESTADO EN EL QUE SE ENCONTRABAN EN EL MOMENTO DE COMETERSE UNA INFRACCIÓN DE [ELEGIR: NORMAS / GARANTÍAS DEL PROCEDIMIENTO], CONCRETAMENTE DEL ARTÍCULODE, QUE HA PRODUCIDO INDEFENSIÓN

Con este motivo, se pretende eliminar todos los posibles vicios del procedimiento operados por infracciones de las garantías mínimas del proceso laboral que han generado manifiesta indefensión. Y, en ese sentido, las normas procesales que se alegan infringidas tienen carácter esencial y debe haberse formulado en tiempo y forma la oportuna protesta, pidiendo la subsanación de la infracción.

Este motivo tiene por finalidad asegurar los principios que deben presidir la actividad procesal, o sea, los principios de igualdad de las partes, de audiencia, de contradicción y de proscripción de la indefensión, por lo que -como viene reiterando la doctrina judicial- para que sea estimado es preciso que:

- En las actuaciones de instancia se haya infringido una norma procesal o una de las garantías procesales explícitas en la Constitución, sobre todo en el artículo 24 de la Constitución Española.
- Se cite de modo concreto por el/la recurrente la norma o garantía cuya infracción se denuncia, en este supuesto (hay que reflejar expresamente la norma o garantía del procedimiento infringida).
- El defecto procesal debe ser invocado precisamente por la parte que, sin haberlo provocado, haya resultado perjudicada por el mismo.
[ELEGIR UNA OPCIÓN Y REDACTARLA: Por no aportarse la prueba solicitada / Por no haber resuelto la sentencia sobre extremos fundamentales — el texto de cada opción no venía en el formulario original]

Lo que es esencial para considerar que el procedimiento se ha realizado con todas las garantías.

La infracción ha de ser de tal índole que haya producido indefensión. La indefensión consiste en un impedimento del derecho a alegar y demostrar en el proceso los propios derechos y, en su manifestación más trascendente, es la situación en la que se impide a una parte, por el órgano judicial, en el curso del proceso, el ejercicio del derecho de defensa, privándola de ejercitar su potestad de alegar y, en su caso, justificar sus derechos e intereses para que le sean reconocidos, o para replicar dialécticamente las posiciones contrarias en el ejercicio del indispensable principio de contradicción (STC 89/1986, 1 jul). La indefensión ha de ser material, no meramente formal, que suponga una vulneración del artículo 24 CE (STC 124/1994, 25 abr) que trascienda al fallo de la sentencia.

Conforme a doctrina jurisprudencial reiterada, este motivo tiene carácter excepcional, al ser también excepcional la medida que resulta del mismo de declaración de nulidad de las actuaciones practicadas desde el momento en que aquella infracción se produjo.

SEGUNDO.- AL AMPARO DEL ARTÍCULO 193 B) DE LA MISMA LEY PROCEDIMENTAL, PARA QUE POR LA SALA SE [ELEGIR: ADICIONE / REVISE / MODIFIQUE] EL HECHO DECLARADO PROBADO, A LA VISTA DE LA PRUEBA [ELEGIR: DOCUMENTAL / PERICIAL] PRACTICADA.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la modificación pretendida se basa en la prueba documental practicada / Si la modificación pretendida se basa en la prueba pericial practicada — el texto de cada opción no venía en el formulario original]

B) Error manifiesto del juzgador: la Juez yerra al valorar la prueba, ya que [COMPLETAR].

C) Los hechos que se pretenden modificar han de ser transcendentes a los efectos del fallo. Requisito que igualmente se cumple ya que [COMPLETAR].

TERCERO.- AL AMPARO DEL ARTÍCULO 193 C) DE LA MISMA LEY REGULADORA DE LA JURISDICCIÓN SOCIAL ANTES CITADA, PARA QUE POR LA SALA SE EXAMINE LA INFRACCION DE NORMAS SUSTANTIVAS O DE LA JURISPRUDENCIA DE LA SENTENCIA, POR INFRACCIÓN DE.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se pretende el examen de normativa aplicada en la sentencia / Si se pretende el examen de jurisprudencia aplicada en la sentencia — el texto de cada opción no venía en el formulario original]

FUNDAMENTOS JURÍDICOS

I. La Sentencia dictada en la instancia es susceptible de Recurso de Suplicación por disponerlo así el artículo 191 de la Ley Reguladora de la Jurisdicción Social (L.R.J.S)

II. El/La Letrado/a que suscribe y firma este escrito presenta ante la Sección de lo Social del Tribunal de Instancia nº [NÚMERO] de [LOCALIDAD] este escrito de formalización del Recurso de Suplicación que ya venía anunciado, dentro del término de diez días, conforme lo dispone el artículo 195 de la L.R.J.S.

III. Se ampara el Recurso de Suplicación en el apartado a), b) y c) del artículo 193 de la invocada Ley Reguladora de la Jurisdicción Social.

IV. Se formaliza el Recurso por Letrado designado que firma este escrito.

Por todo ello,

SUPLICO AL TRIBUNAL DE INSTANCIA que teniendo por presentado este escrito con sus copias en tiempo y forma, se sirva admitirlo, tenga por formalizado recurso de suplicación contra la sentencia dictada por ese Tribunal de Instancia en el procedimiento de autos núm. [NÚMERO], sobre [DESCRIBIR] a instancia de mi representado/a y, seguidos los trámites legales oportunos, eleve las actuaciones a la Sala de lo Social del Tribunal Superior de Justicia de [LOCALIDAD].

SUPLICO A LA SALA DE LO SOCIAL DEL TRIBUNAL SUPERIOR DE JUSTICIA DE [COMUNIDAD AUTÓNOMA] que, recibidas las actuaciones del Tribunal de Instancia antedicho y a la vista del presente recurso de suplicación, dicte en su día sentencia por la que, estimando el presente recurso, proceda a la revocación de la resolución recurrida, y en consecuencia condene a [COMPLETAR] a [COMPLETAR], y determine la devolución del depósito y consignación efectuado en su día por este recurrente, con lo demás que proceda en Derecho.

Todo ello según es de Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: Que, en cumplimiento de lo establecido en el artículo 198 de la Ley reguladora de la jurisdicción social, designo como domicilio en la sede de la Sala de lo Social de ese Tribunal, a efectos de notificaciones, el del despacho profesional del [ELEGIR: Letrado/a / Graduado/a social] que suscribe, que consta al inicio del presente escrito.

Por lo que,

SUPLICO A LA SALA que tenga por hecha la anterior manifestación a los efectos indicados, según consta en el mismo lugar y fecha.

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
