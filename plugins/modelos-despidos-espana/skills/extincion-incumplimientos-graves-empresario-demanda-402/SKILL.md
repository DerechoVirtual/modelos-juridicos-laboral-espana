---
name: extincion-incumplimientos-graves-empresario-demanda-402
description: "Redacta el escrito «Extinción por incumplimientos graves del empresario: demanda del trabajador» (formulario 402 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Extinción por incumplimientos graves del empresario: demanda del trabajador

> Formulario 0402 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Extinción por voluntad del trabajador: el art. 50 ET fue redactado de nuevo por la LO 1/2025 (DF 26.ª, en vigor el 3-4-2025); indemnización de despido improcedente (33 días por año, máximo 24 mensualidades, art. 56.1 ET sin cambios).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] DNI/NIE
- [ ] CALLE (3 veces)
- [ ] FECHA
- [ ] IMPORTE (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, domiciliado en»; «…de contrato de trabajo contra la empresa»; «…, de»; «…, ocupando la categoría profesional de»; «… despido improcedente, contra la empresa»; «…ficaciones el del despacho del Letrado D»; «…el juicio los recibos de salario del año»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 50.1.c) del Estatuto de los Trabajadores
- artículos 1 y 2 de la Ley 36/2011
- artículos 50.2 y 56.1 del RDLeg. 2/2015
- artículo 90.2 de la LRJS

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

### Formulario 0402 · Extinción por incumplimientos graves del empresario: demanda del trabajador

- Año del modelo: 2015
- Revisión 17-11-2026: 17 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Extinción por voluntad del trabajador: el art. 50 ET fue redactado de nuevo por la LO 1/2025 (DF 26.ª, en vigor el 3-4-2025); indemnización de despido improcedente (33 días por año, máximo 24 mensualidades, art. 56.1 ET sin cambios).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Social del Tribunal de Instancia de [SEDE]

D. [NOMBRE Y APELLIDOS], mayor de edad, con DNI n.º [DNI/NIE], domiciliado en [COMPLETAR], calle [CALLE], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, digo:

Que por medio de este escrito formulo demanda de extinción de contrato de trabajo contra la empresa [COMPLETAR] en la persona de su representante legal, con domicilio en calle [CALLE], de [COMPLETAR], fundamentada en los siguientes

HECHOS

Presto servicios para la empresa demandada desde el día [FECHA], ocupando la categoría profesional de [COMPLETAR] y percibiendo un salario anual de [IMPORTE] euros, lo que supone, incluida la prorrata de gratificaciones extraordinarias, un salario diario de [IMPORTE] euros.

Por parte de la empresa demandada, sin justa causa, se ha procedido a incumplir sus obligaciones legales y convencionales en los términos siguientes: (Deberá concretar qué obligaciones legales o convencionales está incumpliendo la empresa. Por ejemplo: la falta de ocupación efectiva, el incumplimiento del abono del complemento de incapacidad temporal establecido convencionalmente, etc.).

Todo ello supone un incumplimiento grave de las obligaciones legales y convencionales por parte del empresario en los términos previstos en el artículo 50.1.c) del Estatuto de los Trabajadores.

Acompaño certificación de haber intentado la conciliación previa ante el organismo administrativo correspondiente.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

Los artículos 1 y 2 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social, en orden a la competencia y procedimiento.

Los artículos 50.1.c), y 49.1.j), del RDLeg. 2/2015, de 23 de octubre, por el que se aprueba el Estatuto de los Trabajadores, que prevén como justas causas de extinción del contrato de trabajo las que se fundamenten en incumplimientos contractuales graves del empresario.

Los artículos 50.2 y 56.1 del RDLeg. 2/2015, de 23 de octubre, por el que se aprueba el Estatuto de los Trabajadores en orden a las indemnizaciones a que el trabajador tiene derecho en tales supuestos.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, habiendo por presentado este escrito, se digne admitirlo, teniendo por formulada demanda en reclamación de extinción de contrato de trabajo por incumplimiento contractual de la empresa, con derecho a indemnización como si se tratase de un despido improcedente, contra la empresa [COMPLETAR], en la persona de su representación legal, y previos los trámites oportunos señale día y hora para la celebración de la conciliación previa, o juicio en caso de no avenencia, para que en definitiva se dicte sentencia declarando extinguido mi contrato de trabajo con la empresa demandada por incumplimientos graves por parte del empresario, condenando a ésta al pago de la correspondiente indemnización como si se tratara de despido improcedente y a estar y pasar por tal declaración.

PRIMER OTROSÍ DIGO: Que asistiré al acto del juicio oral acompañado de Letrado o representado por Graduado Social Colegiado, y señalo como domicilio a efectos de citaciones y notificaciones el del despacho del Letrado D [COMPLETAR], en calle [CALLE] de esta ciudad.

SEGUNDO OTROSÍ: Que para el acto de la vista, y sin perjuicio de ampliación, intereso la práctica de los siguientes medios de PRUEBA:

– INTERROGATORIO del empresario demandado, quien deberá ser citado en legal forma para contestar a las preguntas que se le formulen, con las advertencias previstas en el artículo 90.2 de la LRJS

– DOCUMENTAL.-Para que la empresa aporte al acto del juicio los recibos de salario del año [COMPLETAR]

– INTERROGATORIO DE TESTIGOS.-Solicito que sean citados los siguientes testigos para que contesten a las preguntas que se formularán en el acto del juicio:

D. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD] y

D. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD]

SUPLICO AL TRIBUNAL tenga por propuesta la prueba que se articula, y previa declaración de pertinencia, ordene lo conducente para su práctica.

Por ser de justicia, que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma

Normativa aplicable

– Ley reguladora de la Jurisdicción Social: artículos 1, 2, 80, 90, 91, 92 y 94.

– Estatuto de los Trabajadores: artículos 49.1.j) y 50.1.c).

================================================================================
