---
name: reconocer-responsabilidad-pagar-voluntariamente-sancion-152
description: "Redacta el escrito «Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección» (formulario 152 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección

> Formulario 0152 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- La reducción del 40 % (art. 14.6 RD 928/1998, desde 1-1-2022) exige sanción solo pecuniaria, pago antes de la resolución y renuncia a recursos; pago en 10 días hábiles desde la notificación del documento (art. 18 bis.7); excluida en actas concurrentes con liquidación por los mismos hechos (para ellas, art. 34.2 RD 928/1998 y reducción automática del 50 % del art. 40.3 LISOS si se acepta e ingresa la liquidación).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NÚMERO (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] NIF
- [ ] LOCALIDAD
- [ ] TELÉFONO
- [ ] FECHA (2 veces)
- [ ] IMPORTE
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…DAD ESPECIALIZADA DE SEGURIDAD SOCIAL DE»; «…Inspección Provincial de Trabajo y SS de»; «…en nombre y representación de la empresa»; «…vincial de Trabajo y Seguridad Social de»; «…alizado el procedimiento sancionador. En»

## Elecciones que hay que hacer

- leve / grave / muy grave

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 18 bis.7 del Real Decreto 928/1998
- art. 14.6 del Real Decreto 928/1998

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

### Formulario 0152 · Reconocer la responsabilidad y pagar voluntariamente la sanción de la Inspección

- Año del modelo: 2021
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 16 campos de relleno marcados en blanco
- Avisos de la revisión: La reducción del 40 % (art. 14.6 RD 928/1998, desde 1-1-2022) exige sanción solo pecuniaria, pago antes de la resolución y renuncia a recursos; pago en 10 días hábiles desde la notificación del documento (art. 18 bis.7); excluida en actas concurrentes con liquidación por los mismos hechos (para ellas, art. 34.2 RD 928/1998 y reducción automática del 50 % del art. 40.3 LISOS si se acepta e ingresa la liquidación).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

EXPONE
Firmas

Escrito mediente el cual la empresa manifiesta su renuncia a la interposición de cualquier acción, alegación o recurso en vía administrativa contra la sanción y reconoce su responsabilidad aceptando el pago voluntario del importe de la sanción con la aplicación de la máxima reducción del 40%.

Téngase en cuenta que algunas CCAA tienen formularios telemáticos para realizar este trámite.

A LA INSPECCIÓN DE TRABAJO Y SEGURIDAD SOCIAL DE /JEFATURA DE LA UNIDAD ESPECIALIZADA DE SEGURIDAD SOCIAL DE [COMPLETAR]

REF: Acta de Infracción de la Inspección Provincial de Trabajo y SS de [COMPLETAR] nº [NÚMERO]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE], en nombre y representación de la empresa [COMPLETAR], con NIF [NIF] y domicilio en [LOCALIDAD], según se acredita mediante la escritura de poder que a este escrito se acompaña como DOC. Nº 1, y con teléfono [TELÉFONO] y correo electrónico

EXPONE

PRIMERO.- Que con fecha [FECHA] se ha notificado a mi representada acta de infracción nº [NÚMERO], de fecha [FECHA] de la Inspección Provincial de Trabajo y Seguridad Social de [COMPLETAR], por la que se imputa a la empresa una infracción [ELEGIR: leve / grave / muy grave] tipificada en el art. de la LISOS y se propone una sanción por un importe total de [IMPORTE] euros.

SEGUNDO.- Que por medio del presente escrito, dentro del plazo de quince días concedido para presentar alegaciones, la empresa manifiesta su renuncia a la interposición de cualquier acción, alegación o recurso en vía administrativa contra la citada sanción y reconoce su responsabilidad y acepta el pago voluntario del importe de la sanción con la aplicación de la máxima reducción del 40%.

TERCERO.- Que una vez le sean remitidos a mi representada los documentos e instrucciones precisas para el pago de la sanción, la misma procederá a su realización y acreditación al Órgano al que me dirijo en el plazo de diez días hábiles establecido en el art. 18 bis.7 del Real Decreto 928/1998 [NOTA DE REVISIÓN: Plazo de pago y acreditación: diez días hábiles desde la notificación del documento de pago (ámbito AGE). En CCAA con competencias, comprobar su normativa. Fuente: RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 18 bis.7.].

Por lo expuesto,

SOLICITO que teniendo por presentado este escrito en tiempo y forma, se admita y en virtud de lo expuesto en el mismo, se aplique la reducción del 40 por ciento prevista en el art. 14.6 del Real Decreto 928/1998 [NOTA DE REVISIÓN: En el orden social el reglamento fija una reducción única del 40 % (pago previo a la resolución + renuncia a recursos, sanción solo pecuniaria); el 20 % + 20 % del art. 85.3 LPAC es el régimen general que el propio 85.3 permite elevar reglamentariamente. No cabe en actas de infracción concurrentes con actas de liquidación por los mismos hechos (art. 14.6, párr. 4º). Fuente: RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 14.6; Ley 39/2015, BOE-A-2015-10565, art. 85.3.], de 14 de mayo, por el que se aprueba el Reglamento General sobre procedimientos para la imposición de las sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social, se remita el documento de pago con la reducción correspondiente y, una vez comprobada la realización del mismo, se dicte resolución dando por finalizado el procedimiento sancionador.

En [COMPLETAR]

Fdo. D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
