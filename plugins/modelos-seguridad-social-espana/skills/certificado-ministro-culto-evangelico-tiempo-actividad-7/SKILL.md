---
name: certificado-ministro-culto-evangelico-tiempo-actividad-7
description: "Redacta el escrito «Certificado de ministro de culto evangélico y tiempo de actividad en España» (formulario 7 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Certificado de ministro de culto evangélico y tiempo de actividad en España

> Formulario 0007 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- RD 737/2026 (BOE-A-2026-19846) en vigor desde el 25-12-2026; la solicitud se presenta ante el INSS junto con la de la pensión o su revisión (art. 3).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a actividad en España certificado: desde»; «…hasta»; «…. Conforme (FEREDE) (1) Firmado:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto 737/2026

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

### Formulario 0007 · Certificado de ministro de culto evangélico y tiempo de actividad en España

- Año del modelo: 2026
- Revisión 17-11-2026: restos de formato retirados; notas del formulario agrupadas al final (1); 3 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: RD 737/2026 (BOE-A-2026-19846) en vigor desde el 25-12-2026; la solicitud se presenta ante el INSS junto con la de la pensión o su revisión (art. 3).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

La acreditación de la condición de ministro de culto y del tiempo de desempeño de su actividad en España se efectuará mediante la certificación expedida por la iglesia o federación de iglesias respectiva, debidamente inscrita en el Registro de Entidades Religiosas del Ministerio de la Presidencia, Justicia y Relaciones con las Cortes, en la que el ministro hubiera desempeñado su actividad, con la conformidad de la comisión permanente de FEREDE, según el modelo siguiente.

La inscripción de la entidad religiosa a la que perteneciera el ministro de culto en el Registro de Entidades Religiosas se comprobará por el Instituto Nacional de la Seguridad Social. En caso de obrar en poder del interesado la certificación de dicha inscripción podrá aportarse con la solicitud.

– Iglesia o federación de iglesias que certifica:

– Datos personales del ministro de culto que ejerció su actividad en la iglesia anterior o federación de iglesias:

• Nombre y apellidos:
• DNI/NIE:

– Periodo de ejercicio de la actividad en España certificado: desde [COMPLETAR] hasta [COMPLETAR]

Certificado expedido a efectos de acreditar la condición como ministro de culto de la Unión de Iglesias Cristianas Adventistas del Séptimo Día y el tiempo desempeñado en España con anterioridad al 1 de mayo de 1987, o, en su caso, la condición como ministro de culto de las iglesias pertenecientes a la Federación de Entidades Religiosas Evangélicas de España y el tiempo desempeñado en España con anterioridad al 1 de mayo de 1999, en virtud del Real Decreto 737/2026, de 23 de septiembre, sobre reconocimiento como cotizados a la Seguridad Social de los periodos de actividad ejercidos como ministros de culto de las iglesias pertenecientes a la Federación de Entidades Religiosas Evangélicas de España con anterioridad a su integración en el Régimen General de la Seguridad Social.

En [LUGAR], a [FECHA].

Conforme (FEREDE) (1)

Firmado: [COMPLETAR]

NOTAS DEL FORMULARIO

(1) Esta certificación incluye la conformidad de la comisión permanente de FEREDE.

════════════════════════════════════════════════════════════════════════
