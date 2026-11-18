---
name: ausentarse-reducir-jornada-aviso-trabajador-347
description: "Redacta el escrito «Ausentarse o reducir jornada: aviso del trabajador» (formulario 347 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ausentarse o reducir jornada: aviso del trabajador

> Formulario 0347 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- El art. 37.6 ET (reducción por cuidado de menor con cáncer o enfermedad grave) fue modificado por el RDL 31/2026 (BOE-A-2026-21872, vigente desde el 23-10-2026): extensión más allá de los 23 y 26 años con discapacidad del 65 % o grado III de dependencia, tratamiento continuado sin hospitalización y disfrute por ambos progenitores de forma alternativa o simultánea.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, a [FECHA]. Muy Señor mío/Señora mía:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 37 del Estatuto de los Trabajadores

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

### Formulario 0347 · Ausentarse o reducir jornada: aviso del trabajador

- Año del modelo: 2017
- Revisión 17-11-2026: 1 bloques de alternativas señalados; 3 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: El art. 37.6 ET (reducción por cuidado de menor con cáncer o enfermedad grave) fue modificado por el RDL 31/2026 (BOE-A-2026-21872, vigente desde el 23-10-2026): extensión más allá de los 23 y 26 años con discapacidad del 65 % o grado III de dependencia, tratamiento continuado sin hospitalización y disfrute por ambos progenitores de forma alternativa o simultánea.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
Firmas

Carta de la persona trabajadora a la organización de su decisión de ausentarse o de reducir la jornada de trabajo, de conformidad con los apartados 4 a 8 del artículo 37 del Estatuto de los Trabajadores:

- Ausencia de una hora o de dos medias horas para el cuidado del lactante menor de 9 meses

- Reducción de media hora para el cuidado del lactante de 9/12 meses

- Reducción por guarda legal de menor de 12 años o persona con discapacidad

- Reducción por cuidado de cónyuge, pareja de hecho o familiar hasta segundo grado de consanguinidad o afinidad

- Reducción por cuidado de menor afectado por cáncer o enfermedad grave

- Reducción por nacimiento de hijo prematuro o que debe permanecer hospitalizado tras el parto

- Reducción por ser víctima de violencia de género, de víctima de violencia sexual o víctima de terrorismo

En [LUGAR], a [FECHA].

Muy Señor mío/Señora mía: [COMPLETAR]

Por la presente pongo en conocimiento de esta organización mi decisión de ejercitar el derecho que me confiere

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Ausencia de una hora o de dos medias horas para el cuidado del lactante menor de 9 meses)
— (Reducción de jornada en media hora para el cuidado del lactante menor de 9 meses)
— (Reducción por guarda legal de menor de 12 años o persona con discapacidad)
— (Reducción por cuidado de cónyuge o pareja de hecho, o un familiar hasta el segundo grado de consanguinidad y afinidad, incluido el familiar consanguíneo de la pareja de hecho)
— (Reducción cuidado de menor afectado por cáncer o enfermedad grave)
— (Reducción por nacimiento de hijo prematuro o que debe permanecer hospitalizado tras el parto)
— (Reducción por ser víctima de violencia de género, víctima de violencia sexual o víctima de terrorismo)

A la espera de su conformidad y rogándole firme la copia de la presente como acuse de recibo de ésta, le saluda atentamente,

La persona trabajadora

Recibí del representante de la organización

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
