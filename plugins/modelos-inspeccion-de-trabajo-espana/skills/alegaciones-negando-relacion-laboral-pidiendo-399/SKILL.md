---
name: alegaciones-negando-relacion-laboral-pidiendo-399
description: "Redacta el escrito «Alegaciones negando la relación laboral y pidiendo comunicación de oficio (art. 151 LJS)» (formulario 399 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alegaciones negando la relación laboral y pidiendo comunicación de oficio (art. 151 LJS)

> Formulario 0399 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Modelo sin base vigente: art. 19 RD 928/1998 derogado por la Ley 3/2023 (DDU.2) y el art. 148 LRJS ya no prevé el proceso de oficio para calificar la relación cuando se impugna el acta; la cita al art. 151 LRJS no corresponde. Replantear como alegaciones ordinarias (art. 17 RD 928/1998).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NÚMERO (2 veces)
- [ ] LOCALIDAD
- [ ] ÓRGANO
- [ ] Nº DE PROCEDIMIENTO
- [ ] AÑO
- [ ] FECHA (3 veces)
- [ ] se resuelve el alegato de hecho y de derecho en apartados o numerales distintos y separados con aportación documental o proposición de prueba en su caso
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…TAMENTO DE TRABAJO Y SEGURIDAD SOCIAL DE»; «…D»; «…l contenido del acta, lo cierto es que D»; «…, del que se deduce que el Sr»; «…número 2 y de las facturas giradas por D»; «… relación laboral entre esta empresa y D»; «…libre comunicación de oficio al Tribunal»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 151 de la LJS
- Real Decreto 772/2011

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

### Formulario 0399 · Alegaciones negando la relación laboral y pidiendo comunicación de oficio (art. 151 LJS)

- Año del modelo: 2012
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; 14 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Avisos de la revisión: Modelo sin base vigente: art. 19 RD 928/1998 derogado por la Ley 3/2023 (DDU.2) y el art. 148 LRJS ya no prevé el proceso de oficio para calificar la relación cuando se impugna el acta; la cita al art. 151 LRJS no corresponde. Replantear como alegaciones ordinarias (art. 17 RD 928/1998).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Encabezado
Dice
Alegaciones
Solicita
Firmas

AL DEPARTAMENTO DE TRABAJO Y SEGURIDAD SOCIAL DE [COMPLETAR]

D [COMPLETAR], mayor de edad, con D.N.I. nº [NÚMERO], y domicilio a efectos de notificaciones sito en [LOCALIDAD], y cuyas circunstancias personales constan en el expediente, ante [ÓRGANO] comparece y como mejor proceda,

DICE:

Que por medio del presente escrito, me persono en el trámite de audiencia y vista del Expediente nº [Nº DE PROCEDIMIENTO]/[AÑO], que se sigue ante este Órgano Administrativo y vengo a formular las siguientes

ALEGACIONES:

Que este administrado, habiendo sido notificado del acta de infracción de fecha [FECHA] y teniendo a la vista todo lo actuado, dentro del plazo legalmente establecido, debe manifestar que: [se resuelve el alegato de hecho y de derecho en apartados o numerales distintos y separados con aportación documental o proposición de prueba en su caso].

1) (antecedentes e impugnación) Las presentes actuaciones se iniciaron por acta de la Inspección de Trabajo de fecha [FECHA], número [NÚMERO], calificando la conducta de esta empresa como falta grave por

No obstante el contenido del acta, lo cierto es que D [COMPLETAR] no está ligado con relación laboral alguna con esta empresa, sino que es un trabajador autonómo que tiene un contrato civil con esta empresa para prestar determinados trabajos especializados de perforación de hormigón y regatas en las obras realizadas por esta empresa.

2) (alegaciones y prueba) La relación jurídica que liga a D con esta empresa es de naturaleza civil y así se desprende del contrato firmado por ambas partes de fecha [FECHA], del que se deduce que el Sr [COMPLETAR] realizaba los trabajos por cuenta propia y que se acompaña como documento número 1, del certificado de alta en el RETA del citado que se acompaña como documento número 2 y de las facturas giradas por D [COMPLETAR] a esta empresa, que llevan incluido el correspondiente IVA, que se acompañan como documentos número 3 a 30, de periodicidad irregular y de montante muy diferente cada una de ellas.

De todo ello se deduce claramente que no existe relación laboral entre esta empresa y D [COMPLETAR], y al efecto se impugna el acta de infracción por este motivo, interesando que se proceda a cursar la comunicación prevenida en el art. 151 de la LJS [NOTA DE REVISIÓN: El art. 151 LRJS regula la impugnación de actos administrativos, no esta comunicación. El art. 148 LRJS vigente (red. Ley 3/2023) solo prevé el proceso de oficio en los supuestos de sus letras a) a c), ninguno sobre la calificación de la relación laboral impugnada ante la autoridad laboral. Revisar la utilidad del modelo. Fuente: Ley 36/2011 (LRJS), BOE-A-2011-15936, arts. 148 y 151.] con suspensión de este procedimiento.

Por lo expuesto, y de conformidad con lo preceptuado en el Art. 19 del R.D. 928/1998, de 14 de mayo, en su redacción por Real Decreto 772/2011, de 3 de junio [NOTA DE REVISIÓN: Precepto derogado: la Ley 3/2023, de Empleo, derogó el art. 19 RD 928/1998 (disp. derogatoria única.2), desde el 2-3-2023. Fuente: Ley 3/2023, BOE-A-2023-5365, DDU.2; RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 19.], por el que se modifica el Reglamento General sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social, SOLICITA:

Que se tenga por evacuado el trámite preceptivo de audiencia, tomándose en consideración y admitiendo los documentos acompañados, lo anteriormente manifestado y solicitándose que se libre comunicación de oficio al Tribunal [COMPLETAR] para que califique la relación jurídica objeto de la actuación inspectora, acordando al tiempo suspensión del procedimiento sancionador.

En L. y F.

(Firma del interesado)

════════════════════════════════════════════════════════════════════════
