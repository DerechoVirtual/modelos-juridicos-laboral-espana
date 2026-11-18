---
name: suplicacion-procedimiento-acceso-reversion-modificacion-147
description: "Redacta el escrito «Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso» (formulario 147 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso

> Formulario 0147 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (6 veces)
- [ ] SSTS 25 de septiembre de 2018 (Recurso número 43/2018), y las que cita de 28 mayo 2013, recurso 5/20112; 3 julio 2013, recurso 88/2012; 25 marzo 2014, recurso 161/2013; y 2 marzo 2016, recuro 153/2015
- [ ] Nº (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, como del Iltre. Colegio de de»; «… sobre reversión del trabajo a distancia»; «…niéndose los autos a disposición de este»; «… probado cuarto, en el cual se omite que»; «…onal de la empresa obrante en los folios»; «…, que obra en folios»; «…do por los documentos obrantes en folios»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 195.1 de la Ley 36/2011
- art. 191 de la LRJS
- artículo 196.1 de la LRJS
- artículo 196.1 LRJS
- art. 193.b) de la LRJS
- artículo 193 b) de la LRJS
- art. 193.c) de la LJS
- artículo 5, 7 y 8 de la Ley 10/2021
- art. 1100 del Código Civil
- art. 5.3 de la Ley 10/2021
- art. 198 de la LRJS

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

### Formulario 0147 · Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso

- Año del modelo: 2021
- Revisión 17-11-2026: 24 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Digo
I. ANTECEDENTES
II. REQUISITOS PROCESALES
III. MOTIVOS DEL RECURSO
Suplico
Primer otrosí digo
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], como del Iltre. Colegio de de [COMPLETAR] y de D./Dña. [NOMBRE Y APELLIDOS], parte actora en la reclamación sobre reversión del trabajo a distancia [COMPLETAR] seguido a su instancia contra [ACTO O RESOLUCIÓN], ante el Tribunal de Instancia [SEDE] para ante la Sala de lo Social del Tribunal Superior de Justicia de [LOCALIDAD], comparezco y como mejor proceda en derecho DIGO:

Que mediante el presente escrito y dentro del plazo legalmente conferido por el art. 195.1 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LRJS), se INTERPONE RECURSO DE SUPLICACIÓN, anunciado en su día, contra la sentencia recaída en las actuaciones de referencia. A tal efecto se alegan los siguientes

I. ANTECEDENTES

PRIMERO.- Con fecha [FECHA] se dictó sentencia por ese Tribunal, desestimatoria de la demanda, que fue notificada a esta parte el día [FECHA]

SEGUNDO.- El día [FECHA] se anunció en tiempo y forma, recurso de suplicación frente a la misma, designándose al Letrado que suscribe para su interposición.

TERCERO.- Por diligencia de ordenación de fecha [FECHA] notificada a esta parte el día [FECHA], se admitió a trámite el recurso poniéndose los autos a disposición de este [COMPLETAR].

II. REQUISITOS PROCESALES

PRIMERO.- Recurribilidad. El artículo 138 bis, apartado 1.c), de la LRJS establece que cabe recurso de suplicación contra la sentencia dictada en el procedimiento de cuando se haya acumulado pretensión de resarcimiento de perjuicios que por su cuantía pudiera dar lugar a recurso de suplicación, siendo que en este proceso se solicitó una pretensión de resarcimiento por importe de 6.000 euros, la cual tiene acceso a la suplicación conforme a lo que dispone el art. 191 de la LRJS.

SEGUNDO.- Plazos. El recurso se interpone en el plazo de los diez días siguientes al de la notificación de la puesta a disposición, conforme al artículo 196.1 de la LRJS, una vez se ha tenido por anunciado en forma.

TERCERO.- Forma. El presente escrito de interposición cumple los requisitos del art. 196, apartados 2 y 3 de la LRJS, expresando con precisión y claridad los motivos en que se ampara, con cita de las normas del ordenamiento o de la jurisprudencia que se considere infringida, identificación de los documentos o pericias en que se basa la revisión de hechos declarados probados, y razonamiento de la pertinencia y fundamento de los motivos.

CUARTO.- Copias. Se presentan tantas copias como partes recurridas, de acuerdo a lo prevenido en el artículo 196.1 LRJS.

III. MOTIVOS DEL RECURSO

PRIMERO.- Al amparo del art. 193.b) de la LRJS, interesando la revisión del hecho probado cuarto, en el cual se omite que [COMPLETAR], sustituyendo el cuadro reflejado en el citado hecho cuarto en la sentencia.

El hecho probado cuarto de la sentencia es del siguiente tenor literal:

"Cuarto.- Que en el centro de trabajo del demandante hay tres trabajadores que realizaban teletrabajo en la fecha de solicitud de la reversión por el demandante”.

De acuerdo al resultado de la prueba practicada, se solicita su revisión y que sea sustituido por el siguiente:

"Cuarto.- Que en el centro de trabajo hay diez trabajadores que realizaban teletrabajo en la fecha de solicitud de la reversión por el demandante”.

La revisión del hecho probado se funda en el contenido del informe emitido por el Departamento de Personal de la empresa obrante en los folios [COMPLETAR], donde se relacionan los diez trabajadores de la empresa que estaban realizando el teletrabajo en la fecha en que se solicitó la reversión por el demandante, y en el informe de la Inspección de Trabajo, que recoge los puestos presenciales y por teletrabajo, con relación nominal de los trabajadores que están desempeñando cada uno de ellos en la fecha de la demanda, en el apartado segundo obrante en folio

Esta prueba documental evidencia de forma palmaria que existe un error en el hecho probado cuarto, puesto que son diez los trabajadores que realizaban el teletrabajo en la fecha de presentación de la demanda, con lo que es evidente que existía más de un 25% de la plantilla en esta situación, lo que hace totalmente injustificada la negativa a la reversión como se alegará posteriormente.

Para llegar a estas conclusiones fácticas no es necesario realizar ninguna operación de valoración o razonamiento, puesto que los documentos e informes médicos antes expresados no resultan desvirtuados por el resultado de los demás medios de prueba, ya que en ningún momento la empresa negó este hecho, oportunamente alegado en la demanda, ni solicitó prueba sobre este extremo.

Ello nos lleva a solicitar la revisión del hecho probado cuarto en este recurso de suplicación, en tanto que, según reiterada jurisprudencia, la previsión legal del artículo 193 b) de la LRJS permite solicitar la corrección de las eventuales contradicciones o errores de apreciación entre los hechos que se dan como probados y los que se deduzcan de las pruebas documentales practicadas, siempre que se señale de forma precisa y clara el hecho, y que no comporte valoraciones jurídicas [SSTS 25 de septiembre de 2018 (Recurso número 43/2018), y las que cita de 28 mayo 2013, recurso 5/20112; 3 julio 2013, recurso 88/2012; 25 marzo 2014, recurso 161/2013; y 2 marzo 2016, recuro 153/2015], como sucede en este caso, donde la errónea apreciación de la sentencia deriva de forma clara, directa y patente de los indicados documentos e informes obrantes en autos, ajustándose el resultado de la prueba al texto concreto propuesto del hecho cuarto, que contiene la narración fáctica acertada, lo cual tiene trascendencia para el fallo del proceso

Por tanto, solicitamos que se estime el motivo y se proceda a la modificación del hecho probado cuarto en el sentido anteriormente indicado.

SEGUNDO- Al amparo del art. 193.c) de la LJS, por infracción del artículo 5, 7 y 8 de la Ley 10/2021, de 9 de julio, de trabajo a distancia, y con el art. 1100 del Código Civil respecto de la indemnización por daños y perjuicios interesada en la demanda.

Tal como resulta de los hechos probados, los trabajadores en teletrabajo del centro eran diez, de manera que se superaban ampliamente los umbrales pactados en el acuerdo colectivo de empresa para que se produjera la reversión a elección del trabajador por falta de ocupación presencial de más del 25% de los puestos de trabajo del centro.

El art. 5.3 de la Ley 10/2021, de 9 de julio, de trabajo a distancia dispone que la decisión de trabajar a distancia desde una modalidad de trabajo presencial será reversible para la empresa y la persona trabajadora en los términos establecidos en la negociación colectiva o, en su defecto, en los fijados en el acuerdo de trabajo a distancia al que se refiere el artículo 7, en tanto que el art. 8.3 de la citada Ley 10/2021 establece que los convenios o acuerdos colectivos podrán establecer los mecanismos y criterios por los que la persona que desarrolla trabajo presencial puede pasar a trabajo a distancia o viceversa, estando en vigor el acuerdo colectivo de empresa de fecha [FECHA], que obra en folios [COMPLETAR], en el cual se pactó expresamente la reversión de la jornada, a elección de los trabajadores que realizaban teletrabajo a tiempo parcial, cuando el nivel de ocupación presencial del centro de trabajo fuese inferior al 75% o, lo que es lo mismo, que hubieran más de un 25% de puestos en teletrabajo, y únicamente condicionado al preaviso de treinta días naturales.

Por tanto, dándose los requisitos para el retorno a la modalidad presencial, la notificación del trabajador a la empresa de su voluntad de incorporarse a su puesto de trabajo de forma presencial en el centro de trabajo con efectos del día 1 de septiembre le daba derecho a la reversión a la modalidad presencial, de manera que la negativa de la empresa es totalmente injustificada, por lo que surge el derecho del demandante a ser resarcido por los daños y perjuicios sufridos, que fueron oportunamente reclamados en la demanda.

Tal como ha quedado acreditado, la decisión empresarial ha producido graves perjuicios económicos al demandante, quien ha tenido que rescindir el contrato de arrendamiento de vivienda que había concertado para residir en la localidad con motivo de la nueva reincorporación al puesto de trabajo, habiendo satisfecho la cantidad de 6.000 euros, en concepto de comisiones e indemnización por desistimiento, tal como se resultó acreditado por los documentos obrantes en folios [COMPLETAR] y así se refleja en el hecho probado octavo de la sentencia recurrida, solicitando asimismo que sea condenada la empresa al pago de dicha cantidad, la cual deberá incrementarse con los intereses legales correspondientes.

En consecuencia, se solicita que se estime el recurso de suplicación interpuesto, reconociendo el derecho del demandante a la reversión de su puesto de trabajo a la modalidad presencial en el centro de trabajo expresado y condenando a la empresa a que indemnice al actor en la cantidad de 6.000 euros por los daños y perjuicios sufridos, con más los intereses legales correspondientes.

En virtud de lo expuesto,

SUPLICO AL TRIBUNAL que admita este escrito, con sus copias y con la devolución de los autos, y en su virtud, tenga por interpuesto en tiempo y forma recurso de suplicación frente a la sentencia dictada por el Tribunal núm. [Nº] en el proceso núm. [Nº], dándole el trámite legal pertinente; suplicando, a su vez, a la Sala de lo Social del Tribunal Superior de Justicia de [LOCALIDAD] que en su día dicte sentencia por la que, con estimación del recurso, se dicte otra en su lugar por la que, estimando íntegramente el presente recurso, reconociendo el derecho del demandante a la reversión de su puesto de trabajo a la modalidad presencial en el centro de trabajo expresado y condenando a la empresa a que indemnice al actor en la cantidad de 6.000 euros por los daños y perjuicios sufridos, con más los intereses legales correspondientes.

PRIMER OTROSI DIGO que a efectos de notificaciones y de acuerdo con lo prevenido en el art. 198 de la LRJS, señalo el domicilio sito en [LOCALIDAD]

Es justicia que pido, en [LUGAR], a [DÍA] de [MES] de [AÑO].

(Firma)

════════════════════════════════════════════════════════════════════════
