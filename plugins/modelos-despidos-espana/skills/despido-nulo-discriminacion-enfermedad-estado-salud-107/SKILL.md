---
name: despido-nulo-discriminacion-enfermedad-estado-salud-107
description: "Redacta el escrito «Despido nulo por discriminación por enfermedad o estado de salud: demanda» (formulario 107 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido nulo por discriminación por enfermedad o estado de salud: demanda

> Formulario 0107 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Nulidad objetiva: los arts. 53.4.b) y 55.5.b) ET (redacción LO 1/2025, DF 26.ª, en vigor el 3-4-2025) incluyen permisos del 37.3.b), 4, 5 y 6, adaptaciones del 34.8 y excedencia del 46.3; el art. 55.5.a) incluye el permiso parental del 48 bis.
- Ley 15/2022: carga de la prueba del art. 30 y posible informe de organismos de igualdad (art. 30.2); la Autoridad Independiente para la Igualdad de Trato tiene Estatuto aprobado por RD 606/2026 (BOE-A-2026-16172).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (6 veces)
- [ ] IMPORTE (3 veces)
- [ ] Nº DE DOCUMENTO
- [ ] COLEGIO
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de»; «…MANDA por despido nulo contra la empresa»; «…para la empresa»; «…suscribiendo un contrato temporal»; «…, con la categoría/grupo de»; «…rnada completa (acompaño como documentos»; «…en el servicio de urgencias del Hospital»; «…(acompaño como documentos»; «… dicho acto, acompañando como documentos»; «…y»; «…amplias que en derecho hubiere lugar, al»; «…del Ilustre Colegio de [COLEGIO] de»; …

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO que se acompaña en anexo relación de documentos, debidamente foliados y con índice electrón…
- SEGUNDO OTROSÍ DIGO.– Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al ampar…
- TERCER OTROSÍ DIGO.– Que a los efectos de este procedimiento se designan para la representación y defensa de e…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 30 de la Ley 15/2022
- art. 53.4 y 55.5 del TRET
- arts. 2 y 9 de la Ley 15/2022
- art. 183 de la LJS
- art. 27 de la Ley 15/2022
- artículos 1, 2 y 3 de la Ley 36/2011
- artículos 120 a 123 de la LJS
- artículo 102 LJS
- artículo 24.1 de la CE
- artículo 121.1 de la LJS
- artículos 53, 55 y 59 ET
- artículos 53.4 y 55.5 ET
- arts. 2, 9, 26, 28 y 30 de la Ley 15/2022
- artículo 75 LRJS

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

### Formulario 0107 · Despido nulo por discriminación por enfermedad o estado de salud: demanda

- Año del modelo: 2023
- Revisión 17-11-2026: 2 rangos de artículos despegados («25 a31» → «25 a 31»); 3 párrafos opcionales señalados; 35 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Nulidad objetiva: los arts. 53.4.b) y 55.5.b) ET (redacción LO 1/2025, DF 26.ª, en vigor el 3-4-2025) incluyen permisos del 37.3.b), 4, 5 y 6, adaptaciones del 34.8 y excedencia del 46.3; el art. 55.5.a) incluye el permiso parental del 48 bis. · Ley 15/2022: carga de la prueba del art. 30 y posible informe de organismos de igualdad (art. 30.2); la Autoridad Independiente para la Igualdad de Trato tiene Estatuto aprobado por RD 606/2026 (BOE-A-2026-16172).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

La Ley 15/2022, de 12 de julio, establece la prohibición de discriminar al trabajador por motivos diversos, entre ellos el de enfermedad. Por ello los despidos estando de baja médica podrán ser calificados como discriminatorios, y por tanto nulos de pleno derecho.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], con domicilio en [LOCALIDAD], ante la Sección de lo Social del Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que por medio del presente escrito interpongo ante la Sección de lo Social del Tribunal de Instancia plaza núm. [Nº] de [COMPLETAR] DEMANDA por despido nulo contra la empresa [COMPLETAR], con domicilio en [LOCALIDAD], la cual deberá tramitarse por la modalidad procesal de los artículos 120 y siguientes de la Ley 36/2011, y ello con fundamento en los siguientes

HECHOS

Primero.– La persona demandante comenzó a prestar servicios el día [FECHA] para la empresa [COMPLETAR] suscribiendo un contrato temporal [COMPLETAR], con la categoría/grupo de [COMPLETAR], con un salario mensual bruto con prorrata de pagas extras de [IMPORTE] euros, a jornada completa (acompaño como documentos [COMPLETAR] contrato de trabajo y nóminas).

La demandante no ostenta representación legal ni sindical de los trabajadores.

Segundo.– En fecha [FECHA], la persona demandante sufrió accidente de trabajo que le produjo contusión lumbar y esguince de rodilla, siendo atendido en el servicio de urgencias del Hospital [COMPLETAR] el mismo día, iniciando el proceso de baja por IT.

Al cabo de cinco días es dado de alta médica, si bien recae nuevamente en la patología dos días después de incorporarse al trabajo, expidiéndose nueva baja por el SAS con el diagnóstico de esguince de rodilla, iniciando nuevo proceso de baja por IT el día [FECHA] (acompaño como documentos [COMPLETAR] informes médicos y partes de baja y alta).

Tercero.– Tras iniciar este nuevo proceso de IT; la empresa ya no tramitó la baja, remitiendo al día siguiente, en fecha [FECHA], carta de despido por falta de rendimiento, requiriéndole para pasar por las oficinas al cobro de la liquidación y finiquito del contrato de trabajo (acompaño como documento número [Nº DE DOCUMENTO] carta de despido)

Cuarto.– Se ejercita la acción de nulidad de despido por discriminación por razón de discapacidad, enfermedad y estado de salud, puesto que la empresa ha procedido a despedir a la persona trabajadora tan pronto recae de nuevo en el proceso de IT, como consecuencia del accidente de trabajo, existiendo una evidente conexión temporal y causal entre el despido con la situación de enfermedad del trabajador/a, sin que la empresa procediera ni tan siquiera a tramitar la baja.

No hay ninguna razón para que despidiera al trabajador/a en plena campaña y con contrato vigente hasta finales de septiembre, por lo que es evidente que el despido se produce como consecuencia de la situación de enfermedad de la demandante y en relación exclusivamente con ella.

En cualquier caso, y de conformidad al art. 30 de la Ley 15/2022, de 12 julio corresponde a la empresa la carga de desvirtuar los sólidos indicios de la situación de discriminación descrita.

Quinto.– La pretensión de nulidad se sostiene en aplicación de lo dispuesto en el art. 53.4 y 55.5 del TRET, que se ejercita en el plazo legal de veinte días, en relación con los arts. 2 y 9 de la Ley 15/2022, de 12 julio, que establece como una de las causas de discriminación prohibida, la "enfermedad o condición de salud", sin más adjetivos, como causa de discriminación, existiendo en este caso un claro elemento segregacionista, ya que la persona demandante se ha visto injustamente despedida y, por consiguiente, "segregada" en su empleo laboral, por el solo hecho de estar enfermo y ejercer derechos tal elementales como el de la protección a la salud y el acceso a la prestación sanitaria.

Los tribunales han venido declarando que la prohibición de discriminación contenida en la Directiva comunitaria 2000/78 para los casos de discapacidad, determina la nulidad del despido, ampliándose este espacio por la Ley 15/2022, donde la nulidad no requiere de una existente o previsible discapacidad, sino que también queda protegido el trabajador ante actuaciones discriminatorias motivadas por la simple enfermedad.

Sexto.– En fecha [FECHA] se interpuso por esta parte solicitud de conciliación sin avenencia, al no comparecer la empleadora demandada a dicho acto, acompañando como documentos [COMPLETAR] y [COMPLETAR] copia de la solicitud y certificación del acta.

Séptimo.– En base a lo expuesto, debe declarase la NULIDAD del despido, con todas las consecuencias legales inherentes, solicitándose una indemnización de [IMPORTE] euros en concepto de daño moral, por aplicación del art. 183 de la LJS y art. 27 de la Ley 15/2022, de 12 julio la cual se fija tomando como referencia el criterio orientador de las sanciones pecuniarias previstas por la Ley de infracciones y sanciones del orden para las infracciones producidas en el caso, el cual ha sido reiteradamente admitido por la jurisprudencia expresada, entre otras muchas, en las SSTS de 23 de febrero de 2022 (RCUD 4322/2019)) y de 9 de marzo de 2022 (RCUD 2269/2019), debiendo condenarse a la demandada a todas las responsabilidades que se deriven de la presente acción legal.

A los anteriores hechos les son aplicables los siguientes

FUNDAMENTOS DE DERECHO

Primero.– Jurisdicción y competencia

El Tribunal ante el cual se interpone la presente demanda tiene jurisdicción bastante y competencias territorial, funcional y objetiva o material para el conocimiento y decisión de la litis, según lo que disponen, los artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica del Poder Judicial en relación con los artículos 1, 2 y 3 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LJS), quedando configuradas la competencia objetiva y territorial en los artículos 6 y 10 de la citada LJS.

Segundo.– Legitimación

Según lo previsto en el artículo 1, puntos 1 y 2, de la LJS, esta parte tiene legitimación activa para interponer la presente demanda, del mismo modo que la tiene, en su calidad de pasiva, la parte demandada.

Tercero.– Procedimiento

Dada la naturaleza de la acción emprendida por esta parte y a tenor de la pretensión que se postula, es procedente que la presente litis se encauce por las reglas que, al efecto, determinan los artículos 120 a 123 de la LJS, todo ello con la supletoriedad de las normas previstas en los artículos 103 a 113 de la misma LJS, tal y como se infiere de lo establecido en el artículo 120 antedicho y, en su caso, atendiendo a las normas subsidiarias a que aluden los artículos 80 y siguientes de la tan reiterada Ley, por así indicarlo con carácter general su artículo 102 LJS.

Cuarto.– Plazo

En cuanto a la acción, ésta dimana del derecho que tiene la parte actora, desconocido por la demandada y, por tanto, recubierto del interés legítimo a que se refiere el artículo 24.1 de la CE, habiendo reaccionado frente a la decisión extintiva dentro del plazo de caducidad de veinte días a que se refiere el artículo 121.1 de la LJS, en relación con los artículos 53, 55 y 59 ET.

Quinto.– Fondo del asunto

Son de aplicación los artículos 53.4 y 55.5 ET, en relación con los arts. 2, 9, 26, 28 y 30 de la Ley 15/2022, de la Ley 15/2022, de 12 de julio, integral para la igualdad de trato y la no discriminación. El art. 1 de la citada Ley establece: «Se reconoce el derecho de toda persona a la igualdad de trato y no discriminación con independencia de su nacionalidad, de si son menores o mayores de edad o de si disfrutan o no de residencia legal. Nadie podrá ser discriminado por razón de nacimiento, origen racial o étnico, sexo, religión, convicción u opinión, edad, discapacidad, orientación o identidad sexual, expresión de género, enfermedad o condición de salud (...)». Por su parte, el art. 9 de la misma Ley 15/2022, de 12 julio dispone: «No podrán establecerse limitaciones, segregaciones o exclusiones por razón de las causas previstas en esta ley para el acceso al empleo por cuenta ajena, público o privado, incluidos los criterios de selección, en la formación para el empleo, en la promoción profesional, en la retribución, en la jornada y demás condiciones de trabajo, así como en la suspensión, el despido u otras causas de extinción del contrato de trabajo».

Sexto.– Indemnización por daño moral

El art. 27 de la Ley 15/2022, de 12 julio establece: "la persona física o jurídica que cause discriminación por alguno de los motivos previstos en el apartado 1 del artículo 2 de esta ley reparará el daño causado proporcionando una indemnización y restituyendo a la víctima a la situación anterior al incidente discriminatorio, cuando sea posible. Acreditada la discriminación se presumirá la existencia de daño moral, que se valorará atendiendo a las circunstancias del caso, a la concurrencia o interacción de varias causas de discriminación previstas en la ley y a la gravedad de la lesión efectivamente producida, para lo que se tendrá en cuenta, en su caso, la difusión o audiencia del medio a través del que se haya producido".

Séptimo.– Costas y multa

El artículo 97.3 de la Ley reguladora de la jurisdicción social establece que la sentencia, motivadamente, podrá imponer al litigante que obró de mala fe o con temeridad, así como al que no acudió al acto de conciliación injustificadamente ante el servicio administrativo correspondiente o a mediación, de acuerdo con lo establecido en el artículo 83.3, una sanción pecuniaria dentro de los límites que se fijan en el apartado 4 del artículo 75 LRJS. En tales casos, y cuando el condenado fuera el empresario, deberá abonar también los honorarios de los abogados y graduados sociales de la parte contraria que hubieren intervenido, hasta el límite de seiscientos euros, por lo que procede la imposición de costas a la parte demandada, así como la de una multa en su cuantía máxima, en el caso de que se opusiere a las legítimas pretensiones que en esta demanda se actúan.

Por todo lo expuesto,

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA SUPLICO: Que, teniendo por presentada esta demanda, con las copias y documentos que se adjuntan a la misma, se sirva admitirla y, previos los trámites legales oportunos dicte Sentencia por la que se declare la NULIDAD del despido de D./Dña. [NOMBRE Y APELLIDOS] con efectos del día [FECHA] con todas las consecuencias legales inherentes, condenando a la demandada a estar y pasar por dicha declaración a todos los efectos y a todas las responsabilidades económicas que se deriven de la presente acción legal, debiendo indemnizar a la demandante en la cantidad de [IMPORTE] euros en concepto de daño moral.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO que se acompaña en anexo relación de documentos, debidamente foliados y con índice electrónico, para su debida localización y consulta.

Por lo que, SUPLICO AL TRIBUNAL tenga hecha esta manifestación a los efectos oportunos y por aportados los documentos relacionados en el anexo.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO.– Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el art. 90.3 de la Ley reguladora de la jurisdicción social, interesa al derecho de esta parte que se practiquen las diligencias de citación y requerimiento de la siguiente prueba que esta parte pretende proponer en el juicio:

– INTERROGATORIO de la demandada en el acto de juicio, interesa se acuerde citar y se cite a la empleadora, a fin de que comparezcan al acto del juicio que se señale para responder las preguntas que se le formulen, bajo apercibimiento de tenerse por admitidos tácitamente los hechos para el caso de incomparecencia.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA SUPLICA: Admita las diligencias de citación y requerimiento para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

[OPCIONAL — incluir si procede]

TERCER OTROSÍ DIGO.– Que a los efectos de este procedimiento se designan para la representación y defensa de esta parte, con las facultades más amplias que en derecho hubiere lugar, al [COMPLETAR] del Ilustre Colegio de [COLEGIO] de [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS], quien suscribe conmigo esta demanda a todos los efectos prevenidos en el artículo 80.1.e) de la Ley reguladora de la jurisdicción social, designándose el domicilio de dichos profesionales a efectos de notificaciones y citaciones, sito en [LOCALIDAD] de [COMPLETAR], con los siguientes datos de contactos [COMPLETAR].

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA SUPLICO que tenga por hechas las anteriores manifestaciones a los efectos oportunos.

Es Justicia que respetuosamente solicito en [COMPLETAR]

Demandante	Letrado(a) / Procurador(a) / Graduado(a) social colegiado(a)

Fdo. D./Dña. [NOMBRE Y APELLIDOS]: 	Fdo. D./Dña. [NOMBRE Y APELLIDOS]:

════════════════════════════════════════════════════════════════════════
