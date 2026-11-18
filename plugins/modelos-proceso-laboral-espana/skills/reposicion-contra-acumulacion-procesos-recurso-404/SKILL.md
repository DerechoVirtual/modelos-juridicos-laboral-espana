---
name: reposicion-contra-acumulacion-procesos-recurso-404
description: "Redacta el escrito «Reposición contra la acumulación de procesos: recurso» (formulario 404 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reposición contra la acumulación de procesos: recurso

> Formulario 0404 del plugin **Proceso laboral** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS
- [ ] LOCALIDAD
- [ ] DNI/NIE
- [ ] DESCRIBIR (2 veces)
- [ ] NOMBRE DEL SOLICITANTE
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (3 veces)
- [ ] Nº DE PROCEDIMIENTO (4 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, y DNI nº [DNI/NIE], demandado en autos»; «…, promovidos por»; «…sea en Derecho, digo: Que solicitada por»; «…lación de los referidos autos al proceso»; «…rida incurre en la siguiente infracción:»; «…para»

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

### Formulario 0404 · Reposición contra la acumulación de procesos: recurso

- Año del modelo: 2015
- Revisión 17-11-2026: 20 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A la Sección de lo Social del Tribunal de Instancia de [SEDE]

D. [NOMBRE Y APELLIDOS], mayor de edad, con domicilio en [LOCALIDAD], y DNI nº [DNI/NIE], demandado en autos [COMPLETAR], promovidos por [COMPLETAR] contra el exponente, sobre [DESCRIBIR], respetuosamente comparezco y, como más procedente sea en Derecho, digo:

Que solicitada por [COMPLETAR] la acumulación de los referidos autos al proceso [COMPLETAR], seguido a instancia de [NOMBRE DEL SOLICITANTE], contra [ACTO O RESOLUCIÓN], sobre [DESCRIBIR], vengo a interponer recurso de reposición contra la pretendida acumulación con base en los siguientes razonamientos:

Primero.— Que en fecha [FECHA] se me ha notificado la resolución dictada por ese Tribunal el día [FECHA], en virtud de la cual se procede a la acumulación de los autos nº [Nº DE PROCEDIMIENTO] a los autos nº [Nº DE PROCEDIMIENTO]

Segundo.— La resolución recurrida incurre en la siguiente infracción: [COMPLETAR], por los siguientes motivos: (no ser acumulables los procesos, ejercitarse acciones distintas, haberse tramitado en procedimientos administrativos separados, etc.).

Por lo expuesto, y en virtud de lo establecido en el artículo 186 de la Ley reguladora de la Jurisdicción Social,

SUPLICO AL TRIBUNAL que, habiendo por presentado este escrito con sus copias, tenga por interpuesto en tiempo y forma recurso de reposición contra la resolución de fecha [FECHA] para [COMPLETAR], previa su legal tramitación, dictar auto por el que se estime el recurso y se acuerde dejar sin efecto la acumulación de los autos nº [Nº DE PROCEDIMIENTO] a los autos nº [Nº DE PROCEDIMIENTO].

Pues así procede en justicia, a cuyo título lo pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma

Normativa aplicable

– Ley reguladora de la Jurisdicción Social: Artículos 28 a 32 y 186 y 187.

================================================================================
