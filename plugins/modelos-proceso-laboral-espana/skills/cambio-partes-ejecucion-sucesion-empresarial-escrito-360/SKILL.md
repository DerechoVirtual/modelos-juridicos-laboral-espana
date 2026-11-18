---
name: cambio-partes-ejecucion-sucesion-empresarial-escrito-360
description: "Redacta el escrito «Cambio de partes en la ejecución por sucesión empresarial: escrito» (formulario 360 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cambio de partes en la ejecución por sucesión empresarial: escrito

> Formulario 0360 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] NÚMERO
- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] NIF
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…n empresarial (art. 240 LRJS) Ejecución:»; «…Procedimiento:»; «… a mi representada, la entidad mercantil»; «… mi representada de la entidad mercantil»; «… se acuerde tener a la entidad mercantil»

## Elecciones que hay que hacer

- ejecutante / ejecutada

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 240 LRJS
- artículo 240 de la LRJS
- artículo 44 del Estatuto de los Trabajadores

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

### Formulario 0360 · Cambio de partes en la ejecución por sucesión empresarial: escrito

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 13 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Solicitud de modificación o cambio de partes en la ejecución por sucesión empresarial (art. 240 LRJS)

Ejecución: [COMPLETAR]

Procedimiento: [COMPLETAR]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a en ejercicio del Iltre. Colegio de Abogados de [COLEGIO] (Col. nº [NÚMERO]), con despacho profesional sito en [LOCALIDAD], en nombre y representación de [NOMBRE DEL REPRESENTADO/A], entidad mercantil con domicilio sito en [LOCALIDAD], provista de NIF nº [NIF], según acredito con la copia del poder general para pleitos que acompaño al presente escrito como DOC. Nº 1, ante el tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que de conformidad con lo dispuesto en el artículo 240 de la LRJS, mediante el presente escrito se solicita que se tenga a mi representada, la entidad mercantil [COMPLETAR], como parte [ELEGIR: ejecutante / ejecutada] en este procedimiento de conformidad con las siguientes:

ALEGACIONES

PRIMERA.- Con fecha [FECHA] se produjo una sucesión empresarial como consecuencia de la compra por mi representada de la entidad mercantil [COMPLETAR] ( [ELEGIR: ejecutante / ejecutada] en este procedimiento). A tenor de la fecha anteriormente expuesta, la sucesión empresarial se produjo, en consecuencia, con posterioridad a que se dictase la sentencia cuyo cumplimiento se insta en este procedimiento ejecutivo.

Se acredita este extremo con la copia de escritura pública de compraventa que se adjunta como DOC. Nº 2.

SEGUNDA.- De conformidad con lo dispuesto en el artículo 44 del Estatuto de los Trabajadores la entidad a la que represento debe considerarse subrogada en todos los derechos y obligaciones laborales y de Seguridad Social, por lo que, resultando directamente afectada por lo se dirima en este procedimiento, mediante el presente escrito se solicita que se nos tenga como parte [ELEGIR: ejecutante / ejecutada] en el mismo.

En su virtud,

SUPLICO AL TRIBUNAL Que teniendo por presentado este escrito en tiempo y forma, se sirva admitirlo, por realizadas las manifestaciones en él contenidas y, en méritos del mismo, se acuerde tener a la entidad mercantil [COMPLETAR] como parte [ELEGIR: ejecutante / ejecutada] en este procedimiento.

Es de Justicia que pido en [LUGAR], a [FECHA].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
