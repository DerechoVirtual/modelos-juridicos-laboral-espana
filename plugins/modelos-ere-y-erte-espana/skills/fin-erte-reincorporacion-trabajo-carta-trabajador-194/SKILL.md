---
name: fin-erte-reincorporacion-trabajo-carta-trabajador-194
description: "Redacta el escrito «Fin del ERTE y reincorporación al trabajo: carta al trabajador» (formulario 194 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Fin del ERTE y reincorporación al trabajo: carta al trabajador

> Formulario 0194 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] Nº
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…e reincorpore a la actividad laboral. En»; «…, en su horario habitual de»

## Elecciones que hay que hacer

- por causas económicas / por causas técnicas / por causas organizativas / por fuerza mayor temporal / en aplicación del Mecanismo RED de Flexibilidad y Estabilización del Empleo
- suspensión de su contrato de trabajo / reducción de su jornada laboral
- a su puesto de trabajo / a su puesto de trabajo a jornada completa
- suspensión / reducción

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Asimismo se han comunicado estos extremos a la representación legal de los trabajadores.…

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

### Formulario 0194 · Fin del ERTE y reincorporación al trabajo: carta al trabajador

- Año del modelo: 2020
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 párrafos opcionales señalados; 10 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Comunicación al trabajador de la finalización del ERTE en el que se encontraba afectado para que se reincorpore a la actividad laboral.

En [COMPLETAR]

Estimado/a Sr./Sra. [NOMBRE Y APELLIDOS],

Por medio de la presente la dirección de la empresa le comunica que, con efectos desde el próximo día [FECHA], dejará de estar en vigor el Expediente de Regulación Temporal de Empleo nº [Nº DE EXPEDIENTE] presentado por la empresa [ELEGIR: por causas económicas / por causas técnicas / por causas organizativas / por fuerza mayor temporal / en aplicación del Mecanismo RED de Flexibilidad y Estabilización del Empleo] y que ha supuesto la [ELEGIR: suspensión de su contrato de trabajo / reducción de su jornada laboral] desde el pasado día [FECHA].

Por todo ello, con fecha [FECHA] deberá usted reincorporarse [ELEGIR: a su puesto de trabajo / a su puesto de trabajo a jornada completa], en su horario habitual de [COMPLETAR] a [Nº] horas.

La finalización de las medidas de [ELEGIR: suspensión / reducción] de jornada ya han sido comunicadas por la empresa a la Autoridad Laboral, la Seguridad Social y el Servicio Público de Empleo a los efectos oportunos, no teniendo que realizar usted ninguna gestión en relación con su reincorporación.

[OPCIONAL — incluir si procede]

Asimismo se han comunicado estos extremos a la representación legal de los trabajadores.

Le ruego firme el duplicado de esta carta como prueba de su recepción.

Atentamente,

Empresa

Recibí

Persona Trabajadora

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
