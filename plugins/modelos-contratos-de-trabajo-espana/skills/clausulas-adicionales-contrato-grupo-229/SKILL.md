---
name: clausulas-adicionales-contrato-grupo-229
description: "Redacta el escrito «Cláusulas adicionales del contrato de grupo» (formulario 229 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cláusulas adicionales del contrato de grupo

> Formulario 0229 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] IMPORTE
- [ ] Nº (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rte del grupo de las siguientes labores:»; «…uración del presente contrato será desde»; «…. Estableciéndose un horario concreto de»

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- (Descripción de las labores)…
- (Duración del contrato)…
- (Distribución de la retribución)…
- (Jornada)…
- (Vacaciones)…
- (Cambios en los componentes del grupo)…
- Cláusula de remisión…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 10.2 del ET

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

### Formulario 0229 · Cláusulas adicionales del contrato de grupo

- Año del modelo: 2019
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); 7 párrafos opcionales señalados; 6 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Al contrato de trabajo de grupo se pueden añadir cláusulas:

- Descripción de las labores.

- Duración del contrato.

- Distribución de la retribución.

- Jornada.

- Vacaciones.

- Cambios en los componentes del grupo.

[OPCIONAL — incluir si procede]

(Descripción de las labores)

Objeto del contrato

Que el objeto del presente contrato será la realización por parte del grupo de las siguientes labores: [COMPLETAR].

[OPCIONAL — incluir si procede]

(Duración del contrato)

Duración del contrato

Que la duración del presente contrato será desde [COMPLETAR] hasta la finalización efectiva de las labores señaladas.

[OPCIONAL — incluir si procede]

(Distribución de la retribución)

Distribución de la retribución

Como contraprestación a las labores desarrolladas por el grupo se pacta una retribución global de [IMPORTE] € brutos mensuales.

Dicha suma se entregará íntegramente al jefe del grupo al que autorizan de forma expresa para tal función el resto de sus compañeros, el cual repartirá dicha cuantía en función de los criterios que internamente el propio grupo haya acordado. Una vez que la empresa contratante haya otorgado la suma especificaa, previa firma del correspondiente recibo, al jefe del grupo, aquélla quedará totalmente libre de cualquier reclamación que en este sentido se pueda generar en el señalado colectivo.

[OPCIONAL — incluir si procede]

(Jornada)

Jornada

La jornada de trabajo será de [Nº] horas semanales. Estableciéndose un horario concreto de [COMPLETAR].

[OPCIONAL — incluir si procede]

(Vacaciones)

Vacaciones

El período de vacaciones individuales a disfrutar por el grupo tendrá una duración de [Nº] días naturales.

[OPCIONAL — incluir si procede]

(Cambios en los componentes del grupo)

Cambios en los componentes del grupo

Cualquier cambio, modificación o variación en los componentes del grupo deberá ser previamente notificado por su jefe a la representación de la empresa contratante, lo que deberá ser consentido expresamente por ésta. De no ser así, la empresa queda autorizada para resolver el contrato con el grupo en su integridad.

[OPCIONAL — incluir si procede]

Cláusula de remisión

En todo lo no previsto en el presente contrato se estará a lo dispuesto en la legislación laboral vigente y aplicable, y, más concretamente, en el art. 10.2 del ET y en el Convenio Colectivo Sectorial.

════════════════════════════════════════════════════════════════════════
