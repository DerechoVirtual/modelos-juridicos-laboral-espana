---
name: incapacidad-permanente-demanda-generica-121
description: "Redacta el escrito «Incapacidad permanente: demanda genérica» (formulario 121 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Incapacidad permanente: demanda genérica

> Formulario 0121 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- «Sala de lo Social del Tribunal de Instancia» no existe: Sección de lo Social. La demanda de IP se dirige contra INSS y TGSS (y mutua o empresa, si son responsables), no contra el «empleador».

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] LRJS
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (11 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 20 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con domicilio en [LOCALIDAD], de»; «…, con domicilio en [LOCALIDAD] de»; «…ta afiliado a la Seguridad Social con el»; «… profesión del/de la demandante es la de»; «…, correspondiente al grupo profesional»; «…conforme al Convenio Colectivo»; «…eso de incapacidad temporal, derivado de»; «…con el diagnóstico de»; «…citada, alegando los siguientes motivos:»; «…o 194 LGSS se le declare en situación de»; «…, derivada de»; «…actora es tributaria son las siguientes:»; …

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: Que a los efectos legalmente previstos interesa a esta parte que por ese Tribunal se requi…
- SEGUNDO OTROSÍ DIGO: Que a efectos de práctica de prueba interesa esta parte que en el acto del juicio se apor…
- TERCER OTROSÍ DIGO: Que compareceré al acto del juicio asistido de letrado/a que me dirija y defienda, designa…
- CUARTO OTROSÍ DIGO: Que, de conformidad con lo previsto en el artículo 140.1 en relación al artículo 71, ambos…

## Correcciones de la revisión (4)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica 6/1985
- artículos 2, 6 y 10 LRJS
- artículo 17.1 LRJS
- artículo 194 LGSS
- artículos 143 a 145 LRJS
- Ley 36/2011

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

### Formulario 0121 · Incapacidad permanente: demanda genérica

- Año del modelo: 2022
- Revisión 17-11-2026: 3 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 4 párrafos opcionales señalados; 40 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: «Sala de lo Social del Tribunal de Instancia» no existe: Sección de lo Social. La demanda de IP se dirige contra INSS y TGSS (y mutua o empresa, si son responsables), no contra el «empleador».

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Hechos
Título
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: No existe «Sala de lo Social del Tribunal de Instancia»: el Tribunal de Instancia se organiza en Secciones; «Sala de lo Social» solo en TSJ, AN y TS. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76; arts. 59, 67 y 75 LOPJ.]

D./Dña. [NOMBRE Y APELLIDOS], provisto/a de DNI/NIE [DNI/NIE], con domicilio en [LOCALIDAD], de [COMPLETAR], ante ese Tribunal comparezco y, como mejor en Derecho proceda,

DIGO:

Que mediante el presente escrito vengo a interponer demanda de reclamación de incapacidad permanente al amparo del artículo 140 y siguientes concordantes de la Ley 36/2011, de 10 de octubre, Reguladora de la Jurisdicción Social [LRJS] contra el [ACTO O RESOLUCIÓN], con domicilio en [LOCALIDAD] de [COMPLETAR].

Hechos

Primero.– Circunstancias personales del actor/a

El/La actor/a, nacido/a en fecha [FECHA], consta afiliado a la Seguridad Social con el [COMPLETAR]

La profesión del/de la demandante es la de [COMPLETAR], correspondiente al grupo profesional [COMPLETAR] conforme al Convenio Colectivo [COMPLETAR].

Segundo.– Incapacidad temporal

En fecha [FECHA] la parte actora inició un proceso de incapacidad temporal, derivado de [COMPLETAR] con el diagnóstico de [COMPLETAR].

Ha permanecido en dicha situación de baja hasta el [FECHA].

Tercero.– Tramitación administrativa de la incapacidad permanente

En fecha [FECHA] solicité el reconocimiento de una incapacidad permanente.

Por resolución de fecha [FECHA] notificada a esta parte el día [FECHA] la entidad gestora ha denegado el reconocimiento de dicha prestación solicitada, alegando los siguientes motivos: [COMPLETAR].

En fecha [FECHA] interpuse la correspondiente reclamación previa, que se acompaña a esta demanda. Por resolución de [FECHA], notificada a esta parte en fecha [FECHA] se ha desestimado dicha reclamación previa.

Título

Primero.– Jurisdicción y competencia

El conocimiento de esta demanda es competencia de ese tribunal, de conformidad con las reglas conformadoras de la jurisdicción y la competencia material y territorial aplicables, en aplicación de los artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica 6/1985, de 1 de julio, del Poder Judicial y los artículos 2, 6 y 10 LRJS.

Segundo.– Legitimación activa y pasiva

Ostenta legitimación activa el firmante en su condición de trabajador y pasiva la demandada en su condición de empleador [NOTA DE REVISIÓN (comprobar): En incapacidad permanente la legitimación pasiva es de la entidad gestora (INSS y TGSS) y, en su caso, mutua y empresa responsables; no basta «empleador». Fuente: arts. 140 y 143 LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], de conformidad con el artículo 17.1 LRJS.

Tercero.– Modalidad procesal adecuada

Tratándose de una demanda resultan de aplicación las especificidades contempladas en el artículo 140 y siguientes LRJS.

Cuarto.– Pretensión procesal

Postula esta parte que, de conformidad con el artículo 194 LGSS se le declare en situación de [COMPLETAR], derivada de [COMPLETAR].

En efecto, las lesiones de las que la parte actora es tributaria son las siguientes: [COMPLETAR].

Las limitaciones funcionales que conllevan dichas dolencias son las siguientes:

Quinto.– Base reguladora y fecha de efectos

La referida prestación debe ser calculada sobre una base reguladora de [IMPORTE] €, siendo la fecha de efectos de dicho reconocimiento la de [COMPLETAR].

Por lo expuesto, a la Sección de lo Social del Tribunal de Instancia [NOTA DE REVISIÓN: No existe «Sala de lo Social del Tribunal de Instancia». Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

SUPLICA

Que, teniendo por presentado este escrito con sus copias y documentos adjuntos, se sirva admitir la demanda y, tras los trámites procesales oportunos, se dicte sentencia por la que, con estimación de la demanda, se declare al/ a la actor/a en situación de [COMPLETAR] derivada de [COMPLETAR], condenando al [COMPLETAR] a estar y pasar por dicha declaración y, en consecuencia, al pago de una pensión mensual vitalicia en la cuantía correspondiente a un porcentaje de [COMPLETAR] sobre una base reguladora mensual de [IMPORTE] € y con efectos desde el [FECHA].

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: Que a los efectos legalmente previstos interesa a esta parte que por ese Tribunal se requiera a la entidad gestora para que, de conformidad con los artículos 143 a 145 LRJS proceda a remitir [NOTA DE REVISIÓN: Erratas. La remisión del expediente (diez días) está en el art. 143.1 LRJS. Fuente: art. 143 LRJS (red. RDL 6/2023); LRJS (Ley 36/2011), BOE-A-2011-15936.] el expediente administrativo instruido.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO: Que a efectos de práctica de prueba interesa esta parte que en el acto del juicio se aporte por la demandada la siguiente documentación: [COMPLETAR].

[OPCIONAL — incluir si procede]

TERCER OTROSÍ DIGO: Que compareceré al acto del juicio asistido de letrado/a que me dirija y defienda, designando al efecto a D./Dña. [NOMBRE Y APELLIDOS], con domicilio profesional en [LOCALIDAD], de [COMPLETAR], con los siguientes datos de contacto: [COMPLETAR], a quien confiero poder tan amplio como en Derecho proceda a efectos de representación.

[OPCIONAL — incluir si procede]

CUARTO OTROSÍ DIGO: Que, de conformidad con lo previsto en el artículo 140.1 en relación al artículo 71, ambos LRJS, se acompaña con esta demanda copia de la reclamación previa interpuesta.

En [LUGAR], a [FECHA].

Firma de la parte actora

Firma de letrado/a

════════════════════════════════════════════════════════════════════════
