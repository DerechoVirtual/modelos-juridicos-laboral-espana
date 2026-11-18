---
name: trade-demanda-extincion-incumplimiento-empresa-cliente-406
description: "Redacta el escrito «TRADE: demanda de extinción por incumplimiento de la empresa cliente» (formulario 406 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# TRADE: demanda de extinción por incumplimiento de la empresa cliente

> Formulario 0406 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] NÚMERO (3 veces)
- [ ] LOCALIDAD
- [ ] CALLE (3 veces)
- [ ] IMPORTE (8 veces)
- [ ] FECHA (3 veces)
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] COLEGIO
- [ ] NÚMERO DE LA CALLE
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 13 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…euros, la cual dirijo contra la entidad»; «…, cuyo domicilio radica en»; «…alización de la actividad profesional de»; «…estando sus servicios profesionales como»; «…euros (acompaño como documentos»; «…les justificativos). A partir del mes de»; «…ente sus trabajos desde el pasado mes de»; «…euros (acompaño como documentos»; «…ado por mi representado a partir del mes»; «… del mes, tal como consta en la cláusula»; «…esente demanda contra la empresa cliente»; «…lias que en derecho hubiere lugar, a los»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 63 de la LJS
- art. 2.d) LJS
- arts. 2.d), 6 y 10 LJS
- Ley 20/2007

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

### Formulario 0406 · TRADE: demanda de extinción por incumplimiento de la empresa cliente

- Año del modelo: 2015
- Revisión 17-11-2026: 37 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 3 huecos del original que se habían perdido sin marca, marcados (FECHA, Nº DE DOCUMENTO, NÚMERO DE LA CALLE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS], mayor de edad, provisto de D.N.I. nº [NÚMERO], con domicilio en [LOCALIDAD], c/ [CALLE], nº [NÚMERO], ante ese Tribunal de Instancia comparece y como mejor proceda en derecho DICE:

Que mediante el presente escrito interpongo DEMANDA DE PROCESO ORDINARIO de extinción del contrato de trabajador autónomo dependiente por incumplimiento de la empresa cliente, reclamando una indemnización de daños y perjuicios de [IMPORTE] euros, la cual dirijo contra la entidad [COMPLETAR], cuyo domicilio radica en [COMPLETAR], c/ [CALLE], nº [NÚMERO], con fundamento en los siguientes

HECHOS

En fecha [FECHA], el demandante y la empresa cliente demandada suscribieron al amparo de la Ley 20/2007, del Estatuto del Trabajador Autónomo, un contrato de trabajador autónomo económicamente dependiente, para la realización de la actividad profesional de [COMPLETAR], el cual fue registrado en la oficina pública (acompaño como documento número [Nº DE DOCUMENTO] copia de un ejemplar del citado contrato).

El contrato se concertó por tiempo indefinido y por ello, como es de ver en sus cláusulas, no se pactó plazo ni servicio determinado.

Desde la fecha del contrato, el demandante ha venido prestando sus servicios profesionales como [COMPLETAR], con una facturación bruta en exclusiva para dicha empresa cliente de [IMPORTE] euros anuales; y con un importe de promedio/facturación diaria de [IMPORTE] euros (acompaño como documentos [COMPLETAR] documentos contables justificativos).

A partir del mes de [COMPLETAR], la empresa cliente empezó a retrasarse en el pago de los servicios realizados por el actor, incumplimiento que fue agravándose al punto de dejar de abonar totalmente sus trabajos desde el pasado mes de [COMPLETAR], estando la empresa cliente en adeudar la cantidad de [IMPORTE] euros, con el siguiente desglose:

Mes de [IMPORTE] euros

Mes de [IMPORTE] euros

(acompaño como documentos [COMPLETAR], facturas impagadas por la empresa cliente).

La conducta de la empresa cliente constituye un grave e injustificado incumplimiento de sus obligaciones, con lesión del derecho profesional del demandante reconocido en el art. 4.3.f) de la Ley (derecho a la percepción puntual de la contraprestación económica convenida por el ejercicio profesional de su actividad), al haberse retrasado reiteradamente en el pago, y haber dejado de abonar las cantidades correspondientes al trabajo realizado por mi representado a partir del mes [COMPLETAR] de las cuales debían ser satisfechas a la finalización del mes, tal como consta en la cláusula [COMPLETAR] del contrato, de manera que se ha incumplido gravemente sus obligaciones, debiendo decretarse por ello la extinción del contrato e indemnizar los daños y perjuicios ocasionados al actor conforme a lo dispuesto en el apartado 3 del art. 15 del Estatuto del Trabajador Autónomo, en relación con los apartados 2 y 4 del mismo art. 15, cuyo "quantum" se fija en [IMPORTE] euros, de acuerdo a lo establecido en dicho precepto.

No habiendo percibido cantidad alguna, se instó el preceptivo acto de conciliación ante el órgano administrativo "ad hoc", conforme disponen el artículo 63 de la LJS en relación con el art. 18 del Estatuto del Trabajador Autónomo, con el resultado de intentado sin efecto, según acredito documentalmente con la certificación de fecha [FECHA] que acompaño como documento núm. [Nº DE DOCUMENTO]

FUNDAMENTOS DE DERECHO

Jurisdicción y competencia

El órgano judicial al que se dirige la demanda tiene jurisdicción (art. 2.d) LJS) y competencia objetiva, funcional y territorial (arts. 2.d), 6 y 10 LJS y art. 17 Estatuto del Trabajo Autónomo).

Legitimaciones activa y pasiva

Siendo evidente la existencia de una relación de TRADE, esta parte tiene legitimación activa para interponer la presente demanda contra la empresa cliente [COMPLETAR] del mismo modo que la tiene, en su calidad de pasiva, la parte demandada mencionada.

Procedimiento adecuado

Dada la naturaleza de la acción emprendida por esta parte y habida cuenta de la pretensión que se incardina en la demanda, debe seguirse el trámite del procedimiento ordinario, al no existir un cauce específico para la acción, según se reitera en la interpretación de los Tribunales.

Extinción del contrato TRADE

El art. 15.1.e) del Estatuto del Trabajo Autónomo establece que la relación contractual entre las partes se extinguirá por voluntad del trabajador autónomo económicamente dependiente, fundada en un incumplimiento contractual grave de la contraparte.

Indemnización

El art. 15.2 de la citada Ley establece que si la resolución contractual se produce por la voluntad de una de las partes fundada en un incumplimiento contractual de la otra, quien resuelva el contrato tendrá derecho a percibir la correspondiente indemnización por los daños y perjuicios ocasionados, en tanto que el apartado 4 del mismo art. 15 establece que cuando la parte que tenga derecho a la indemnización sea el trabajador autónomo económicamente dependiente, la cuantía de la indemnización será la fijada en el contrato individual o en el acuerdo de interés profesional que resulte de aplicación; en los casos en que no estén regulados, a los efectos de determinar su cuantía se tomarán en consideración, entre otros factores, el tiempo restante previsto de duración del contrato, la gravedad del incumplimiento del cliente, las inversiones y gastos anticipados por el trabajador autónomo económicamente dependiente vinculados a la ejecución de la actividad profesional contratada y el plazo de preaviso otorgado por el cliente sobre la fecha de extinción del contrato.

AL TRIBUNAL SUPLICA: Que teniendo por presentado este escrito se sirva admitirlo, tenga por formulada Demanda de extinción del contrato de fecha [FECHA] suscrito entre ambas partes, por incumplimiento de la empresa cliente, y de reclamación de indemnización de daños y perjuicios derivados del incumplimiento, y previos los trámites procesales oportunos dicte Sentencia declarando la extinción y condenando a la demandada a indemnizar al demandante en la cantidad de [IMPORTE] euros con más los intereses correspondientes.

PRIMER OTROSÍ DIGO.- Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el art. 90.3 de la Ley reguladora de la jurisdicción social, interesa al derecho de esta parte que se practiquen las diligencias de citación de la siguiente prueba que esta parte pretende proponer en el juicio:

- INTERROGATORIO DEL DEMANDADO: Del legal representante de la empresa cliente, que deberá ser citado bajo el apercibimiento de que podrán ser tenidos como ciertos los hechos a que se refieran las preguntas que se le formulen.

AL TRIBUNAL SUPLICA: Admita las diligencias de citación para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

SEGUNDO OTROSÍ DIGO.- Que a los efectos de este procedimiento se designan para la representación y defensa de esta parte, con las facultades más amplias que en derecho hubiere lugar, a los [COMPLETAR] del Ilustre Colegio de [COLEGIO] de [COMPLETAR], D./D.ª [NOMBRE Y APELLIDOS] y D./D.ª [NOMBRE Y APELLIDOS], quien suscribe conmigo esta demanda a todos los efectos prevenidos en el artículo 80.1.e) de la Ley reguladora de la jurisdicción social, designándose el domicilio de dichos profesionales a efectos de notificaciones y citaciones, sito en la c/ [CALLE], nº [NÚMERO DE LA CALLE]

AL TRIBUNAL SUPLICO que tenga por hechas las anteriores manifestaciones a los efectos oportunos.

Es justicia que respetuosamente solicito en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del demandante y letrado/procurador/graduado social colegiado

================================================================================
