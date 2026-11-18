---
name: informacion-sobre-proteccion-datos-geolocalizacion-252
description: "Redacta el escrito «Información sobre protección de datos en la geolocalización: cláusula» (formulario 252 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información sobre protección de datos en la geolocalización: cláusula

> Formulario 0252 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

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

- Informar también a la RLT «en su caso» y de los derechos de acceso, rectificación, limitación y supresión (art. 90.2 LOPDGDD); la base es el art. 20.3 ET, no el consentimiento.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…co de la relación laboral que le une con»; «… caso, en los vehículos) facilitados por»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 20.3 del Estatuto de los Trabajadores
- artículos 12 y 13 del RGPD
- artículo 90 de la Ley Orgánica 3/2018
- art. 90.2 LOPDGDD
- artículos 15 a 22 del RGPD

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

### Formulario 0252 · Información sobre protección de datos en la geolocalización: cláusula

- Año del modelo: 2018
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 6 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Informar también a la RLT «en su caso» y de los derechos de acceso, rectificación, limitación y supresión (art. 90.2 LOPDGDD); la base es el art. 20.3 ET, no el consentimiento.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Consentimiento
Información sistema de control
Finalidad de la geolocalización
Firmas

La doctrina judicial considera válido el control de la actividad laboral a través de estos sistemas, pero, en la medida en que puede afectar a la intimidad o al derecho a la protección de datos, se exige que haya previa información a la persona trabajadora y sus representeantes sobre su utilización. El control será limitado y no se utilizará más allá de la actividad durante la jornada laboral.

El/La abajo firmante, D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], en el marco de la relación laboral que le une con [COMPLETAR], se da por informado/a de la siguiente medida de control establecida por la empresa, a partir del día [FECHA]:

En los próximos días se va a implementar un sistema de geolocalización en los terminales móviles (o en su caso, en los vehículos) facilitados por [COMPLETAR], para el desempeño de la actividad, que permite obtener información acerca de la situación geográfica de las personas trabajadoras, exclusivamente durante su jornada laboral.

Los vehículos de la flota comercial de la empresa están dotados de dispositivos de geolocalización con el objeto de ejercer las atribuciones otorgadas por el art. 20.3 del Estatuto de los Trabajadores, pudiendo la empresa obtener información sobre los movimientos de los vehículos al objeto de gestionar con mayor eficacia las rutas comerciales.

En cumplimiento de lo dispuesto en los artículos 12 y 13 del RGPD y artículo 90 de la Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales, le informamos que los datos recogidos con ocasión del citado sistema de geolocalización van a ser objeto de tratamiento por parte de la empresa, con la finalidad de gestionar la relación laboral existente, no siendo cedidos a terceros salvo obligación legal. Puede ejercer los derechos de acceso, rectificación, limitación del tratamiento y supresión (art. 90.2 LOPDGDD), así como los demás previstos en los artículos 15 a 22 del RGPD. [NOTA DE REVISIÓN (comprobar): El art. 90.2 LOPDGDD exige informar de los derechos; la exclusión absoluta de cesiones es inexacta (requerimientos de la ITSS, juzgados). Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 90.2; Reglamento (UE) 2016/679 (RGPD), CELEX 32016R0679, arts. 15-22.]

En [LUGAR], a [FECHA].

D-/Dña. [NOMBRE Y APELLIDOS]

Firma de la persona trabajadora

════════════════════════════════════════════════════════════════════════
