---
name: revision-contra-decretos-laj-recurso-188
description: "Redacta el escrito «Revisión contra decretos del LAJ: recurso» (formulario 188 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revisión contra decretos del LAJ: recurso

> Formulario 0188 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Art. 188 LRJS (red. RDL 6/2023): revisión contra el decreto que resuelve la reposición y directa contra los que ponen fin al procedimiento; plazo de tres o cinco días (art. 188.2).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO (2 veces)
- [ ] FECHA (6 veces)
- [ ] LUGAR
- [ ] Otros 13 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…AL TRIBUNAL»; «…ito al Ilustre Colegio de la Abogacía de»; «…, con número de colegiado/a»; «… del órgano al que me dirijo, por el que»; «…ón citando como infringido los artículos»; «…curso de reposición contra la resolución»; «…, por entender que»; «…sticia alegando como causa de inadmisión»; «…ión recurrida por entender el/la LAJ que»; «… citada resolución vulnera los artículos»; «…e perjuicio, por los motivos siguientes:»; «…días»; …

## Elecciones que hay que hacer

- 3 / 5

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 188.1 LRJS
- artículo 188 LRJS
- art. 188 de la Ley 36/2011
- art. 244 LRJS

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

### Formulario 0188 · Revisión contra decretos del LAJ: recurso

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 2 bloques de alternativas señalados; 26 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: Art. 188 LRJS (red. RDL 6/2023): revisión contra el decreto que resuelve la reposición y directa contra los que ponen fin al procedimiento; plazo de tres o cinco días (art. 188.2).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MOTIVOS
Firmas

En virtud del art. 188.1 LRJS, contra el decreto resolutivo de la reposición cabrá recurso de revisión. También cabrá recurso directo de revisión contra los decretos que pongan fin al procedimiento o impidan su continuación. Dichos recursos carecerán de efectos suspensivos sin que, en ningún caso, proceda actuar en sentido contrario a lo que se hubiese resuelto.

Cabrá interponer igualmente recurso directo de revisión contra los decretos en aquellos casos en que expresamente se prevea por la ley.

El recurso directo de revisión deberá interponerse en el plazo de tres o cinco días, según el carácter unipersonal o colegiado del órgano en el que se haya dictado la resolución recurrida, mediante escrito en el que deberá fundamentarse la infracción en que la resolución hubiera incurrido.

Actualizado conforme a la nueva redacción del artículo 188 LRJS dada por el apartado veinticinco del artículo 104 del R.D.-ley 6/2023, de 19 de diciembre, por el que se aprueban medidas urgentes para la ejecución del Plan de Recuperación, Transformación y Resiliencia en materia de servicio público de justicia, función pública, régimen local y mecenazgo.

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

AL TRIBUNAL [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a adscrito al Ilustre Colegio de la Abogacía de [COMPLETAR], con número de colegiado/a [COMPLETAR], actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS] según tengo referenciado en los autos n.º [NÚMERO] ante el Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que habiendo sido notificado a esta representación el Decreto de fecha [FECHA], dictado por el/la Letrado/a de la Administración de Justicia del órgano al que me dirijo, por el que [COMPLETAR], mediante el presente escrito, al amparo del art. 188 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LJS), interpongo recurso directo de revisión de la mencionada resolución citando como infringido los artículos [COMPLETAR] de la LJS en base a los siguientes

MOTIVOS

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Primero.- Que en fecha [FECHA], en el procedimiento de referencia, esta parte interpuso recurso de reposición contra la resolución [COMPLETAR], por entender que [COMPLETAR] que fue inadmitido a trámite por Decreto del/de la Letrado/a de Administración de Justicia alegando como causa de inadmisión [COMPLETAR].

Primero.- Que con fecha [FECHA] esta representación solicitó la suspensión, y correspondiente aplazamiento, de la ejecución nº [NÚMERO], en virtud de lo establecido en el art. 244 LRJS, que fue denegada por la resolución recurrida por entender el/la LAJ que [COMPLETAR].

Primero.- Que el decreto impugnado acuerda tener por desistida a esta parte del acto de conciliación señalado para el día [FECHA] a las [Nº] horas, al entender injustificada la incomparecencia de mi representado/a.

Se acompaña, a efectos probatorios, copia certificada del Decreto recurrido.

Segundo.- Que la citada resolución vulnera los artículos [COMPLETAR] y ha causado de forma injusta a mi representado/a un grave perjuicio, por los motivos siguientes: [COMPLETAR].

Tercero.- Que, por lo anterior, esta parte entiende que no concurren los motivos alegados por el/la Letrado/a de la Administración de Justicia para justificar su decisión. Fundamentamos nuestra posición en los siguientes motivos:

Por lo expuesto anteriormente, y dentro del plazo que nos confiere la Ley de [ELEGIR: 3 / 5] días [COMPLETAR].

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito, junto con la certificación del Decreto de referencia y demás documentos que se acompañan, se sirva admitirlo y, en su virtud, tenga por interpuesto RECURSO DIRECTO DE REVISIÓN contra el decreto dictado por el/la Letrado/a de la Administración de Justicia del órgano al que me dirijo de fecha [FECHA], y en consecuencia, lo revoque y tenga por admitido el recurso de reposición planteado, acuerde la suspensión de la ejecución solicitada, tenga por presentada a esta parte al acto de conciliación reanudándose el procedimiento [COMPLETAR]).

Es Justicia que pido en [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]

Firma

════════════════════════════════════════════════════════════════════════
