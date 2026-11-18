---
name: pedir-actos-preparatorios-prueba-anticipada-373
description: "Redacta el escrito «Pedir actos preparatorios o prueba anticipada» (formulario 373 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir actos preparatorios o prueba anticipada

> Formulario 0373 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…pretende demandar a la entidad mercantil»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se solicita declaración/interrogatorio preparatoria/o / Si se solicita prueba testifical anticipada / Si se solicita examen de libros y cuentas / Si se solicita prueba anticipada — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se solicita declaración/interrogatorio preparatoria/o / Si se solicita prueba testifical anticipada / Si se solicita examen de libros y cuentas / Si se solicita prueba anticipada — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 76 y 77 de la LRJS
- art. 78 de la LRJS

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

### Formulario 0373 · Pedir actos preparatorios o prueba anticipada

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Los actos preparatorios en el proceso laboral tienen como finalidad permitir a quien pretenda demandar recabar información o documentación imprescindible para fundamentar adecuadamente la demanda o su oposición. Estos actos están regulados en los artículos 76 y 77 de la LRJS.

La anticipación de la prueba en el proceso laboral, que ser regula en el art. 78 de la LRJS consiste en la posibilidad de solicitar la práctica anticipada de algún medio de prueba antes del momento procesal generalmente previsto, cuando exista un temor fundado de que, por causa de las personas o del estado de las cosas, dichos actos no puedan realizarse en el momento oportuno o cuya realización presente graves dificultades. Esta figura permite asegurar la obtención de elementos probatorios esenciales para el proceso, evitando su posible pérdida o imposibilidad de práctica posterior.

Este formulario refunde los siguientes supuestos, que puede seleccionar individualmente:

- Solicitud de declaración preparatoria.

- Solicitud de prueba testifical anticipada.

- Solicitud de examen de libros y cuentas.

- Solicitud de práctica de prueba anticipada.

En caso de los actos preparatorios y dado que aún no se ha presentado la demanda, su presentación se hará en el Registro General. En caso de prueba anticipada se presentará ante la Plaza en la que se esté tramitando el procedimiento.

Procedimiento núm. [Nº DE PROCEDIMIENTO]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. En actos preparatorios previos a la demanda no hay plaza (se presenta en el registro). Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con NIF/NIE núm. [DNI/NIE], y domicilio en [LOCALIDAD], ante el Tribunal comparece y como mejor proceda en Derecho, DICE:

Que esta parte pretende demandar a la entidad mercantil [COMPLETAR]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se solicita declaración/interrogatorio preparatoria/o / Si se solicita prueba testifical anticipada / Si se solicita examen de libros y cuentas / Si se solicita prueba anticipada — el texto de cada opción no venía en el formulario original]

En su virtud,

SUPLICA AL TRIBUNAL DE INSTANCIA que, habiendo por presentado este escrito, con sus copias, lo admita, y conforme a lo dispuesto en el artículo

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se solicita declaración/interrogatorio preparatoria/o / Si se solicita prueba testifical anticipada / Si se solicita examen de libros y cuentas / Si se solicita prueba anticipada — el texto de cada opción no venía en el formulario original]

Todo ello por ser de justicia que respetuosamente se pide en [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
