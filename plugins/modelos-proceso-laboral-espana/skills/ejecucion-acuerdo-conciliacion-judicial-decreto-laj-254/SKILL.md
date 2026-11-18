---
name: ejecucion-acuerdo-conciliacion-judicial-decreto-laj-254
description: "Redacta el escrito «Ejecución del acuerdo de conciliación judicial (decreto del LAJ)» (formulario 254 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecución del acuerdo de conciliación judicial (decreto del LAJ)

> Formulario 0254 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Lo acordado ante el LAJ se ejecuta como sentencia (art. 84.5 LRJS); con firma digital de todas las partes, decreto en tres días (art. 84.1, LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (7 veces)
- [ ] IMPORTE (8 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ue la empresa demandada se comprometía a»; «…haberse aplazado la cantidad adeudada en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se conocen bienes o derechos de la ejecutada / Si se desconocen bienes o derechos — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 84.5 LRJS
- artículo 84.5 de la Ley 36/2011
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

### Formulario 0254 · Ejecución del acuerdo de conciliación judicial (decreto del LAJ)

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 18 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: Lo acordado ante el LAJ se ejecuta como sentencia (art. 84.5 LRJS); con firma digital de todas las partes, decreto en tres días (art. 84.1, LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA
Firmas

En el proceso ordinario regulado en la LRJS, el/la Letrado/a de la Administración de Justicia intentará la conciliación entre las partes, llevando a cabo la labor mediadora que le es propia, y advertirá a aquella de los derechos y obligaciones que pudieran corresponderles. Si las partes alcanzan la avenencia, dictará decreto aprobándola y acordando, además, el archivo de las actuaciones. Del mismo modo, corresponderá al Letrado/a la aprobación del acuerdo alcanzado por las partes antes del día señalado para los actos de conciliación y juicio, de haberse señalado conciliación anticipada, o en la misma fecha del juicio de tratarse de conciliación y juicio señalados sucesivamente.

La conciliación alcanzada ante el/la Letrado/a de la Administración de Justicia y los acuerdos logrados entre las partes aprobados por aquel tendrán, a todos los efectos legales, la consideración de conciliación judicial.

La conciliación y estos acuerdos entre partes, ratificados por el/la Letrado/a de la Administración de Justicia o, en su caso, por el/la Juez/a o Tribunal se llevarán a efecto por los trámites de la ejecución de sentencias, de acuerdo con el art. 84.5 LRJS.

Actualizado según las modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], actuando en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], según consta acreditado en los autos al margen referenciados, ante el Tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que de conformidad con lo dispuesto en el artículo 84.5 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, en relación con lo dispuesto en los artículos 237 y 239 del citado cuerpo legal, por medio del presente escrito, solicito la EJECUCIÓN FORZOSA del Decreto de fecha [FECHA] por el que se aprobó el acto de conciliación judicial de fecha [FECHA].

La presente ejecución tiene su base en los siguientes:

HECHOS

PRIMERO: Que en fecha [FECHA] se celebró acto de conciliación judicial ante el/la Letrado/a de la Admnistración de Justicia, que fue aprobado por Decreto de fecha [FECHA], por el que la empresa demandada se comprometía a [COMPLETAR].

SEGUNDO: Llegada la fecha del cumplimiento de la obligación asumida por la empresa (), esta no ha cumplido lo pactado en conciliación judicial, aún a pesar de haberse aplazado la cantidad adeudada en [COMPLETAR], y sin que se haya recibido por esta parte comunicación alguna que justifique tal incumplimiento.

TERCERO: Ante la actitud incumplidora de la empresa me veo en la obligación de solicitar la ejecución de lo acordado en la referida acta de conciliación judicial y Decreto aprobatorio de la misma por la cantidad total de [IMPORTE] € por los siguientes conceptos:

- [IMPORTE] Euros ( €) en concepto de principal.

- [IMPORTE] Euros ( €) en concepto de costas.

- [IMPORTE] Euros ( €) en concepto de intereses de demora.

Cantidades en concepto de intereses y costas que por el momento se estiman sin perjuicio de ulterior liquidación de conformidad con lo dispuesto en el art. 251 de la Ley reguladora de la jurisdicción Social.

En su virtud,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA

Que teniendo por presentado este escrito, junto con sus copias y documentos acompañatorios, se sirva admitirlo, por realizadas las manifestaciones en él contenidas y, en méritos del mismo, se tenga instada la EJECUCIÓN del acta de conciliación judicial de fecha [FECHA] y Decreto aprobatorio de la misma de fecha [FECHA], por la que se acuerde la ejecución por vía de apremio contra la ejecutada por la cantidad total de [IMPORTE] Euros ( €) de los que [IMPORTE] Euros ( €) son en concepto de principal, [IMPORTE] Euros ( €) en concepto de demora y [IMPORTE] Euros ( €) en concepto de costas de la ejecución; cantidades que por el momento se estiman sin perjuicio de ulterior liquidación.

Es de Justicia que pido en [LUGAR], a [FECHA].

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se conocen bienes o derechos de la ejecutada / Si se desconocen bienes o derechos — el texto de cada opción no venía en el formulario original]

Es justicia que reitero en el lugar y fecha indicados ut supra.

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
