---
name: despido-colectivo-fuerza-mayor-sin-resolucion-249
description: "Redacta el escrito «Despido colectivo por fuerza mayor sin resolución administrativa: demanda» (formulario 249 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido colectivo por fuerza mayor sin resolución administrativa: demanda

> Formulario 0249 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.

## Nota explicativa: puntualizaciones de la revisión

La nota explicativa de este formulario se ha revisado en el BOE. Tenlo en cuenta al redactar:

- Fuerza mayor: la extinción exige resolución previa de la autoridad laboral que constate la fuerza mayor, dictada en cinco días desde la solicitud (art. 51.7 ET). Si la empresa extingue sin ella, falta el procedimiento del art. 51.7 ET, y eso es causa de nulidad (art. 124.11 LRJS). La impugnación de la resolución administrativa, cuando exista, va por el art. 151 LRJS ante la Sala de lo Social del TSJ o de la Audiencia Nacional (arts. 7.a y 8.1 LRJS).
- Lo demás está vigente: legitimación (art. 124.1, 124.3 y 124.13 LRJS), competencia de la Audiencia Nacional o del TSJ (arts. 8.1 y 7.a LRJS), demanda a los firmantes del acuerdo (art. 124.4), caducidad de veinte días (art. 124.6) y exención de conciliación o mediación previas (arts. 124.5 y 64.1 LRJS; los MASC de la LO 1/2025 no rigen en lo social).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión. Empieza con una nota explicativa (para qué sirve el escrito y cuándo se usa), revisada en el BOE: léela antes de redactar, pero no la copies en el escrito.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LOCALIDAD
- [ ] CALLE
- [ ] FECHA (4 veces)
- [ ] DESCRIBIR
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…E LA AUTORIDAD LABORAL contra la empresa»; «…, cuyo domicilio radica en»; «…la empresa»; «…o su intención de extinguir un número de»; «…tantes de los trabajadores el despido de»; «…va previa del departamento de trabajo de»; «…ue suscribe, con despacho profesional en»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 124 de la Ley 36/2011
- artículo 51.7 del Real Decreto Legislativo 2/2015
- artículo 124.1 de la LRJS
- art. 51.7 del ET
- artículo 124.9 de la LRJS

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

### Formulario 0249 · Despido colectivo por fuerza mayor sin resolución administrativa: demanda

- Año del modelo: 2012
- Revisión 17-11-2026: 17 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.
- Nota explicativa incorporada desde la colección Procesal (formulario 337) y revisada en el BOE el 17-11-2026

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

#### Nota explicativa: para qué sirve este escrito

Recuerde que.... El despido colectivo puede ser impugnado por los representantes legales de los trabajadores, por los representantes sindicales que tengan implantación suficiente en el ámbito del despido colectivo (artículo 124.1 LRJS), por el empresario (artículo 124.3 LRJS) y por el trabajador individual (artículo 124.13 LRJS). Este formulario desarrolla la modalidad colectiva para cuyo ejercicio están legitimados los representantes legales o sindicales de los trabajadores. En el caso de la demanda por los representantes:- Competencia: es competente la Sala de lo Social de la Audiencia Nacional (si extiende sus efectos a un ámbito territorial superior al de una Comunidad Autónoma)o la Sala de lo Social del Tribunal Superior de Justicia de las distintas Comunidades Autónomas (de la Comunidad Autónoma en la que el despido extienda sus efectos).- Están exceptuados del requisito de intento de conciliación, o en su caso de mediación,- La demanda puede ser presentada por todos los representantes de los trabajadores de la empresa o sólo por parte de ellos, siempre que el acuerdo de presentar la demanda se adopte por la mayoría de miembros del comité de empresa ya que, al tratarse de un órgano colegiado, sus decisiones han de ser adoptadas por acuerdo mayoritario de sus miembros. Asimismo puede presentarse por los representantes sindicales de un solo sindicato o de varios, siempre que tengan implantación suficiente en el ámbito del despido colectivo. Si no tienen implantación suficiente no están legitimados para presentar la demanda. STS de 21 de octubre de 2014.- La sentencia declarará nula la decisión extintiva cuando el empresario no haya realizado el período de consultas o entregado la documentación prevista en el artículo 51.2 ET (RCL 2015, 1654) o no haya respetado el procedimiento establecido en el artículo 51.7 ET u obtenido la autorización judicial del juez del concurso en los supuestos en que esté legalmente prevista, así como cuando la medida empresarial se haya efectuado con vulneración de derechos fundamentales y libertades públicas- En el caso de que el período de consultas hubiera finalizado con acuerdo, los representantes de los trabajadores que formulan la demanda y no firmaron dicho acuerdo deberán demandar a los firmantes del mismo.- La demanda deberá presentarse en el plazo de caducidad de veinte días desde la fecha del acuerdo alcanzado en el período de consultas o de la notificación a los representantes de los trabajadores de la decisión empresarial de despido colectivo- La demanda podrá fundarse en los siguientes motivos:- a) Que no concurre la causa legal indicada en la comunicación escrita.- b) Que no se ha realizado el período de consultas o entregado la documentación prevista en el artículo 51.2 ET o no se ha respetado el procedimiento establecido en el artículo 51.7 ET.- c) Que la decisión extintiva se ha adoptado con fraude, dolo, coacción o abuso de derecho.- d) Que la decisión extintiva se ha efectuado vulnerando derechos fundamentales y libertades públicas.- El número de trabajadores afectados en un periodo de noventa días determina si las extinciones por causas económicas, técnicas, organizativas o de producción siguen el cauce del despido colectivo (art. 51.1 ET); en cambio, la fuerza mayor ha de ser constatada por la autoridad laboral cualquiera que sea el número de trabajadores afectados (art. 51.7 ET).

---

Encabezamiento
Formulación de la interposición de demanda
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Primer otrosí digo: pruebas
Segundo otrosí digo: representación
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D. / Dña. [NOMBRE Y APELLIDOS], abogado/graduado social colegiado/procurador, en representación de la Sección sindical de [LOCALIDAD], según acredito mediante escritura de poder que acompaño (o designación apud-acta), ante el Tribunal de Instancia que por turno de reparto corresponda, comparezco y, como mejor proceda en derecho, DIGO

Que por medio del presente escrito, al amparo de lo dispuesto en el artículo 124 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (en lo sucesivo LRJS), INTERPONGO DEMANDA DE DESPIDO COLECTIVO POR CAUSA DE FUERZA MAYOR SIN RESOLUCIÓN-ADMINISTRATIVA PREVIA DE LA AUTORIDAD LABORAL contra la empresa [COMPLETAR], en la persona de su legal representante, Don / Dña. [NOMBRE Y APELLIDOS], cuyo domicilio radica en [COMPLETAR], calle [CALLE], con fundamento en los siguientes

HECHOS

PRIMERO.- Que el pasado día [FECHA] la empresa [COMPLETAR] inició un período de consultas con los representantes de los trabajadores, manifestando su intención de extinguir un número de [COMPLETAR] contratos por razones de fuerza mayor

SEGUNDO.- No habiéndose alcanzado ningún acuerdo, el día [FECHA], la empresa comunicó a los representantes de los trabajadores el despido de [COMPLETAR] trabajadores/as, con efectos del día [FECHA], alegándose como justificación del mismo que se había producido una causa de fuerza mayor consistente en [DESCRIBIR].

El despido afecta a los siguientes trabajadores/as:

TERCERO.- Que dicho despido debe considerarse nulo, ya que la fuerza mayor no ha sido constatada por resolución administrativa previa del departamento de trabajo de [COMPLETAR], constituyendo la misma una exigencia legal, a tenor de lo dispuesto en el artículo 51.7 del Real Decreto Legislativo 2/2015, de 23 de octubre, por el que se aprueba el texto refundido de la Ley del Estatuto de los Trabajadores (en lo sucesivo ET) y artículos 31 y ss del RD 1483/2012, de 29 de octubre, para los casos de extinción del contrato por fuerza mayor, trámite éste que resultó totalmente omitido por el empresario.

CUARTO.- La presente demanda se plantea en el plazo de veinte días des desde la notificación a los representantes de los trabajadores el pasado día [FECHA], no siendo necesario el agotamiento de ninguna de las formas de evitación del proceso.

FUNDAMENTOS DE DERECHO

Primero.- JURISDICCIÓN Y COMPETENCIA

.- El Tribunal al que va dirigida la presente demanda tiene jurisdicción bastante y competencias territorial, funcional y objetiva o material para el conocimiento y decisión de la litis, habida cuenta lo que disponen, al efecto, los artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica del Poder Judicial de 1 de julio de 1985, en relación con lo que ordenan los artículos 2, 6 y 10 de la LJRS.

Segundo.- LEGITIMACIONES ACTIVA Y PASIVA

. Esta parte tiene legitimación activa para interponer la presente demanda en su calidad de representante sindical conforme al artículo 124.1 de la LRJS, del mismo modo que la tiene el empresario, en su calidad de pasiva, la parte demandada mencionada.

Tercero.- PROCEDIMIENTO ADECUADO

.- Dada la naturaleza de la acción emprendida por esta parte y habida cuenta de la pretensión que se incardina en la demanda y, por tanto, a la vista del objeto en litigio, es procedente que la presente litis se encauce por las reglas que, al efecto, determina el artículo, 124 LRJS, al tratarse de una extinción contractual por fuerza mayor sin autorización administrativa previa, debiendo tramitarse por vía urgente con preferencia absoluta.

Cuarto.- MOTIVOS

.- La demanda se funda en la infracción del art. 51.7 del ET al no haberse seguido el procedimiento establecida con carácter preceptivo en el referido precepto, debiendo declararse nula la decisión empresarial de despido conforme a lo prevenido en el artículo 124.9 de la LRJS.

Por lo expuesto,

SUPLICAN AL TRIBUNAL: Que teniendo por presentado este escrito, documentos que se acompañan y copias de todo ello, se sirva admitirlo, y tener por interpuesta demanda contra [ACTO O RESOLUCIÓN], en reclamación por despido nulo y, previos los trámites legales oportunos, dicte sentencia estimando la demanda y declarando la nulidad de la decisión extintiva con las consecuencias inherentes a dicho pronunciamiento.

PRIMER OTROSÍ DIGO: Que sin perjuicio de las pruebas que se aporten en su momento, esta parte intenta valerse de las siguientes.

INTERROGATORIO del representante legal de la empresa demandada, previa citación judicial bajo los apercibimientos legales.

DOCUMENTAL PRIVADA, consistente en que se requiera a la empresa demandada para que aporte toda la documentación relativa al procedimiento seguido para la extinción de los contratos.

SEGUNDO OTROSÍ DIGO: Que esta parte comparecerá en juicio con el letrado/graduado social colegiado/procurador, que suscribe, con despacho profesional en [COMPLETAR], domicilio que designo a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Que tenga por hechas las manifestaciones de los anteriores otrosíes, a los efectos oportunos.

Es Justicia, que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

D./Dña. [NOMBRE Y APELLIDOS]

Firma letrado/graduado social colegiado/procurador

════════════════════════════════════════════════════════════════════════

---

#### Notas al pie

[NOTA DE REVISIÓN: Fuerza mayor: la extinción exige resolución previa de la autoridad laboral que constate la fuerza mayor, dictada en cinco días desde la solicitud (art. 51.7 ET). Si la empresa extingue sin ella, falta el procedimiento del art. 51.7 ET, y eso es causa de nulidad (art. 124.11 LRJS). La impugnación de la resolución administrativa, cuando exista, va por el art. 151 LRJS ante la Sala de lo Social del TSJ o de la Audiencia Nacional (arts. 7.a y 8.1 LRJS).]

[NOTA DE REVISIÓN: Lo demás está vigente: legitimación (art. 124.1, 124.3 y 124.13 LRJS), competencia de la Audiencia Nacional o del TSJ (arts. 8.1 y 7.a LRJS), demanda a los firmantes del acuerdo (art. 124.4), caducidad de veinte días (art. 124.6) y exención de conciliación o mediación previas (arts. 124.5 y 64.1 LRJS; los MASC de la LO 1/2025 no rigen en lo social).]
