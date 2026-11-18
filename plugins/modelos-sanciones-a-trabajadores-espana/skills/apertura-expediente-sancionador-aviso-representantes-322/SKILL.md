---
name: apertura-expediente-sancionador-aviso-representantes-322
description: "Redacta el escrito «Apertura de expediente sancionador: aviso a representantes, sindicato y delegado de prevención» (formulario 322 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Apertura de expediente sancionador: aviso a representantes, sindicato y delegado de prevención

> Formulario 0322 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] Nº
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ado y proponer las pruebas que deseen. A»; «…ical Muy Sr. mío/Sra. mía/Srs. nuestros:»; «…de»; «…l art. del vigente Convenio Colectivo de»; «…diente disciplinario son los siguientes:»; «…rmidad con lo prevenido en los artículos»

## Elecciones que hay que hacer

- grave / muy grave
- legales / sindicales

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 54.2 del Estatuto de los Trabajadores

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

### Formulario 0322 · Apertura de expediente sancionador: aviso a representantes, sindicato y delegado de prevención

- Año del modelo: 2017
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 11 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Firmas

Modelo de comunicación a la representación legal de los trabajadores, la representación sindical o al delegado de prevención de apertura de expediente disciplinario previo a la imposición de sanción, a fin de que puedan evacuar el oportuno informe, alegar lo que estimen apropiado y proponer las pruebas que deseen.

A [COMPLETAR].

Att.
Comité de empresa
Delegado/s de personal
Delegado/a sindical

Muy Sr. mío/Sra. mía/Srs. nuestros: [COMPLETAR]

Por la presente comunicación ponemos en su conocimiento los siguientes particulares:

a) Se ha abierto expediente disciplinario previo a una posible sanción disciplinaria en grado de [ELEGIR: grave / muy grave] a D./Dña. [NOMBRE Y APELLIDOS], trabajador/a de esta empresa, que ostenta la condición de miembro del Comité de empresa/Delegado de personal/Delegado sindical/Delegado de prevención.
b) Dicha persona ha cometido una falta [ELEGIR: grave / muy grave] de [COMPLETAR], tipificada en el art. del vigente Convenio Colectivo de [COMPLETAR] y sancionable conforme a lo establecido en el art. de dicha norma convencional y, en su caso, art. 54.2 del Estatuto de los Trabajadores.
c) Los hechos que han dado lugar a la apertura del expediente disciplinario son los siguientes: [COMPLETAR].
d) Se ha nombrado Instructor/a del expediente contradictorio a D./Dña. [NOMBRE Y APELLIDOS], y Secretario/a del mismo a D./Dña. [NOMBRE Y APELLIDOS].
e) Se ha comunicado esta decisión de apertura de expediente disciplinario a los demás representantes [ELEGIR: legales / sindicales] de las personas trabajadoras, a fin de que en el plazo de [Nº] días, puedan ustedes evacuar el oportuno informe, alegar lo que estimen apropiado y proponer las pruebas que deseen ante el citado Instructor, a los posibles efectos y de conformidad con lo prevenido en los artículos [COMPLETAR] del Convenio colectivo de y/o artículos 55.1 y 68 a) del Estatuto de los Trabajadoresy/o artículo 10.3 de la Ley Orgánica de Libertad Sindical.

Le rogamos acuse recibo y firme copia de la presente a los solos efectos de probar su recepción.

Empresa

Recibí

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
