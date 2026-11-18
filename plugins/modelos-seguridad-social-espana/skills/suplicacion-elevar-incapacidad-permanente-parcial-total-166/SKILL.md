---
name: suplicacion-elevar-incapacidad-permanente-parcial-total-166
description: "Redacta el escrito «Suplicación para elevar la incapacidad permanente de parcial a total» (formulario 166 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplicación para elevar la incapacidad permanente de parcial a total

> Formulario 0166 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Plazo de interposición: art. 195.1 LRJS (diez días); presentación: art. 196.1 (LO 1/2025, sin mención de copias). Grados de IP: DT 26.ª LGSS mientras no se desarrolle el art. 194.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] ACTO O RESOLUCIÓN
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (6 veces)
- [ ] SSTS 25 de septiembre de 2018 (Recurso número 43/2018), y las que cita de STS 28 mayo 2013, recurso 5/20112; STS 3 julio 2013, recurso 88/2012; STS 25 marzo 2014, recurso 161/2013; y STS 2 marzo 2016, recuro 153/2015
- [ ] Nº
- [ ] IMPORTE
- [ ] LUGAR
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…l servicio de Oftalmología de la Clínica»; «…, obrante en el folio»; «…rme médico de síntesis obrante en folios»; «… en el informe del EVI obrante en folios»; «… mi representado fue declarado en el año»; «… permanente parcial para su profesión de»; «…ala la adición de un nuevo hecho probado»; «…el desempeño de su profesión habitual de»; «…n en cuanto impedimentos reales, esto es»; «…incapacidad permanente parcial en el año»; «…en el ámbito de su profesión habitual de»; «… 137 de la LGSS (actual art. 194 TRLGSS)»; …

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 195.1 de la Ley 36/2011
- artículo 191.3.c) de la LJS
- artículo 195.1 de la LJS
- artículo 196.1 LJS
- art. 193.b) de la LJS
- artículo 193 b) de la LJS
- art. 193.c) de la LJS
- artículo 137 de la LGSS
- art. 194 de la LGSS
- art. 198 de la LJS
- Real Decreto Legislativo 8/2015

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

### Formulario 0166 · Suplicación para elevar la incapacidad permanente de parcial a total

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 2 puntualizaciones normativas añadidas en el texto; 32 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Avisos de la revisión: Plazo de interposición: art. 195.1 LRJS (diez días); presentación: art. 196.1 (LO 1/2025, sin mención de copias). Grados de IP: DT 26.ª LGSS mientras no se desarrolle el art. 194.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
Digo
ANTECEDENTES DE HECHO
REQUISITOS PROCESALES
MOTIVOS DE RECURSO
Suplico
Otrosí digo I
Firmas

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS], Letrado/a del Iltre. Colegio de Abogados de (o Graduado/a Social colegiado/a) y de D./D.ª [NOMBRE Y APELLIDOS], parte actora en el proceso ordinario núm. [Nº DE PROCEDIMIENTO] seguido a su instancia contra [ACTO O RESOLUCIÓN], ante el Tribunal de Instancia [SEDE] para ante la Sala de lo Social del Tribunal Superior de Justicia de [LOCALIDAD], comparezco y como mejor proceda en derecho DIGO:

Que mediante el presente escrito y dentro del plazo legalmente conferido por el art. 195.1 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LJS), se INTERPONE RECURSO DE SUPLICACIÓN, anunciado en su día, contra la sentencia recaída en las actuaciones de referencia. A tal efecto se alegan los siguientes

ANTECEDENTES DE HECHO

PRIMERO.- Con fecha [FECHA] se dictó sentencia por ese Tribunal, desestimatoria de la demanda, que fue notificada a esta parte el día [FECHA]

SEGUNDO.- El día [FECHA] se anunció en tiempo y forma, recurso de suplicación frente a la misma, designándose al Letrado que suscribe para su interposición.

TERCERO.- Por diligencia de ordenación de fecha [FECHA] notificada a esta parte el día [FECHA], se admitió a trámite el recurso poniéndose los autos a disposición de este Letrado

REQUISITOS PROCESALES

PRIMERO.- Recurribilidad. El artículo 191.3.c) de la LJS establece que son recurribles en suplicación las sentencias dictadas por los Tribunales de Instancia que versen sobre reconocimiento o denegación del derecho a obtener prestaciones de Seguridad Social, así como sobre el grado de incapacidad permanente aplicable.

SEGUNDO.- Plazos. El recurso se interpone en el plazo de los diez días siguientes al de la notificación de la puesta a disposición, conforme al artículo 195.1 de la LJS, una vez [NOTA DE REVISIÓN: El plazo de diez días para interponer la suplicación desde la puesta a disposición está en el art. 195.1; el 196.1 (red. LO 1/2025) solo dice que el escrito se presenta ante el órgano que dictó la sentencia. Fuente: arts. 195.1 y 196.1 LRJS (red. art. 24.10 LO 1/2025); LRJS (Ley 36/2011), BOE-A-2011-15936.] se ha tenido por anunciado en forma.

TERCERO.- Forma. El presente escrito de interposición cumple los requisitos del art. 196, apartados 2 y 3 de la LJS, expresando con precisión y claridad los motivos en que se ampara, con cita de las normas del ordenamiento o de la jurisprudencia que se considere infringida, identificación de los documentos o pericias en que se basa la revisión de hechos declarados probados, y razonamiento de la pertinencia y fundamento de los motivos.

CUARTO.- Copias. Se presentan tantas copias como partes recurridas, de acuerdo a lo prevenido en el artículo 196.1 LJS [NOTA DE REVISIÓN: El art. 196.1 vigente (LO 1/2025) ya no menciona copias: solo la presentación ante el órgano que dictó la resolución. Fuente: art. 196.1 LRJS (red. LO 1/2025); LRJS (Ley 36/2011), BOE-A-2011-15936.]

MOTIVOS DE RECURSO

PRIMERO.- Al amparo del art. 193.b) de la LJS, interesando la adición de un hecho probado sexto, con el siguiente tenor literal:

"Sexto.- En julio de 2020, se produjo en ojo derecho, desprendimiento vítreo posterior con anillo de Weiss Coroidosis miópica.”.

La adición del hecho probado se funda en los documentos e informes obrantes en autos, de los cuales se desprende que, junto la pérdida total de visión del ojo izquierdo y parcial del derecho expresada en los hechos probados, se produjo el desprendimiento del vítreo del ojo derecho en julio de 2020, según resulta claramente de los documentos e informes obrantes en autos.

Así, en el informe del servicio de Oftalmología de la Clínica [COMPLETAR], obrante en el folio [COMPLETAR] de las actuaciones se recoge este diagnóstico tras la visita del paciente el día 23 de julio de 2020. Esta misma patología consta en el informe médico de síntesis obrante en folios [COMPLETAR], donde literalmente se indica: “En julio de 2018: Refiere escotoma (mancha negra). OI: desprendimiento vítreo posterior con anillo de Weiss Coroidosis miópica”. Asimismo, esta limitación consta en el informe del EVI obrante en folios [COMPLETAR], al expresar las limitaciones derivadas del cuadro médico.

Esta prueba de documentos e informes evidencia de forma palmaria que los defectos de visión en el ojo izquierdo resultan agravados sustancialmente desde que mi representado fue declarado en el año [COMPLETAR] en situación de incapacidad permanente parcial para su profesión de [COMPLETAR], tanto por el aumento de la pérdida de agudeza visual en el ojo izquierdo que resultan reflejados en los hechos probados, como la descripción de las limitaciones derivadas del desprendimiento del vítreo que se solicita que se incluyan en los hechos probados.

Para llegar a estas conclusiones fácticas no es necesario realizar ninguna operación de valoración o razonamiento, puesto que los documentos e informes médicos antes expresados no resultan desvirtuados por el resultado de los demás medios de prueba. En efecto, todos los documentos e informes son coincidentes y, en consecuencia, tales limitaciones resultan expresadas en el dictamen del EVI, sin que exista prueba alguna que las desvirtúe mínimamente, por lo que la omisión de la patología resulta de un error de apreciación manifiesto con las pruebas documentales practicadas.

Ello nos lleva a instar de la Sala la adición de un nuevo hecho probado [COMPLETAR] sexto en este recurso de suplicación, en tanto que, según reiterada jurisprudencia, la previsión legal del artículo 193 b) de la LJS permite solicitar la corrección de las eventuales contradicciones o errores de apreciación entre los hechos que se dan como probados y los que se deduzcan de las pruebas documentales practicadas, siempre que se señale de forma precisa y clara el hecho, y que no comporte valoraciones jurídicas [SSTS 25 de septiembre de 2018 (Recurso número 43/2018), y las que cita de STS 28 mayo 2013, recurso 5/20112; STS 3 julio 2013, recurso 88/2012; STS 25 marzo 2014, recurso 161/2013; y STS 2 marzo 2016, recuro 153/2015], como sucede en este caso, donde la errónea apreciación de la sentencia deriva de forma clara, directa y patente de los indicados documentos e informes obrantes en autos, ajustándose el resultado de la prueba al texto concreto propuesto del nuevo hecho sexto, que contiene la narración fáctica acertada, lo cual tiene trascendencia para el fallo del proceso

Por tanto, solicitamos que se estime el motivo y se proceda a la adición de un hecho probado sexto en el sentido anteriormente indicado.

SEGUNDO- Al amparo del art. 193.c) de la LJS, por infracción del artículo 194.4, en la redacción aplicable conforme a la disposición transitoria vig [NOTA DE REVISIÓN: Correcto: la DT 26.ª LGSS sigue vigente (red. Ley 2/2025) y mantiene los grados clásicos de IP hasta el desarrollo reglamentario del art. 194. Fuente: art. 194 y DT 26.ª LGSS (red. Ley 2/2025, BOE-A-2025-8567).]ésimo sexta, en relación con el art. 200, todos ellos del Real Decreto Legislativo 8/2015, de 30 de octubre, por el que se aprueba el texto refundido de la Ley General de la Seguridad Social (LGSS), y de la doctrina del Tribunal Supremo y Tribunales Superiores de Justicia, por cuanto que las dolencias que padece el actor le hacen tributario del grado de invalidez permanente total que postula por revisión.

Tal como resulta de los hechos probados, la situación patológica en la que se encuentra mi representado ha de encuadrarse en el concepto de incapacidad permanente total para el desempeño de su profesión habitual de [COMPLETAR] que es definido por el precepto que se menciona como infringido, y por la doctrina jurisprudencial interpreta esta norma, como que la incapacidad permanente total para la profesión habitual, se caracteriza por un doble elemento: primero, por su carácter profesional lo que implica que, para su calificación jurídica, habrá de valorarse más que la índole y naturaleza de los padecimientos que presenta el trabajador, la limitación que ellos generen en cuanto impedimentos reales, esto es [COMPLETAR],susceptibles de determinación objetiva y suficiente para dejar imposibilitado a quien los padece, de iniciar y consumar las tareas propias de su oficio, por cuanto son esas limitaciones funcionales las que determinan la efectiva reducción de la capacidad de ganancia; y segundo, por su carácter de permanencia que implica la necesidad de estabilización de su estado residual en el sentido que las patologías o secuelas tengan un carácter previsiblemente definitivo dado que la posibilidad de recuperación clínica se estima médicamente como incierta o a largo plazo.

En este caso, según resulta de los hechos probados, desde que mi representado fue declarado en situación de incapacidad permanente parcial en el año [COMPLETAR] por pérdida de visión del ojo derecho, sus limitaciones se han venido agravando por la progresiva pérdida de visión en el ojo izquierdo, lo cual tiene especial incidencia en el ámbito de su profesión habitual de [COMPLETAR], teniendo tales limitaciones carácter definitivo e irreversible.

La jurisprudencia ha venido interpretando de forma uniforme que la pérdida de visión de un ojo es causa, en principio, de incapacidad permanente parcial, y para que sea causa de incapacidad permanente total es necesario que vaya unida a una reducción de la visión del otro, si bien, excepcionalmente, en algunas profesiones cabe que la pérdida de visión de un solo ojo dé lugar a la IPT, como, por ejemplo en el caso de un gruísta (Sentencia del Tribunal Supremo de 23 de diciembre de 2014).

A título orientativo, se viene acudiendo a la escala de Wecker -que calcula el porcentaje de pérdida de visión global- conforme a la cual se considera Incapacidad Permanente Total la comprendida entre el 37% y el 50%. Se trata de un criterio médico que establece unos porcentajes según la pérdida de visión, y según sea mayor o menor ese porcentaje se le asigna un grado de incapacidad permanente. Como indica la STSJ Madrid núm. 728/2020, de 9 julio, el funcionamiento es muy sencillo, teniendo en cuenta que un ojo sano equivale a 1 y una ceguera equivale a 0; se elige según cuál sea el ojo más sano y cual el peor un lado de la tabla y el número resultante es la pérdida de agudeza que tendremos que mirar si está dentro de alguna incapacidad. A tenor del Decreto de 22 junio 1956, por el que se aprueba el texto refundido de la Ley y el Reglamento de accidentes de trabajo, aplicable también con carácter orientativo según reiterada doctrina judicial, la pérdida de visión de un ojo, si queda reducida la del otro, en menos de un 50 por 100, equivale a una incapacidad permanente total (art. 38 E).

Pueden citarse en este sentido la STS de 4 de mayo de 2016, recordando la primera sentencia la doctrina tradicional de la Sala Cuarta -sentencias entre otras de 27 de enero y 23 de septiembre de 1986, 2 de abril de 1987 y 23 de enero de 1990 -, que ha venido señalando que los supuestos específicos de Incapacidad Permanente establecidos en los artículos 37 , 38 y 41 del Reglamento de Accidentes de Trabajo de 22 de junio de 1956, aunque ya no están vigentes, se consideran como orientadores é indicativos para aplicar lo dispuesto en el artículo 137 de la LGSS (actual art. 194 TRLGSS) [COMPLETAR], en el que se definen los distintos grados de incapacidad permanente, añadiendo que la disminución de rendimiento que caracteriza la incapacidad permanente debe valorarse no sólo atendiendo a lo que puede rendir objetivamente el trabajador afectado, sino atendiendo también a la peligrosidad o penosidad que comporta.

Asimismo, en relación a la incapacidad permanente en grado de total para su profesión habitual, la Sentencia del Tribunal Supremo de 21 de marzo de 2005 (recurso 1211/2004 ), que "aplicando como orientación los parámetros contenidos en los hoy derogados artículos 37 y 38 del antiguo Reglamento de Accidentes de Trabajo de 22 de junio de 1.956 , con arreglo a los que la pérdida de la visión completa de un ojo y de menos del 50% en el otro determinaba el reconocimiento de la incapacidad permanente total (art. 38 e). La incapacidad parcial (art. 37 b) se correspondía con la pérdida de la visión completa de un ojo, subsistiendo la del otro sin limitaciones. Como se ha dicho antes, el trabajador demandante tiene perdida la visión de un ojo y limitado el otro en menos del 50%, lo que se correspondía con la situación descrita en la referida norma, hoy traída a colación como elemento orientador exclusivamente, a falta de otros instrumentos legales que regulen la materia”.

De ello resulta que mi representado se encuentra en una situación de incapacidad permanente total, puesto que, tras la pérdida de visión del ojo derecho que determinó la situación de incapacidad parcial, ha visto agravado su estado, con pérdida de visión del ojo izquierdo superior al 50% y las limitaciones derivadas del desprendimiento del vitrio que le impiden el desarrollo de su profesión, donde resulta imprescindible el uso de la vista, pues son tareas propias de misma la lectura, utilización de dispositivos electrónicos, y uso de pantallas, por lo que está en una situación de incapacidad permanente en grado de total para el desarrollo de su profesión. Tal como se refleja en los hechos probados, mi representado tiene ceguera total en el ojo izquierdo, mientras que en el derecho, con corrección, su visión es del 45%. Con estos parámetros en escala de Wecker el actor obtendría una puntuación de 50, dentro de la banda entre el 37-50% equivalente a la incapacidad permanente total. Si a eso unimos tiene limitaciones para uso de ordenador y tecnologías visuales, conducir y coger pesos, requerimientos que están presentes en su profesión, existe una situación clara de incapacidad permanente total.

Por tanto, la situación actual del trabajador le incapacita para su profesión habitual y por lo tanto se encuentra en el supuesto del art. 194 de la LGSS y resulta tributario de una invalidez permanente en el grado de total con los derechos inherentes a tal declaración, y a tal efecto solicitamos la estimación del recurso, con reconocimiento de dicha situación jurídica de mi representado con los efectos solicitados en nuestro escrito de demanda que no han sido controvertidos de contrario

En virtud de lo expuesto,

SUPLICO AL TRIBUNAL que admita este escrito, con sus copias y con la devolución de los autos, y en su virtud, tenga por interpuesto en tiempo y forma recurso de suplicación frente a la sentencia dictada por el Tribunal [COMPLETAR] en el proceso núm. [Nº], dándole el trámite legal pertinente; suplicando, a su vez, a la Sala de lo Social del Tribunal Superior de Justicia de [LOCALIDAD] que en su día dicte sentencia por la que, con estimación del recurso, se dicte otra en su lugar por la que, estimando íntegramente el presente recurso, reconociendo la situación de mi representado de incapacidad permanente total para su profesión habitual de [COMPLETAR] con derecho a una pensión del [COMPLETAR] % de su base reguladora de [IMPORTE] euros mes y efectos desde el día siguiente al cese en el trabajo, todo ello con las mejoras, revalorizaciones y topes legales procedentes, condenando al INSS y TGSS a estar y pasar por ello.

PRIMER OTROSI DIGO que a efectos de notificaciones y de acuerdo con lo prevenido en el art. 198 de la LJS, señalo el domicilio sito en [LOCALIDAD]

Es justicia que pido, en [LUGAR], a [FECHA].

(Firma abogado o graduado social colegiado)

════════════════════════════════════════════════════════════════════════
