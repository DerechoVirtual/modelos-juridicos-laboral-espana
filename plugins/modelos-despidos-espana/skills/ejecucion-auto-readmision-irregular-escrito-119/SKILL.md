---
name: ejecucion-auto-readmision-irregular-escrito-119
description: "Redacta el escrito «Ejecución del auto de readmisión irregular: escrito» (formulario 119 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecución del auto de readmisión irregular: escrito

> Formulario 0119 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE COLEGIADO/A
- [ ] COLEGIO
- [ ] LOCALIDAD
- [ ] FECHA (6 veces)
- [ ] Nº DE RESOLUCIÓN
- [ ] IMPORTE (8 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tel. y correo electrónico:»; «…laboral del/la demandante y se condena a»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

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

### Formulario 0119 · Ejecución del auto de readmisión irregular: escrito

- Año del modelo: 2023
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 23 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 notas de revisión repetidas retiradas; 2 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
Firmas

El incidente se inicia cuando el trabajador solicita la ejecución del fallo; y se resuelve por Auto del Juez, quien, tras la comparecencia de las partes y la práctica de las pruebas pertinentes, decidirá si estima no producida la readmisión o producida de modo irregular.

Procedimiento nº [Nº DE PROCEDIMIENTO]

Ejecución nº [Nº DE PROCEDIMIENTO]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a colegiado/a nº [Nº DE COLEGIADO/A] del Ilustre Colegio de Abogados de [COLEGIO], en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], tal como consta acreditado en el procedimiento de referencia, y con domicilio a efectos de notificaciones en su despacho sito en [LOCALIDAD] tel. y correo electrónico: [COMPLETAR], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

PRIMERO.- Que con fecha [FECHA] se dictó la Sentencia nº [Nº DE RESOLUCIÓN] en el procedimiento de referencia, por la que estimando la demanda presentada por mi mandante frente a la empresa y el Fondo de Garantía Salarial, se declaró improcedente el despido del/la actor/a de fecha [FECHA] y se condenó a la empresa a readmitirle en su puesto de trabajo en las mismas condiciones que tenía antes de producirse el despido, a no ser que en el plazo de cinco días optase por el abono de indemnización correspondiente.

SEGUNDO.- Que no habiendo optado la empresa por la indemnización ha tenido lugar incidente de no readmisión que se ha resuelto por Auto de fecha [FECHA], por el que se declara extinguida la relación laboral del/la demandante y se condena a [COMPLETAR] a que le abone la cantidad de [IMPORTE] euros en concepto de indemnización y la cantidad de [IMPORTE] euros en concepto de salarios de tramitación.

TERCERO.- Que no habiendo abonado la empresa cantidad alguna al/la actor/a, por medio del presente escrito se insta la EJECUCIÓN del Auto de fecha [FECHA], para que por el tribunal se proceda al embargo de bienes propiedad de la demandada suficientes para cubrir el principal adeudado de [IMPORTE] euros en concepto de indemnización y [IMPORTE] euros en concepto de salarios de tramitación, más [IMPORTE] euros en concepto de intereses y costas, que se calculan por ahora, y sin perjuicio de su liquidación definitiva. Todo ello de conformidad con los arts. 237 y siguientes de la LRJS.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito, se sirva admitirlo y tras los trámites legales oportunos, tenga por instada la ejecución del Auto de fecha [FECHA] procediéndose por este Tribunal al embargo de bienes propiedad de la demandada suficientes para cubrir el principal adeudado de [IMPORTE] euros en concepto de indemnización y [IMPORTE] euros en concepto de salarios de tramitación, más [IMPORTE] euros en concepto de intereses y costas, que se calculan por ahora, y sin perjuicio de su liquidación definitiva.

Por ser de Justicia que se pide en [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
