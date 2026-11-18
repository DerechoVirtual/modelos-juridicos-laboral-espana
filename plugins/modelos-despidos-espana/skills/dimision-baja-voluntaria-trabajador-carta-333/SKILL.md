---
name: dimision-baja-voluntaria-trabajador-carta-333
description: "Redacta el escrito «Dimisión o baja voluntaria del trabajador: carta» (formulario 333 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Dimisión o baja voluntaria del trabajador: carta

> Formulario 0333 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Dimisión: art. 49.1.d) ET (preaviso del convenio o la costumbre); la extinción por la trabajadora víctima de violencia de género o sexual está en el art. 49.1.m).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA
- [ ] Nº
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o a las víctimas de violencia sexual. En»; «…Muy Señores/as míos/as:»; «…, así como en la cláusula»

## Elecciones que hay que hacer

- violencia de género / violencia sexual

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- En caso de haber pactado en el contrato un plazo de preaviso diferente al establecido en el convenio colectivo…
- En el caso de ser víctima de violencia de género o violencia sexual…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 49.1.m) ET
- Ley Orgánica 2/2024

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

### Formulario 0333 · Dimisión o baja voluntaria del trabajador: carta

- Año del modelo: 2017
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos opcionales señalados; 7 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Dimisión: art. 49.1.d) ET (preaviso del convenio o la costumbre); la extinción por la trabajadora víctima de violencia de género o sexual está en el art. 49.1.m).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
Firmas

Comunicación de la persona trabajadora a la empresa de su voluntad de extinguir la relación laboral o contrato de trabajo.

No requiere ninguna formalidad ni explicación (solo si la persona trabajadora es víctima de violencia de género o violencia sexual), únicamente el respeto al preaviso que señalen los convenios colectivos.

A partir del 22 de agosto de 2024, la Ley Orgánica 2/2024, de 1 de agosto, de representación paritaria y presencia equilibrada de mujeres y hombres, modifica el art. 49.1.m) ET, ampliando el derecho de extinguir el contrato de trabajo de las víctimas de violencia de género a las víctimas de violencia sexual.

En [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

Muy Señores/as míos/as: [COMPLETAR]

Por medido de la presente les comunico mi decisión de extinguir la relación laboral que nos une con efectos a partir del día [FECHA], lo que pongo en su conocimiento con el preaviso de [Nº] días establecido en el art. del convenio colectivo de trabajo

[OPCIONAL — incluir si procede]

En caso de haber pactado en el contrato un plazo de preaviso diferente al establecido en el convenio colectivo

[NOMBRE Y APELLIDOS], así como en la cláusula [COMPLETAR] de mi contrato de trabajo.

[OPCIONAL — incluir si procede]

En el caso de ser víctima de violencia de género o violencia sexual

El motivo de esta decisión es que soy víctima de [ELEGIR: violencia de género / violencia sexual], por lo que me veo obligada a abandonar definitivamente mi puesto de trabajo. Acompaño a esta carta la documentación justificativa del correspondiente reconocimiento por la autoridad competente.

En consecuencia, les ruego que acusen recibo de esta comunicación y realicen los trámites oportunos con el fin de preparar la correspondiente liquidación de haberes y finiquito a la fecha de la extinción.

Sin otro particular les saluda atentamente,

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
