---
name: caducidad-actuaciones-previas-itss-declaracion-396
description: "Redacta el escrito «Caducidad de las actuaciones previas de la ITSS: declaración» (formulario 396 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Caducidad de las actuaciones previas de la ITSS: declaración

> Formulario 0396 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Base legal vigente: art. 21.4 Ley 23/2015 (además del art. 8.2 RD 928/1998).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…as actuaciones practicadas en la empresa»; «…previas al procedimiento sancionador por»; «…scurso de dichas actuaciones inspectoras»; «…e cinco meses. Por cuanto antecede EL/LA»; «… de comprobación iniciadas en la empresa»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 121 y 122 de la Ley 39/2015
- Real Decreto 928/1998

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

### Formulario 0396 · Caducidad de las actuaciones previas de la ITSS: declaración

- Año del modelo: 2015
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 7 campos de relleno marcados en blanco
- Avisos de la revisión: Base legal vigente: art. 21.4 Ley 23/2015 (además del art. 8.2 RD 928/1998).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Antecedentes de Hecho
Fundamentos de Derecho
Resolución
Firmas

Vistas las actuaciones practicadas en la empresa [COMPLETAR] y teniendo en cuenta los siguientes

ANTECEDENTES DE HECHO

Con fecha [FECHA] se han iniciado actuaciones previas inspectoras previas al procedimiento sancionador por [COMPLETAR]

Durante el transcurso de dichas actuaciones inspectoras [COMPLETAR]

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- El art. 8.2 del Reglamento General [NOTA DE REVISIÓN: Citar también el art. 21.4 Ley 23/2015 (norma legal vigente): además del texto del art. 8.2 RD 928/1998, excluye del límite de 5 meses la pendencia de un pronunciamiento judicial y fija el inicio del cómputo. Fuente: Ley 23/2015, BOE-A-2015-8168, art. 21.4; RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 8.2.] sobre procedimientos para la imposición de sanciones por infracciones al orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social, aprobado por Real Decreto 928/1998 de 14 de mayo, al regular el objeto de la actividad inspectora previa dispone que: “Tales actuaciones comprobatorias no se dilatarán por espacio de más de nueve meses salvo que la dilación sea imputable al sujeto a inspección o a las personas dependientes del mismo… Asimismo, no se podrán interrumpir por más de cinco meses, salvo que la interrupción sea causada por el sujeto inspeccionado o personas de él dependientes…”.

SEGUNDO.- El incumplimiento de dichos plazos, de acuerdo con lo dispuesto en dicho artículo 8.2, no interrumpirá el cómputo de la prescripción y decaerá la posibilidad de extender acta de infracción o de liquidación, como consecuencia de tales actuaciones previas.

Ello no obstante, en los supuestos anteriormente citados, y siempre que no lo impida la prescripción, la Inspección de Trabajo y Seguridad Social podrá promover nuevas actuaciones de comprobación referentes a los mismos hechos y extender, en su caso, las actas correspondientes. Las comprobaciones efectuadas en las actuaciones inspectoras previas caducadas, tendrán el carácter de antecedente para las sucesivas, haciendo constar formalmente tal incidencia.

TERCERO.- De acuerdo con el relato de hechos expuesto en esta resolución, las actuaciones comprobatorias se han dilatado por espacio superior a nueve meses/interrumpido por más de cinco meses.

Por cuanto antecede

EL/LA [COMPLETAR] RESUELVE:

Declarar la caducidad de las actuaciones previas de comprobación iniciadas en la empresa [COMPLETAR]

Contra esta resolución puede interponerse recurso de alzada ante el/la Director/a del Organismo Estatal Inspección de Trabajo y Seguridad Social en el plazo de un mes a partir de su notificación, de acuerdo con lo establecido en los arts. 121 y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas.

En [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
