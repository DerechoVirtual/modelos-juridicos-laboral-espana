---
name: demanda-complemento-maternidad-pension-jubilacion-143
description: "Redacta el escrito «Demanda por complemento de maternidad en pensión de jubilación contributiva» (formulario 143 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda por complemento de maternidad en pensión de jubilación contributiva

> Formulario 0143 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- El complemento de maternidad por aportación demográfica solo cabe para pensiones causadas antes del 4-2-2021; después, el complemento de brecha de género del art. 60 vigente (DT 33.ª LGSS). El suplico mezcla ambos: unificar.
- «Sala de lo Social del Tribunal de Instancia» → Sección de lo Social.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (12 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en General de la Seguridad Social con el»; «…, en la actividad de»; «…ridad Social, con una cuantía inicial de»; «… tenido cuatro hijos nacidos en los años»; «…a presente demanda asistiré dirigido por»; «…respondiente expediente tramitado con el»; «…da laboral del otro progenitor. – (....)»; «…. Fdo. D./Dña. [NOMBRE Y APELLIDOS]:»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicció…
- SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, intere…

## Correcciones de la revisión (4)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 60 LGSS
- artículos 2.o), 6 y 10 de la Ley 36/2011
- art. 80 de la LJS
- arts. 71 y 140 de la LJS
- artículo 60 LGSS

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

### Formulario 0143 · Demanda por complemento de maternidad en pensión de jubilación contributiva

- Año del modelo: 2022
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 2 puntualizaciones normativas añadidas en el texto; 2 párrafos opcionales señalados; 27 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: El complemento de maternidad por aportación demográfica solo cabe para pensiones causadas antes del 4-2-2021; después, el complemento de brecha de género del art. 60 vigente (DT 33.ª LGSS). El suplico mezcla ambos: unificar. · «Sala de lo Social del Tribunal de Instancia» → Sección de lo Social.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Hechos
Fundamentos de derecho
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provista de D.N.I. nº [NÚMERO], con domicilio en [LOCALIDAD], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA EN RECLAMACIÓN DE COMPLEMENTO DE MATERNIDAD DE PENSIÓN CONTRIBUTIVA DE JUBILACIÓN, amparada en el art. 60 del TRLGSS en la redacción aplicable dada por Real Decreto legislativo 8/2015 [NOTA DE REVISIÓN: El complemento de maternidad por aportación demográfica (art. 60 original) solo alcanza a pensiones causadas antes del 4-2-2021; desde entonces el art. 60 es el complemento para la reducción de la brecha de género y la DT 33.ª mantiene los complementos ya reconocidos. Fuente: art. 60 LGSS (red. RDL 2/2023) y DT 33.ª (red. RDL 3/2021, BOE-A-2021-1529); LGSS (RDLeg 8/2015), BOE-A-2015-11724.], de 30 de octubre., contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], y TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], que deberá tramitarse por la modalidad procesal de prestaciones de Seguridad Social, a fin de que sean condenadas en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

Hechos

Primero.– El demandante nació el día [FECHA], estando afiliado y en alta en el Régimen General de la Seguridad Social con el [COMPLETAR], en la actividad de [COMPLETAR], teniendo reconocida una pensión contributiva de jubilación desde el día [FECHA] por el Régimen General de la Seguridad Social, con una cuantía inicial de [COMPLETAR] mensuales más revalorizaciones.

Segundo.– En fecha [FECHA], el actor solicitó el reconocimiento del derecho al complemento por maternidad por aportación demográfica con efectos desde el día [FECHA], de conformidad a lo dispuesto en el art. 60 del TRLGSS en su redacción anterior y disposición transitoria trigésima tercera del citado Texto Refundido, al haber tenido cuatro hijos nacidos en los años [COMPLETAR], respectivamente, por lo que en fecha [FECHA], solicitó el reconocimiento del derecho al complemento por maternidad con efectos desde el día [FECHA], lo cual le fue denegado por resolución del INSS de fecha [FECHA].

Tercero.– Tal como se ha indicado y habida cuenta que se daban todos los requisitos para el complemento de maternidad y no se daba ninguna de las incompatibilidades previstas en la disposición transitoria 33 del TRLGSS, solicitó el complemento de maternidad por aportación demográfica, el cual le fue denegado por la resolución de fecha [FECHA] por entender que el art. 60 del TRLGSS; en la redacción aplicable, solo contempla un complemento por maternidad a las mujeres que habiendo tenido dos o más hijos biológicos o adoptados, y que en todo caso la fecha de reconocimiento no podía ser anterior a la fecha de publicación en el Diario Oficial de la Unión Europea (DOUE) de la STJUE de 12 de diciembre de 2019 (asunto C-450/18 (TJCE 2019, 281)), que se publicó en el DOUE el 17 de febrero de 2020.

Cuarto.– Disconforme con dicha resolución, el demandante interpuso reclamación previa alegando, tal como se recoge en las SSTS del Pleno de la Sala Cuarta del Tribunal Supremo núm. 160/2022 de 17 febrero y núm. 163/2022 de 17 febrero, el contenido del artículo 60 TRLGSS, que, en su redacción original excluyó a los padres varones pensionistas de la percepción del complemento, se ha declarado constitutivo de una discriminación directa por razón de sexo y contrario a la Directiva 79/7/CEE del Consejo, de 19 de diciembre de 1978, relativa a la aplicación progresiva del principio de igualdad de trato entre hombres y mujeres en materia de seguridad social, que estableció que ese principio de igualdad de trato supone la ausencia de toda discriminación por razón de sexo, ya sea directa o indirectamente, así como la indicación a los Estados miembros de que adopten las medidas necesarias con el fin de suprimir las disposiciones legales, reglamentarias y administrativas contrarias al principio de igualdad de trato, tal como se expresa en la STJUE de 12 de diciembre de 2019 (asunto C-450/18 (TJCE 2019, 281).

El Pleno de la Sala Cuarta, en las SSTS de 17 de febrero de 2022 antes citadas, de manera consecuente, expresa que la exégesis de los órganos judiciales nacionales ha de ser compatible con los objetivos perseguidos por la Directiva, lo que conduce a ubicar el momento de producción de las consecuencias jurídicas anudadas a la prestación debatida al nacimiento mismo de la norma y consecuente acaecimiento del hecho causante -efectos ex tunc-, dado que debía ser entendida y aplicada en el sentido desarrollado por el TJUE, que ninguna limitación temporal dispuso en su pronunciamiento, por lo que, si se cumplen los requisitos exigidos por la redacción original del art. 60 LGSS para los hombres, se les tiene que reconocer el complemento en las mismas condiciones que a las mujeres.

Tal como se expresaba en la reclamación administrativa previa, de acuerdo a la interpretación jurisprudencial, el demandante tiene derecho al incremento de su pensión por el complemento de maternidad conforme a la redacción anterior del art. 60 del TRLGSS, según la escala recogida en el apartado 1 del precepto, desde la fecha de entrada en vigor de la norma, por ser de aplicación directa, con efectos ex tunc, las disposiciones del derecho comunitario en los Estados miembros, tal como se afirma en las citadas SSTS de 17 de febrero de 2022, y sin que exista ninguna causa de incompatibilidad de las previstas en la disposición transitoria trigésima tercera del TRLGSS.

Quinto.– La citada reclamación previa planteada ante el INSS, ha sido desestimada por resolución expresa de fecha [FECHA], notificada en fecha [FECHA], la cual se acompaña como documento número 1.

A los anteriores hechos son de aplicación los siguientes

Fundamentos de derecho

Primero.– Es competente el Tribunal de Instancia, tanto por razón de la condición de los litigantes, como por la materia y territorio, de conformidad a lo que determinan los artículos 2.o), 6 y 10 de la Ley 36/2011 [NOTA DE REVISIÓN: El art. 1 LRJS no tiene apartados; las prestaciones de Seguridad Social son la letra o) del art. 2 (la «b)» venía de la LPL de 1995). Fuente: arts. 1, 2.o) y 10.2.a) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], Reguladora de la Jurisdicción Social (LJS).

Segundo.– Se han hecho constar en la presente demanda todos los requisitos formales exigidos por el art. 80 de la LJS, debiendo tramitarse el procedimiento por la modalidad procesal de prestaciones de Seguridad Social.

Tercero.– Los arts. 71 y 140 de la LJS, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad gestora codemandada.

Cuarto.– En cuanto al fondo del asunto, la SSTS del Pleno de la Sala Cuarta del Tribunal Supremo núm. 160/2022 de 17 febrero y núm. 163/2022 de 17 febrero, establecen que el contenido del artículo 60 LGSS, que, en su redacción original excluyó a los padres varones pensionistas de la percepción del complemento, se ha declarado constitutivo de una discriminación directa por razón de sexo y contrario a la Directiva 79/7/CEE del Consejo, de 19 de diciembre de 1978, y, de manera consecuente, la exégesis de los órganos judiciales nacionales ha de ser compatible con los objetivos perseguidos por la Directiva, lo que conduce a ubicar el momento de producción de las consecuencias jurídicas anudadas a la prestación debatida al nacimiento mismo de la norma y consecuente acaecimiento del hecho causante -efectos ex tunc-, dado que debía ser entendida y aplicada en el sentido desarrollado por el TJUE, que ninguna limitación temporal dispuso en su pronunciamiento, por lo que, si se cumplen los requisitos exigidos por la redacción original del art. 60 LGSS para los hombres, se les tiene que reconocer el complemento en las mismas condiciones que a las mujeres.

Quinto.– En cuanto a los efectos, es de aplicación el art. 60 del TRLGSS [NOTA DE REVISIÓN (comprobar): Los efectos del reconocimiento se rigen por el art. 53.1 LGSS (tres meses de retroactividad), sin perjuicio de la doctrina del TS sobre efectos que invoca el formulario. Fuente: art. 53.1 LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.], debiendo reconocerse el incremento de pensión, así como el abono de las cantidades atrasadas con más los intereses legales correspondientes.

Por lo expuesto,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA [NOTA DE REVISIÓN: No existe «Sala de lo Social del Tribunal de Instancia»: el Tribunal de Instancia se organiza en Secciones; «Sala de lo Social» solo en TSJ, AN y TS. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76; arts. 59, 67 y 75 LOPJ.] que, teniendo por presentada esta demanda en reclamación de complemento de pensión de jubilación para la reducción de la brecha de género, contra el INSS y TGSS, con sus respectivas copias y documentos que se adjuntan, se sirva admitirla, darle el turno que corresponda, citar a las partes para la celebración del acto del juicio y, en definitiva, dictar sentencia por la que estimando la presente demanda se reconozca el derecho del demandante a la percepción del complemento de maternidad por aportación demográfica en la pensión contributiva de jubilación por la cuantía establecida normativamente de [IMPORTE] euros mensuales desde el día [FECHA], condenando a las demandadas al abono de las cantidades atrasadas con más los intereses legales correspondientes.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por [COMPLETAR] en ejercicio, designando a D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], el cual se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes

[OPCIONAL — incluir si procede]

SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, interesa al derecho de esta parte la verificación de los siguientes medios de prueba:

– DOCUMENTAL consistente en que se remita el correspondiente expediente tramitado con el [COMPLETAR] referente a la solicitud de complemento de pensión contributiva de maternidad por aportación demográfica del demandante.
– MÁS DOCUMENTAL, consistente en que por el INSS se remite la hoja de vida laboral del otro progenitor.
– (....) [COMPLETAR].

SUPLICO tenga por propuestos los medios de prueba solicitados y acuerde lo conducente para su práctica.

Por ser Justicia que pido para principal y otrosíes,

en [LUGAR], a [FECHA].

Fdo. D./Dña. [NOMBRE Y APELLIDOS]: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
