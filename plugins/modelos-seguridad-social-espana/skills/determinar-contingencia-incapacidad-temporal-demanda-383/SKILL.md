---
name: determinar-contingencia-incapacidad-temporal-demanda-383
description: "Redacta el escrito «Determinar la contingencia de la incapacidad temporal: demanda» (formulario 383 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Determinar la contingencia de la incapacidad temporal: demanda

> Formulario 0383 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- La resolución del INSS en determinación de contingencia puede valer como resolución de la reclamación previa (art. 6.8 RD 1430/2009); el informe de la ITSS lo pide el órgano judicial al admitir la demanda (art. 142.2 LRJS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (6 veces)
- [ ] FECHA (9 veces)
- [ ] IMPORTE
- [ ] arts. 2.o), 6 y 10 Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social
- [ ] CORREO ELECTRÓNICO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, la empresa»; «…tua colaboradora con la Seguridad Social»; «…ntando la categoría/grupo profesional de»; «…en General de la Seguridad Social con el»; «…r lo que fue dado de baja por enfermedad»; «…por el/la trabajador/a es enfermedad»; «…NSS declarando el carácter de enfermedad»; «…(acompaño como documentos»; «…a presente demanda asistiré dirigido por»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 6 del Real Decreto 1430/2009
- art. 3 del Real Decreto 625/2014
- art. 156.2 LGSS
- art. 156.3 LGSS
- arts. 2.o), 6 y 10 Ley 36/2011
- arts. 71 y 140.1 de la Ley 36/2011
- artículo 156.2 de la LGSS
- artículo 157 LGSS
- art. 142.2 LRJS

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

### Formulario 0383 · Determinar la contingencia de la incapacidad temporal: demanda

- Año del modelo: 2015
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 30 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: La resolución del INSS en determinación de contingencia puede valer como resolución de la reclamación previa (art. 6.8 RD 1430/2009); el informe de la ITSS lo pide el órgano judicial al admitir la demanda (art. 142.2 LRJS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Parte
Interposición de demanda
HECHOS
FUNDAMENTOS DE DERECHO
Suplico de presentación de demanda
Otrosí digo: representación del demandante
Segundo otrosí digo: pruebas
Tercer otrosí digo: informe de la ITSS
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], con domicilio en [LOCALIDAD], ante el TRIBUNAL DE INSTANCIA comparece y como mejor proceda en Derecho, DIGO:

Que, por medio del presente escrito, interpongo DEMANDA a fin de que se determine la contingencia causante del proceso de incapacidad temporal iniciado por la parte demandante en fecha [FECHA] como ACCIDENTE DE TRABAJO, la cual dirijo contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], la TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], la empresa [COMPLETAR], con domicilio en [LOCALIDAD], y la Mutua colaboradora con la Seguridad Social [COMPLETAR], con domicilio en [LOCALIDAD], y todo ello sobre la base de los siguientes

HECHOS

El/La demandante presta sus servicios por cuenta de la empresa desde el día [FECHA], ostentando la categoría/grupo profesional de [COMPLETAR], afiliado/a y en alta en el Régimen General de la Seguridad Social con el [COMPLETAR], y percibiendo un salario bruto mensual de [IMPORTE] euros, incluida la prorrata de pagas extraordinarias.

El día [FECHA] al encontrarse en el desempeño de sus funciones, el/la demandante realizó un movimiento brusco sufriendo un bloqueo cervical intenso con dolor en miembro superior izquierdo, siendo diagnosticada de contractura muscular cervical y parestesias con pérdida de fuerza, por lo que fue dado de baja por enfermedad [COMPLETAR] en fecha [FECHA], calificando la contingencia como

Al no estar de acuerdo con la calificación de la contingencia, y al amparo de lo dispuesto en el artículo 6 del Real Decreto 1430/2009, de 11 de septiembre, y en el art. 3 del Real Decreto 625/2014, de 18 de julio, el/la demandante dedujo solicitud de determinación de contingencia.

[NOTA DE REVISIÓN: Según el art. 6.8 RD 1430/2009, la resolución del INSS en el procedimiento de determinación de contingencia puede tener los efectos de la resolución de una reclamación previa (art. 71 LRJS). Fuente: art. 6.8 RD 1430/2009 (BOE-A-2009-15442); art. 3 RD 625/2014 (BOE-A-2014-7684).]

A raíz de esta solicitud, se emitió Dictamen Propuesta del Equipo de Valoración de Incapacidades (EVI) en fecha [FECHA], en el que propone a la Dirección Provincial del INSS "que el proceso de incapacidad temporal iniciado con fecha [FECHA] por el/la trabajador/a es enfermedad [COMPLETAR] y no accidente de trabajo.

El día [FECHA] se dictó Resolución por el INSS declarando el carácter de enfermedad [COMPLETAR] de la incapacidad temporal padecida por el/la demandante. Contra esta resolución, la parte actora interpuso reclamación previa el día [FECHA], siendo desestimada mediante Resolución de fecha [FECHA] (acompaño como documentos [COMPLETAR] copia de la reclamación y de la resolución mencionadas).

Esta parte impugna la citada resolución en tanto que la enfermedad que padece trae causa del accidente sufrido al realizar sus funciones, que debe ser calificado como de accidente de trabajo, pues lo que ha actuado como desencadenante del proceso de IT es el referido accidente laboral sufrido en el lugar de trabajo y durante su jornada, lo que se pone de manifiesto por la conexión causal, espacial y temporal entre el accidente sufrido y la patología, lo cual determina, conforme al art. 156.2 LGSS y en aplicación de la presunción establecida en el art. 156.3 LGSS, que la contingencia deba calificarse como accidente de trabajo a cuyo efecto se interpone esta demanda.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

Competencia y procedimiento

El órgano judicial al que se dirige la demanda tiene jurisdicción y competencia objetiva, funcional y territorial [arts. 2.o), 6 y 10 Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social] para conocer del juicio que se suscita, quedando válidamente constituida la relación jurídico-procesal por ostentar las partes legitimación activa y pasiva; por otra parte, la pretensión deducida debe seguirse por los trámites de la modalidad procesal de prestaciones de Seguridad Social.

Reclamación previa

Los arts. 71 y 140.1 de la Ley 36/2011, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad gestora demandada.

Determinación de la contingencia como accidente de trabajo

El artículo 156.2 de la LGSS establece que tendrán la consideración de accidente de trabajo las enfermedades, no incluidas en el artículo 157 LGSS, que contraiga el trabajador con motivo de la realización de su trabajo, siempre que se pruebe que la enfermedad tuvo por causa exclusiva la ejecución del mismo. Por su parte, el art. 156.3 LGSS establece la presunción, salvo prueba en contrario, que son constitutivas de accidente de trabajo las lesiones que sufra el trabajador durante el tiempo y en el lugar del trabajo. Para la destrucción de la presunción de laboralidad de la enfermedad surgida en el tiempo y lugar de la prestación de servicios es necesario que la falta de relación entre la lesión padecida y el trabajo realizado se acredite de manera suficiente, bien porque se trate de enfermedad que por su propia naturaleza excluya la etiología laboral, bien porque se aduzcan hechos que desvirtúen dicho nexo causal (Sentencia del Tribunal Supremo de 16 de diciembre de 2005, recurso UD 3344/2004). En este caso, la patología que dio lugar al proceso temporalmente invalidante tiene su único fundamento en el desempeño del trabajo; pues es en tal medio en donde se ha generado la enfermedad del recurrente, por lo que la contingencia causante es accidente de trabajo.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentada esta demanda para determinación de contingencia de incapacidad temporal contra el INSS, TGSS, la empresa y la Mutua colaboradora, con sus respectivas copias y documentos que se adjuntan, se sirva admitirla, darle el turno que corresponda, citar a las partes para la celebración del acto del juicio y, en definitiva, dictar sentencia por la que estimando la presente demanda se declare que la contingencia de la que trae causa el proceso de incapacidad temporal del demandante es por accidente de trabajo, con los efectos que corresponden como consecuencia de la determinación de la contingencia causante como accidente de trabajo y en cuanto a la responsabilidad de las prestaciones económicas y sanitarias.

OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por [COMPLETAR], designando a D./D.ª [NOMBRE Y APELLIDOS], con domicilio profesional en [LOCALIDAD], correo electrónico [CORREO ELECTRÓNICO], el/la cual suscribe esta demanda y cuyo domicilio se señala a efectos de notificaciones.

Por lo que,

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes.

SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, interesa al derecho de esta parte la verificación del siguiente medio de prueba:

- DOCUMENTAL, que se requiera a la demandada para que aporte el expediente administrativo.

- MÁS DOCUMENTAL consistente en que, por la Mutua colaboradora con la Seguridad Social, se acompañe el correspondiente expediente tramitado referente al accidente de trabajo padecido, con la documentación médica aportada por el demandante.

Por lo que SUPLICO AL TRIBUNAL: Tenga por propuesto el medio de prueba solicitado y acuerde lo conducente para su práctica.

TERCER OTROSI DIGO: Que se recabe el preceptivo informe a la Inspección de Trabajo y Seguridad Social, al amparo del art. 142.2 LRJS.

Es Justicia, que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma demandante	Firma representante

════════════════════════════════════════════════════════════════════════
