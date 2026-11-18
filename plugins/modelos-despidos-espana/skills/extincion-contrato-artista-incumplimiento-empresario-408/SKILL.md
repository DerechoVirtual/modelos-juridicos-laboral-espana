---
name: extincion-contrato-artista-incumplimiento-empresario-408
description: "Redacta el escrito «Extinción del contrato de artista por incumplimiento del empresario: demanda» (formulario 408 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Extinción del contrato de artista por incumplimiento del empresario: demanda

> Formulario 0408 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Art. 10.4 RD 1435/1985 (redacción RDL 5/2022): la inejecución total de la prestación artística se rige por el Código Civil.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NÚMERO (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] CALLE
- [ ] IMPORTE (5 veces)
- [ ] FECHA (7 veces)
- [ ] Nº DE DOCUMENTO
- [ ] COLEGIO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 21 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…euros, la cual dirijo contra la empresa»; «…, cuyo domicilio radica en»; «…cuyo domicilio radica en [COMPLETAR], de»; «…los, suscribieron un contrato de trabajo»; «…l/la demandante con el grupo profesional»; «…en»; «…en [COMPLETAR] de la empresa situado en»; «…de la empresa situado en [COMPLETAR] de»; «…de [COMPLETAR],»; «…la contratación (acompaño como documento»; «…, en el teatro»; «…, sito en [LOCALIDAD] de»; …

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 10.4 del Real Decreto 1435/1985
- artículo 10.4 del RD 1435/1985
- artículo 63 de la Ley 36/2011
- art. 11 RD 1435/1985
- art. 17 de la Ley 20/2007
- artículo 90.3 LJS
- artículo 80.1.e) LJS

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

### Formulario 0408 · Extinción del contrato de artista por incumplimiento del empresario: demanda

- Año del modelo: 2015
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 45 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº DE DOCUMENTO)
- Avisos de la revisión: Art. 10.4 RD 1435/1985 (redacción RDL 5/2022): la inejecución total de la prestación artística se rige por el Código Civil.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS], mayor de edad, provisto de D.N.I. nº [NÚMERO], con domicilio en [LOCALIDAD], c/ [CALLE], nº [NÚMERO], ante ese Tribunal de Instancia comparezco y como mejor proceda en derecho

DIGO:

Que, al amparo de lo dispuesto en el artículo 10.4 del Real Decreto 1435/1985, de 1 de agosto, por el que se regula la relación laboral especial de las personas artistas que desarrollan su actividad en las artes escénicas, audiovisuales y musicales, así como de las personas que realizan actividades técnicas o auxiliares necesarias para el desarrollo de dicha actividad, mediante el presente escrito interpongo DEMANDA DE PROCESO ORDINARIO de extinción del contrato de trabajo por incumplimiento empresarial que conlleva la inejecución del contrato, reclamando una indemnización de daños y perjuicios de [IMPORTE] euros, la cual dirijo contra la empresa [COMPLETAR], cuyo domicilio radica en [COMPLETAR], de [COMPLETAR], con fundamento en los siguientes

HECHOS

En fecha [FECHA] el/la demandante y la empresa demandada, dedicada a la producción de actividades cinematográficas, de video, y espectáculos, suscribieron un contrato de trabajo [COMPLETAR], de duración determinada, para la prestación de servicios por el/la demandante con el grupo profesional [COMPLETAR] en [COMPLETAR] de la empresa situado en [COMPLETAR] de [COMPLETAR], [COMPLETAR], percibiendo a cambio una retribución de [IMPORTE] euros brutos por programa trabajado, pactándose su duración desde el día [FECHA] hasta fin de los trabajos objeto de la contratación (acompaño como documento [COMPLETAR] copia del contrato de trabajo de fecha [FECHA]).

El/La actor/actriz fue convocado para grabar el primer programa en fecha [FECHA], en el teatro [COMPLETAR], sito en [LOCALIDAD] de [COMPLETAR] Personado en el día señalado, el/la directora/a de la empresa D./Dª [NOMBRE Y APELLIDOS] le informó que por razones ajenas a la voluntad de la empresa se había decidido que no hubiera actuación musical y por tanto que se prescindía de sus servicios, comunicándole que no se iban ya a realizar las grabaciones previstas

La conducta de la empresa constituye un grave e injustificado incumplimiento de sus obligaciones, al haberse producido una falta de ejecución del contrato totalmente imputable a la misma, puesto que ni es cierto que concurriera causa lícita para la falta de ejecución de los trabajos ni es verdad que el programa en el que debía participar el demandante se suspendiese, como se acreditará en el momento procesal oportuno. Al respecto, es de aplicación el artículo 10.4 del RD 1435/1985, de 1 de agosto, que contempla la extinción por incumplimiento empresarial consistente en la inejecución total del contrato que se produce al no haberse empezado a realizar el trabajo pactado entre las partes por culpa exclusiva del empresario.

El incumplimiento empresarial ha ocasionado graves perjuicios al demandante, quien ha sufrido tanto un daño emergente, derivado de la pérdida sufrida por la inejecución del contrato, como un lucro cesante, puesto que con motivo del contrato se vio obligado a abandonar la orquesta [COMPLETAR], en la cual trabajaba y por la que percibía una cantidad de [IMPORTE] euros por actuación (se acompañan como documentos [COMPLETAR] documento de rescisión de contrato con la orquesta [COMPLETAR] en fecha [FECHA] y certificación del agente de dicha orquesta [COMPLETAR] sobre las actuaciones realizadas en el periodo comprendido entre [COMPLETAR]).

Por ello se solicita una indemnización por daños por importe de [IMPORTE] euros, comprensiva del daño emergente y del lucro cesante, atendidas las cantidades dejadas de percibir por el incumplimiento empresarial y las ganancias que no han podido ser obtenidas por parte del actor.

No habiendo percibido cantidad alguna, se instó el preceptivo acto de conciliación ante el órgano administrativo "ad hoc", conforme disponen el artículo 63 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LJS),con el resultado de intentado sin efecto, según acredito documentalmente con la certificación de fecha [FECHA] que acompaño como documento núm. [Nº DE DOCUMENTO]

FUNDAMENTOS DE DERECHO

Jurisdicción y competencia

El órgano judicial al que se dirige la demanda tiene jurisdicción (art. 2.d. LJS y art. 11 RD 1435/1985) y competencia objetiva, funcional y territorial (arts. 2.a., 6 y 10 LJS y art. 17 de la Ley 20/2007, de 11 de julio, del Estatuto del trabajo autónomo [NOTA DE REVISIÓN: El art. 17 de la Ley 20/2007 atribuye al orden social los litigios de los TRADE; no procede en una demanda de la relación laboral especial de artistas (RD 1435/1985). Fuente: Ley 20/2007, art. 17, BOE-A-2007-13409.])

Legitimaciones activa y pasiva

Siendo evidente la existencia de una relación laboral especial de artista, esta parte tiene legitimación activa para interponer la presente demanda contra la empresa [COMPLETAR], del mismo modo que la tiene, en su calidad de pasiva, la parte demandada mencionada.

Procedimiento adecuado

Dada la naturaleza de la acción emprendida por esta parte y habida cuenta de la pretensión que se incardina en la demanda, debe seguirse el trámite del procedimiento ordinario.

Extinción del contrato

El artículo 10.4 del RD 1435/1985 establece que el incumplimiento del contrato por la empresa o por el artista, que conlleve la inejecución total de la prestación artística, se regirá por lo establecido al respecto en el Código Civil. Por inejecución total se entenderán aquellos supuestos en los que ni siquiera hubiera empezado a realizarse el trabajo que constituye la prestación pactada.

Indemnización

Conforme al citado artículo 10.4 del RD 1435/1985, al producirse un incumplimiento empresarial culpable, obstativo del cumplimiento de la obligación recíproca pactada de poner en ejecución el contrato dando y prestando trabajo, debe resolverse el mismo aplicando el régimen indemnizatorio establecido en el artículo 1101 y ss. del Código Civil, en particular el artículo 1106, según el cual la indemnización de daños y perjuicios alcanza tanto el daño emergente (pérdida sufrida) como al lucro cesante (ganancia dejada de obtener).

AL TRIBUNAL SUPLICA: Que teniendo por presentado este escrito se sirva admitirlo, tenga por formulada demanda de extinción del contrato de artista de fecha [FECHA], suscrito entre ambas partes, por incumplimiento de la empresa, y de reclamación de indemnización de daños y perjuicios derivados del incumplimiento, y previos los trámites procesales oportunos dicte Sentencia declarando la extinción y condenando a la demandada a indemnizar al demandante en la cantidad de [IMPORTE] euros con más los intereses correspondientes.

PRIMER OTROSÍ DIGO.- Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el artículo 90.3 LJS, interesa al derecho de esta parte que se practiquen las diligencias de citación de la siguiente prueba que esta parte pretende proponer en el juicio:

- INTERROGATORIO DEL DEMANDADO: Del legal representante de la empresa, que deberá ser citado bajo el apercibimiento de que podrán ser tenidos como ciertos los hechos a que se refieran las preguntas que se le formulen.

AL TRIBUNAL SUPLICA: Admita las diligencias de citación para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

SEGUNDO OTROSÍ DIGO.- Que a los efectos de este procedimiento se designan para la representación y defensa de esta parte, con las facultades más amplias que en derecho hubiere lugar, a los [COMPLETAR] del Ilustre Colegio de [COLEGIO] de [COMPLETAR], D./D.ª [NOMBRE Y APELLIDOS] y D./D.ª [NOMBRE Y APELLIDOS], quien suscribe conmigo esta demanda a todos los efectos prevenidos en el artículo 80.1.e) LJS, designándose el domicilio de dichos profesionales a efectos de notificaciones y citaciones, sito en [LOCALIDAD] de [COMPLETAR].

AL TRIBUNAL SUPLICO que tenga por hechas las anteriores manifestaciones a los efectos oportunos.

Es justicia que respetuosamente solicito en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del demandante y letrado/a, procurador/a, graduado/a social colegiado

================================================================================
