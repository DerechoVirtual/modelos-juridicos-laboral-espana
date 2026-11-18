---
name: despido-colectivo-carta-plantilla-nombrar-comision-186
description: "Redacta el escrito «Despido colectivo: carta a la plantilla para nombrar la comisión negociadora» (formulario 186 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido colectivo: carta a la plantilla para nombrar la comisión negociadora

> Formulario 0186 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…ibilidad de continuar con el negocio por»

## Elecciones que hay que hacer

- total / parcial
- económicas / técnicas / organizativas / productivas

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 41.4 del ET
- artículo 51 del Estatuto de los Trabajadores

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

### Formulario 0186 · Despido colectivo: carta a la plantilla para nombrar la comisión negociadora

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 5 campos de relleno marcados en blanco
- Avisos de la revisión: Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

A fin de poder iniciar el periodo de consultas, la empresa debe comunicar a los representantes de los trabajadores o a las personas trabajadoras (si no hubiera representación) su intención de iniciar un proceso de despido colectivo y emplazarles para que en 7 días (o 15 si no todos los centros de trabajo afectados cuentan con representación legal de trabajadores) para que constituyan su representación en la Comisión Negociadora mediante las reglas del artículo 41.4 del ET [NOTA DE REVISIÓN: El art. 51.2 ET remite al art. 41.4 ET para designar a los interlocutores. Fuente: ET (RDLeg 2/2015), BOE-A-2015-11430, arts. 41.4 y 51.2.].

D./Dña. [NOMBRE Y APELLIDOS]

En [LUGAR], a [FECHA].

Muy Sr./Sra. nuestro/a,

Como ya les ha comunicado verbalmente la Dirección de la empresa y por los motivos que ya conocen de imposibilidad de continuar con el negocio por [COMPLETAR] y, consecuentemente, la cesación [ELEGIR: total / parcial] de la actividad, les comunico que la empresa va a iniciar un procedimiento de despido colectivo por causas [ELEGIR: económicas / técnicas / organizativas / productivas] en virtud de lo establecido en el artículo 51 del Estatuto de los Trabajadores.

La intervención como interlocutores ante la dirección de la empresa en el procedimiento de consultas corresponderá a los sujetos indicados en el artículo 41.4 del Estatuto de los trabajadores, que establece que "en el supuesto de que en el centro de trabajo no exista representación legal de los trabajadores, estos podrán optar por atribuir su representación para la negociación del acuerdo, a su elección, a una comisión de un máximo de tres miembros integrada por trabajadores de la propia empresa y elegida por estos democráticamente o a una comisión de igual número de componentes designados, según su representatividad, por los sindicatos más representativos y representativos del sector al que pertenezca la empresa y que estuvieran legitimados para formar parte de la comisión negociadora del convenio colectivo de aplicación a la misma".

Con el fin de negociar los términos del procedimiento en el período de consultas y no existiendo representación legal de los trabajadores, por medio de la presente les rogamos que nos comuniquen los tres miembros que van a constituir la Comisión Negociadora en representación de todas las personas trabajadoras.

La comisión negociadora de los procedimientos en representación de los trabajadores deberá establecer en su acta de constitución que se constituyen como órgano colegiado en cuanto a la formación de su voluntad y el carácter vinculante de sus decisiones.

A la espera de la conformación de la citada comisión, que deberá estar constituida en el plazo máximo de siete días, les rogamos que firmen esta comunicación como prueba de su recepción.

Atentamente,

La Empresa	Recibí

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
