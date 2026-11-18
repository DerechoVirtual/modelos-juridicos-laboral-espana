---
name: contrato-laboral-colaboracion-formar-cuadrilla-133
description: "Redacta el escrito «Contrato laboral de colaboración para formar una cuadrilla» (formulario 133 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato laboral de colaboración para formar una cuadrilla

> Formulario 0133 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] LUGAR (2 veces)
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, a [FECHA]. REUNIDOS De una parte, el»; «… domicilio en [LOCALIDAD]. Y de otra, el»; «…solicita y requiere los servicios del»; «…o las siguientes CONDICIONES Primera. El»; «…formará parte de la cuadrilla de»; «…durante la temporada taurina de»; «…llo del espectáculo taurino. Segunda. El»; «…iones del jefe de cuadrilla. Tercera. El»

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

### Formulario 0133 · Contrato laboral de colaboración para formar una cuadrilla

- Año del modelo: 2022
- Revisión 17-11-2026: 16 campos de relleno marcados en blanco; 2 huecos del original que se habían perdido sin marca, marcados (DNI/NIE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
CONDICIONES
CLAÚSULAS ADICIONALES
Firmas

Los contratos entre los Jefes de Cuadrilla y los integrantes de ésta se formalizarán preferentemente por escrito.

Los jefes de cuadrilla que vengan obligados a contratar toda o parte de su cuadrilla fija, comunicarán a la Comisión de Seguimiento, antes del 15 de enero de cada año, el nombre, apellidos y puesto de cada uno de los miembros de su cuadrilla.

En [LUGAR], a [FECHA].

REUNIDOS

De una parte, el [COMPLETAR] D./Dña. [NOMBRE Y APELLIDOS], con DNI núm. [DNI/NIE] y domicilio en [LOCALIDAD].

Y de otra, el [COMPLETAR] D./Dña. [NOMBRE Y APELLIDOS], con DNI núm. [DNI/NIE] y domicilio en [LOCALIDAD].

Ambas partes se reconocen mutua capacidad para el otorgamiento del presente contrato, en el que previamente

EXPONEN

Que, para formalizar la constitución de su reglamentaria cuadrilla, prevista por las disposiciones en vigor, D./Dña. [NOMBRE Y APELLIDOS] solicita y requiere los servicios del [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS], que acepta y se obliga a desempeñar su colaboración profesional, pactando las siguientes

CONDICIONES

Primera. El [COMPLETAR] formará parte de la cuadrilla de [COMPLETAR] durante la temporada taurina de [COMPLETAR], de conformidad con lo previsto en las normas y disposiciones que regulan la organización y desarrollo del espectáculo taurino.

Segunda. El [COMPLETAR] se obliga a concurrir a todas las actuaciones del jefe de cuadrilla para las que la normativa vigente exija cuadrilla completa. En caso de que la actuación no requiriese cuadrilla completa (festivales y otros festejos en los que el jefe de cuadrilla lidie una sola res), se estará a las oportunas instrucciones del jefe de cuadrilla.

Tercera. El [COMPLETAR] devengará como retribución por cada una de sus actuaciones, la establecida para cada categoría de plaza por las tablas salariales anexas al Convenio Colectivo Nacional Taurino. Las mismas tablas serán de aplicación para las actuaciones que, en su caso, tuvieran lugar en plazas americanas, si el subalterno fuese designado por el jefe de cuadrilla para actuar allí.

Cuarta. Este contrato será visado y registrado en la Comisión de Seguimiento, Vigilancia y Control del Convenio Colectivo Nacional Taurino, en sus oficinas ubicadas en Madrid, c/ Carretas, 27, 1.º dcha.

CLAÚSULAS ADICIONALES

Y en prueba de conformidad, firman por triplicado ejemplar en [LUGAR], a [FECHA].

EL SUBALTERNO	VISADO CSVC	EL JEFE DE CUADRILLA

════════════════════════════════════════════════════════════════════════
