---
name: pedir-jubilacion-parcial-empresa-150
description: "Redacta el escrito «Pedir jubilación parcial a la empresa» (formulario 150 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir jubilación parcial a la empresa

> Formulario 0150 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Jubilación parcial (RDL 11/2024): con relevo, hasta tres años antes de la edad ordinaria, 33 años cotizados (25 con discapacidad del 33 %), seis años de antigüedad y reducción del 25 % al 75 % (del 20 % al 33 % el primer año si se anticipa más de dos años); tras la edad ordinaria, sin relevo (art. 215.1).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº (3 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o. Att. Dirección de Recursos Humanos En»; «… jubilación parcial a partir del próximo»; «…4, BOE-A-2024-26917, vigente 1-4-2025).]»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 215 de la Ley General de la Seguridad Social
- Real Decreto-ley 11/2024

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

### Formulario 0150 · Pedir jubilación parcial a la empresa

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 7 campos de relleno marcados en blanco
- Avisos de la revisión: Jubilación parcial (RDL 11/2024): con relevo, hasta tres años antes de la edad ordinaria, 33 años cotizados (25 con discapacidad del 33 %), seis años de antigüedad y reducción del 25 % al 75 % (del 20 % al 33 % el primer año si se anticipa más de dos años); tras la edad ordinaria, sin relevo (art. 215.1).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Firmas

Mediante el presente escrito o carta la persona trabajadora solicita a la empresa la conversión de su contrato de tiempo completo en contrato de tiempo parcial para acceder a la jubilación parcial.

Actualizado según las modificaciones introducidas por el Real Decreto-ley 11/2024, de 23 de diciembre, para la mejora de la compatibilidad de la pensión de jubilación con el trabajo.

Att. Dirección de Recursos Humanos

En [COMPLETAR]

Muy señores míos,

Por medio de la presente les comunico mi deseo de acceder a la jubilación parcial a partir del próximo [COMPLETAR], fecha en la que cumpliré [Nº] años.

Habiendo cotizado más de [Nº] años y teniendo una antigüedad en la empresa de [Nº] años, se cumplen todas las condiciones establecidas en el art. 215 de la Ley General de la Seguridad Social para acceder a la jubilación parcial.

Por ello me gustaría llegar a un acuerdo con la empresa para seguir trabajando a tiempo parcial, con una reducción de jornada del % [NOTA DE REVISIÓN: Errata. Límites vigentes de la reducción: entre el 25 % y el 75 % (y del 20 % al 33 % el primer año si se anticipa más de dos años). Fuente: art. 215 LGSS (red. RDL 11/2024, BOE-A-2024-26917, vigente 1-4-2025).] [COMPLETAR], hasta mi completa jubilación.

Les ruego, por tanto, que, una vez estudiada mi propuesta, me comuniquen su decisión y quedo a su disposición para ampliarles cualquier información que consideren oportuna.

Muchas gracias por su atención y, a la espera de sus noticias, les saluda atentamente,

La persona trabajadora

Recibí

D./Dña. [NOMBRE Y APELLIDOS] 	La empresa

════════════════════════════════════════════════════════════════════════
