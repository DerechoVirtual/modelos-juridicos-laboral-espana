---
name: pedir-conciliacion-anticipada-ante-tribunal-17
description: "Redacta el escrito «Pedir la conciliación anticipada ante el tribunal» (formulario 17 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir la conciliación anticipada ante el tribunal

> Formulario 0017 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Conciliación anticipada (art. 82.2 y 82.3 LRJS, LO 1/2025): desde diez días tras la admisión y al menos treinta días antes del juicio; el acuerdo lo aprueba el LAJ por decreto, en tres días si viene firmado digitalmente (art. 84.1).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Demandante:»; «…Demandante: [COMPLETAR] Demandado/a:»; «… de admisión de la demanda planteada por»; «…a fecha del juicio oral previsto para el»

## Elecciones que hay que hacer

- según tengo acreditado en los autos de referencia / según se acredita mediante la escritura de poder/certificado de apoderamiento "apud acta" que a este escrito se acompaña
- llevan un tiempo negociando en aras a llegar a un acuerdo / van a llegar a un acuerdo

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 82.2 de la LRJS

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

### Formulario 0017 · Pedir la conciliación anticipada ante el tribunal

- Año del modelo: 2025
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 2 desplegables y casillas convertidos en elección en blanco; 16 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 notas de revisión repetidas retiradas
- Avisos de la revisión: Conciliación anticipada (art. 82.2 y 82.3 LRJS, LO 1/2025): desde diez días tras la admisión y al menos treinta días antes del juicio; el acuerdo lo aprueba el LAJ por decreto, en tres días si viene firmado digitalmente (art. 84.1).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
Firmas

La celebración de los actos de conciliación y juicio, el primero ante el/la Letrado/a de la Administración de Justicia y el segundo ante el/la juez/a, el/la magistrado/a podrá tener lugar en distinta convocatoria, debiendo hacerse a este efecto la citación en forma, con entrega a los demandados, a los interesados y, en su caso, al Ministerio Fiscal, de copia de la demanda y demás documentos; así como requiriendo de la Administración pública la remisión del expediente administrativo, cuando proceda, dentro de los diez días siguientes a la notificación.

El señalamiento del acto de conciliación en convocatoria separada y anticipada a la fecha del juicio podrá establecerse a instancia de cualquiera de las partes, si estimaran razonadamente que existe la posibilidad de llegar a un acuerdo conciliatorio, o de oficio por el/la Letrado/a de la Administración de Justicia si entendiera que, por la naturaleza y circunstancias del litigio o por la solución dada judicialmente en casos análogos, pudiera ser factible que las partes alcanzaran un acuerdo.

Procedimiento nº [Nº DE PROCEDIMIENTO]

Demandante: [COMPLETAR]

Demandado/a: [COMPLETAR]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], Colegiado/a nº [Nº DE COLEGIADO/A], en nombre y representación de [NOMBRE DEL REPRESENTADO/A], [ELEGIR: según tengo acreditado en los autos de referencia / según se acredita mediante la escritura de poder/certificado de apoderamiento "apud acta" que a este escrito se acompaña], y con domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], teléfono [TELÉFONO], y correo electrónico [CORREO ELECTRÓNICO], ante el Tribunal comparezco y como mejor proceda en Derecho, DIGO:

PRIMERO.- Que con fecha [FECHA] se ha notificado a mi representado/a Decreto de admisión de la demanda planteada por [COMPLETAR], señalando el día [FECHA], a las [Nº] horas, para la celebración de los actos de conciliación y, en su caso, juicio.

SEGUNDO.- Que ambas partes, demandante y demandada, [ELEGIR: llevan un tiempo negociando en aras a llegar a un acuerdo / van a llegar a un acuerdo] sobre el objeto del pleito, por lo que es muy posible que resuelvan sus diferencias sin necesidad de acudir juicio.

TERCERO.- Que, en virtud de lo establecido en el art. 82.2 de la LRJS [NOTA DE REVISIÓN: Cita correcta tras la LO 1/2025 (art. 82.2, párr. 2.º); el art. 82.3 fija que la conciliación anticipada se celebra desde los diez días de la admisión y al menos treinta días antes del juicio. Fuente: art. 82.2 y 82.3 LRJS (red. LO 1/2025); LRJS (Ley 36/2011), BOE-A-2011-15936.], y considerando que existe la posibilidad de llegar a un acuerdo, por medio del presente escrito vengo a solicitar el señalamiento del acto de conciliación en convocatoria separada y anticipada a la fecha del juicio.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito (con el documento que lo acompaña), lo admita y, en virtud de lo manifestado, señale el acto de conciliación en convocatoria separada y anticipada a la fecha del juicio oral previsto para el [COMPLETAR].

Por ser de Justicia que se pide en [LUGAR], a [FECHA].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
