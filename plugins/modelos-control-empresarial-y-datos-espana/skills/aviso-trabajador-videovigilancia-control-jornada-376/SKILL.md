---
name: aviso-trabajador-videovigilancia-control-jornada-376
description: "Redacta el escrito «Aviso al trabajador de videovigilancia, control de jornada o geolocalización» (formulario 376 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Aviso al trabajador de videovigilancia, control de jornada o geolocalización

> Formulario 0376 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

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

- Separar las tres opciones: videovigilancia (art. 89 LOPDGDD), geolocalización (art. 90) y registro de jornada (art. 34.9 ET, con negociación o consulta previa a la RLT y conservación 4 años).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] LOCALIDAD
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, a [FECHA]. La empresa»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Instalación de sistema de videovigilancia / Instalación de sistema para el registro de jornada / Instalación de sistema de geolocalización en terminales móviles o vehículos de empresa / La empresa	La persona trabajadora — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 18 ET

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

### Formulario 0376 · Aviso al trabajador de videovigilancia, control de jornada o geolocalización

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 campos de relleno marcados en blanco
- Avisos de la revisión: Separar las tres opciones: videovigilancia (art. 89 LOPDGDD), geolocalización (art. 90) y registro de jornada (art. 34.9 ET, con negociación o consulta previa a la RLT y conservación 4 años).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

El artículo 18 ET atribuye al empresario un control [NOTA DE REVISIÓN: El art. 18 ET regula solo los registros sobre la persona, taquillas y efectos. La videovigilancia y la geolocalización se amparan en el art. 20.3 ET y en los arts. 89-90 LOPDGDD (art. 20 bis ET); el registro de jornada es una obligación del art. 34.9 ET que se organiza por convenio, acuerdo de empresa o decisión del empresario previa consulta con la RLT. Fuente: RDLeg 2/2015 (ET), BOE-A-2015-11430, arts. 18, 20.3, 20 bis y 34.9; LO 3/2018 (LOPDGDD), BOE-A-2018-16673, arts. 89-90.] que excede del que deriva de su posición en el contrato de trabajo. Es un control vinculado a la defensa del patrimonio empresarial, del patrimonio de otros trabajadores de la empresa y al control de la actividad laboral. Pero el empresario tiene la obligación de informar a las personas trabajadoras sobre la existencia de cámaras de vigilancia (videovigilancia), sistemas de registro de la jornada o geolocalización.

La LOPDGDD (arts. 89 y 90) obliga [NOTA DE REVISIÓN: La ley es de 2018; precisar los artículos. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, arts. 89 y 90.] a informar con carácter previo a los representantes de los trabajadores sobre la instalación de sistemas de videovigilancia. También a los trabajadores debiendo instalarse además un cartel informativo. En base al RGPD y doctrina judicial debe informarse claramente sobre la finalidad: las funciones de control empresarial sólo pueden satisfacer un derecho o un interés legítimo del empleador. Si se pretende una finalidad sancionadora ante un incumplimiento del trabajador este punto debe ser informado por el empleador. Admás, la medida de control sólo será válida si supera el juicio de proporcionalidad (idoneidad, necesidad y proporcionalidad).

En [LUGAR], a [FECHA].

La empresa [COMPLETAR], con domicilio en [LOCALIDAD], informa a la persona trabajadora D./Dña. [NOMBRE Y APELLIDOS], que presta sus servicios en la misma,

[ELEGIR UNA OPCIÓN Y REDACTARLA: Instalación de sistema de videovigilancia / Instalación de sistema para el registro de jornada / Instalación de sistema de geolocalización en terminales móviles o vehículos de empresa / La empresa	La persona trabajadora — el texto de cada opción no venía en el formulario original]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
