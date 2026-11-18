---
name: riesgo-durante-lactancia-natural-demanda-contra-mutua-259
description: "Redacta el escrito «Riesgo durante la lactancia natural: demanda contra la Mutua» (formulario 259 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Riesgo durante la lactancia natural: demanda contra la Mutua

> Formulario 0259 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Situación protegida: art. 188 LGSS y art. 26.4 LPRL; la prestación se extingue cuando el hijo cumple nueve meses (art. 189 LGSS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] LOCALIDAD (6 veces)
- [ ] DNI/NIE
- [ ] FECHA (6 veces)
- [ ] NÚMERO
- [ ] Nº
- [ ] IMPORTE
- [ ] NOMBRE Y APELLIDOS
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 19 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, en»; «…tua Colaboradora con la Seguridad Social»; «…tua Colaboradora con la Seguridad Social»; «…, contra la empresa»; «…como persona trabajadora para la empresa»; «…, dedicada a la actividad de»; «…, con»; «…, con [COMPLETAR] de»; «…ción a la Seguridad Social en el Régimen»; «…tua Colaboradora con la Seguridad Social»; «…, la actora tuvo un hijo»; «…ión de Riesgos Laborales, por la empresa»; …

## Correcciones de la revisión (4)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 26.4 de la Ley 31/1995
- arts. 4 y 21 LOPJ
- arts. 2.o), 6 y 10 Ley 36/2011
- artículo 26.4 de la Ley 31/1995
- articulo 26.4 de la Ley de Prevención de Riesgos Laborales
- artículo 45.1 e) del Estatuto de los Trabajadores

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

### Formulario 0259 · Riesgo durante la lactancia natural: demanda contra la Mutua

- Año del modelo: 2011
- Revisión 17-11-2026: 4 citas normativas corregidas tras comprobarlas en el BOE; 37 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Situación protegida: art. 188 LGSS y art. 26.4 LPRL; la prestación se extingue cuando el hijo cumple nueve meses (art. 189 LGSS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Parte
Interposición de la demanda
HECHOS
FUNDAMENTOS DE DERECHO
Suplico de interposición de demanda
Otrosí de representación
Otrosí de proposición de prueba
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

Dª., mayor de edad, con domicilio en [LOCALIDAD], en [COMPLETAR], provisto de DNI [DNI/NIE], ante ese Tribunal de Instancia comparece y como mejor proceda en derecho DICE:

Que mediante el presente escrito formulo demanda, que deberá ser tramitada por la modalidad procesal de prestaciones de la Seguridad Social, en reclamación de PRESTACIÓN POR RIESGO DURANTE LA LACTANCIA NATURAL del Régimen General, denegada por la resolución de fecha [FECHA] de la Mutua Colaboradora con la Seguridad Social [COMPLETAR], por la que se desestima la reclamación previa presentada por el que suscribe en fecha [FECHA], por estimar que la misma no se ajusta a derecho, y resultan perjudicial para mis intereses, dicho sea con los debidos respecto y en términos de defensa, la cual dirijo contra la citada Mutua Colaboradora con la Seguridad Social [COMPLETAR], con domicilio en [LOCALIDAD], contra la empresa [COMPLETAR], con domicilio en [LOCALIDAD], y contra el INSS y la TGSS, con domicilio en [LOCALIDAD], demanda que baso en los siguientes:

HECHOS

PRIMERO.- La exponente viene prestando sus servicios como persona trabajadora para la empresa [COMPLETAR] con domicilio en [LOCALIDAD], dedicada a la actividad de [COMPLETAR], con [COMPLETAR] de [COMPLETAR] y con número de afiliación a la Seguridad Social en el Régimen [COMPLETAR], con el número [NÚMERO] acreditando un periodo de cotización de [Nº] días.

La empresa tiene cubierta la responsabilidad por prestaciones con la Mutua Colaboradora con la Seguridad Social [COMPLETAR].

SEGUNDO.- La actora desempeña las funciones de vigilante de seguridad que comprenden la vigilancia y protección de bienes e inmuebles, así como la protección de los que puedan encontrarse en los mismos y evitar actos delictivos y poner a disposición de los miembros de las Fuerzas de Seguridad, desempeñando su trabajo en turnos y en ocasiones nocturno.

TERCERO.- En fecha [FECHA], la actora tuvo un hijo [COMPLETAR] que está siendo alimentado exclusivamente con lactancia materna, solicitando la prestación por riesgo durante la lactancia, al tratarse de un puesto de riesgo y no existiendo otro puesto de trabajo compatible con su situación acorde al art. 26.4 de la Ley 31/1995 [NOTA DE REVISIÓN: Para la lactancia natural rige el art. 26.4 LPRL (que remite a los apartados 1 a 3); el 26.3 es el embarazo. Fuente: art. 26 LPRL, BOE-A-1995-24292.], de 8 de noviembre, de Prevención de Riesgos Laborales, por la empresa [COMPLETAR] se propuso la suspensión del contrato de trabajo por riesgo durante el embarazo o lactancia natural, en fecha [FECHA] sellado y firmado por la empresa codemandada, la cual le fue denegada mediante Resolución de la Mutua Colaboradora con la Seguridad Social [COMPLETAR] de fecha [FECHA] le fue denegada dicha prestación por ser compatible la situación con la realización del trabajo habitual.

CUARTO.- La actora formuló contra la anterior resolución reclamación previa que fue desestimada por otra de fecha [FECHA], agotándose de esta forma la vía previa, y la cual acompaño como documento [COMPLETAR] de la demanda.

Por lo expuesto, y estando disconforme con la resolución impugnada, interpongo la presente acción en reclamación de la prestación por riesgo durante la lactancia.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

En cuanto a los sujetos procesales y procedimiento, este órgano judicial al que se dirige la demanda tiene jurisdicción (arts. 4 y 21 LOPJ) y competencia objetiva, funcional y territorial (arts. 2.o), 6 y 10 Ley 36/2011 [NOTA DE REVISIÓN: Las letras a) y c) del art. 2 son contrato de trabajo y sociedades laborales; la prestación por riesgo durante la lactancia es la o). Fuente: art. 2.o) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], de 10 de octubre, reguladora de la jurisdicción social) para conocer del juicio que se suscita, quedando válidamente constituida la relación jurídico-procesal por ostentar las partes legitimación activa y pasiva; por otra parte, la pretensión deducida debe seguirse por los trámites de la modalidad de prestaciones de la Seguridad Social.

En cuanto a la situación protegida es de aplicación el artículo 188 de la Ley General de Seguridad Social [NOTA DE REVISIÓN: El texto citado es el art. 188 (lactancia); el 186 es el riesgo durante el embarazo. Fuente: arts. 186 y 188 LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.] que dispone que "a los efectos de la prestación económica por riesgo durante la lactancia natural, se considera situación protegida el período de suspensión del contrato de trabajo en los supuestos en que, debiendo la mujer trabajadora cambiar de puesto de trabajo por otro compatible con su situación, en los términos previstos en el artículo 26.4 de la Ley 31/1995 [NOTA DE REVISIÓN: Errata en la cita literal del art. 188 LGSS, que remite al art. 26.4 LPRL (está dentro de comillas). Fuente: art. 188 LGSS; art. 26.4 LPRL (Ley 31/1995, BOE-A-1995-24292).], de 8 de noviembre, de prevención de riesgos laborales, dicho cambio de puesto no resulte técnica u objetivamente posible, o no pueda razonablemente exigirse por motivos justificados". Por su parte, el articulo 26.4 de la Ley de Prevención de Riesgos Laborales establece que "lo dispuesto en los números 1 y 2 de este artículo será también de aplicación durante el período de lactancia natural, si las condiciones de trabajo pudieran influir negativamente en la salud de la mujer o del hijo y así lo certifiquen los Servicios Médicos del Instituto Nacional de la Seguridad Social o de las Mutuas, en función de la Entidad con la que la empresa tenga concertada la cobertura de los riesgos profesionales, con el informe del médico del Servicio Nacional de Salud que asista facultativamente a la trabajadora o a su hijo. Podrá, asimismo, declararse el pase de la trabajadora afectada a la situación de suspensión del contrato por riesgo durante la lactancia natural de hijos menores de nueve meses contemplada en el artículo 45.1 e) del Estatuto de los Trabajadores, si se dan las circunstancias previstas en el número 3 de este articulo".

En cuanto a la procedencia de la pretensión sostenida, debe citarse la doctrina unificada establecida en la STS de 17 de marzo de 2011 y STS de 21 de marzo de 2013 y, en igual sentido, STS 3 de abril de 2018 en las que se expresa que la, evaluación de los riesgos en caso de lactancia natural en relación con el puesto de trabajo ha de ser específica, que alcance a la determinación de la naturaleza, grado, y duración de la exposición. Una vez determinados esos extremos, la acción inmediata que ha de seguirse por parte del empresario es la de adoptar las medidas necesarias para evitar esa exposición al riesgo, adaptando las condiciones o el tiempo de trabajo de la trabajadora.

En el caso de la actora, desempeña un trabajo peligroso, pues conlleva no sólo la vigilancia y protección de bienes sino también evitar delitos y poner a los delincuentes a disposición de las fuerzas de seguridad, y que no existe otro puesto disponible que no conlleve tal circunstancia. Por otra parte, es un trabajo sin horario fijo, pues se efectúa a turnos, y que conlleva además trabajo nocturno. En definitiva, es un trabajo que conlleva situaciones de estrés, que supone una irregularidad horaria y que compromete el tiempo nocturno, elementos todos que hacen penosa y no sólo incómoda la lactancia natural, pues, como indica la STC de 3 de julio de 2006, esta prestación hay que contemplarla tanto como una técnica de compatibilidad de la maternidad y el trabajo, cuanto de protección de la salud del hijo.

En cuanto a la cuantía económica de la prestación, es de aplicación el artículo 189 de la Ley General de Seguridad Social, el cual establece que la prestación económica por riesgo durante la lactancia natural se concederá a la mujer trabajadora en los términos y condiciones previstos en esta ley para la prestación económica por riesgo durante el embarazo en el articulo 187, y se extinguirá en el momento en que el hijo cumpla nueve meses, salvo que la beneficiaria se haya reincorporado con anterioridad a su puesto de trabajo anterior o a otro compatible con su situación.

Por lo expuesto, respetuosamente

SUPLICO AL TRIBUNAL Que tenga por presentado este escrito, con sus copias y documento, se sirva admitirlo, tener por interpuesta la presente demanda en reclamación sobre PRESTACIÓN DE RIESGO DURANTE LA LACTANCIA, contra la Mutua Colaboradora con la Seguridad Social [COMPLETAR], la empresa [COMPLETAR], el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL y contra la TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, y previo los trámites legales oportunos, declarando el derecho de la actora a la prestación económica correspondiente por un periodo de nueve meses, con una base reguladora diaria de [IMPORTE] euros, condenando a los demandados, a pasar por dicha declaración con todas las consecuencias legales inherentes a la misma.

PRIMER OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por [COMPLETAR], designando a D. /Dña. [NOMBRE Y APELLIDOS], con domicilio profesional en [LOCALIDAD], [COMPLETAR] el cual suscribe esta demanda y cuyo domicilio se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes.

SEGUNDO OTROSÍ DIGO: Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el art. 90.3 de la Ley reguladora de la jurisdicción social, interesa al derecho de esta parte que se practiquen las diligencias de citación de la siguiente prueba que esta parte pretende proponer en el juicio:

DOCUMENTAL, requiriendo a la empresa [COMPLETAR] para que aporte los documentos relativos a la evaluación del riesgo del puesto de trabajo desempeñado por mi representada

AL TRIBUNAL SUPLICA: Admita la diligencia de requerimiento para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

Es Justicia que respetuosamente solicito en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del demandante y persona representante

════════════════════════════════════════════════════════════════════════
