---
name: mecanismo-red-apertura-periodo-consultas-comunicada-61
description: "Redacta el escrito «Mecanismo RED: apertura del periodo de consultas comunicada a la plantilla» (formulario 61 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mecanismo RED: apertura del periodo de consultas comunicada a la plantilla

> Formulario 0061 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LOCALIDAD
- [ ] Nº (2 veces)
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…n caso, la ampliación de su duración. En»; «…Muy Sres. nuestros:»; «…brarán en los locales de la empresa: 1ª)»; «…, a las [Nº] horas 2ª)»; «…esignación de las personas afectadas son»; «…es el»; «…y tendrá una duración hasta»; «…. Las medidas consistirán en»

## Elecciones que hay que hacer

- reducción de la jornada / suspensión de los contratos de trabajo
- quince / siete
- suspensiones de contratos / reducciones de jornada
- cíclica / sectorial
- suspensión de contratos / reducción de jornada
- suspensión de los contratos / reducción de jornada

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Sólo en el caso de la modalidad sectorial del mecanismo RED)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 6.2 del Real Decreto 608/2023

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

### Formulario 0061 · Mecanismo RED: apertura del periodo de consultas comunicada a la plantilla

- Año del modelo: 2023
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 1 párrafos opcionales señalados; 13 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Constituida la comisión representativa o transcurrido el plazo máximo para su constitución, la dirección de la empresa podrá comunicar formalmente a la representación de las personas trabajadoras la apertura del periodo de consultas. La falta de constitución de dicha comisión representativa no impedirá el inicio y transcurso del periodo de consultas, y su constitución con posterioridad al inicio del mismo no comportará, en ningún caso, la ampliación de su duración.

En [COMPLETAR]

Muy Sres. nuestros: [COMPLETAR]

Debido a la situación que atraviesa la empresa y de conformidad con lo dispuesto en el artículo 47.bis del Estatuto de los Trabajadores, y en el Real Decreto 608/2023, de 11 de julio, les comunico que la empresa va a proceder a la [ELEGIR: reducción de la jornada / suspensión de los contratos de trabajo] como consecuencia del cese en la actividad en el centro de trabajo sito en [LOCALIDAD], así como el inicio del período de consultas con el objeto de llegar a un acuerdo.

Dando cumplimiento a lo dispuesto en el artículo 6.2 del Real Decreto 608/2023, de 11 julio, con esta misma fecha se notifica a la Autoridad Laboral el comienzo del período de consultas a que se refiere el citado precepto, por lo que con fecha de hoy se tiene por iniciado el mismo, el cual tendrá una duración no superior a [ELEGIR: quince / siete] días naturales y con el siguiente calendario de reuniones, que se celebrarán en los locales de la empresa:

1ª) [COMPLETAR], a las [Nº] horas
2ª) [COMPLETAR], a las [Nº] horas

Las causas que motivan las [ELEGIR: suspensiones de contratos / reducciones de jornada], se detallan en la Memoria explicativa que se hace entrega junto a este escrito, así como la documentación que se adjunta acreditativa de la concurrencia de la situación [ELEGIR: cíclica / sectorial] establecida en el acuerdo de activación del Mecanismo RED aprobado por Acuerdo del Consejo de Ministros de fecha [FECHA].

El número y clasificación profesional de las personas trabajadoras afectadas por la medida de [ELEGIR: suspensión de contratos / reducción de jornada] son los siguientes:

Categorías	Afectados/as	No afectados/as	Total	Total general
Hombres	Mujeres	Hombres	Mujeres	Hombres	Mujeres

Los criterios que se han tenido en cuenta para la designación de las personas afectadas son [COMPLETAR].

La fecha prevista para la [ELEGIR: suspensión de los contratos / reducción de jornada] es el [COMPLETAR] y tendrá una duración hasta [COMPLETAR].

Las medidas consistirán en [COMPLETAR].

[OPCIONAL — incluir si procede]

(Sólo en el caso de la modalidad sectorial del mecanismo RED)

Se acompaña a esta comunicación un plan de recualificación de las personas afectadas.

Les informamos que en esta misma fecha se procede a comunicar a la autoridad laboral la apertura del periodo de consultas.

Le rogamos acuse recibo de esta notificación y documentación que se acompaña a la misma.

Atentamente,

Empresa

Recibí

Personas trabajadoras

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
