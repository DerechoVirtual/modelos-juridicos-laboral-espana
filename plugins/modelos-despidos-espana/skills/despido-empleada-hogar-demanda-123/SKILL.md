---
name: despido-empleada-hogar-demanda-123
description: "Redacta el escrito «Despido de empleada del hogar: demanda» (formulario 123 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido de empleada del hogar: demanda

> Formulario 0123 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Desistimiento en el hogar familiar: el art. 11 RD 1620/2011 (redacción RDL 16/2022) exige causa justificada (letras a-c del ap. 2), comunicación escrita, indemnización de 12 días por año con límite de seis mensualidades y preaviso de 20 días (7 si dura menos de un año); su incumplimiento formal hace presumir despido.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] FECHA (6 veces)
- [ ] IMPORTE (2 veces)
- [ ] Nº
- [ ] Nº DE DOCUMENTO
- [ ] COLEGIO
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, de»; «…, con domicilio en [LOCALIDAD], de»; «…, en virtud de contrato de trabajo»; «…horas semanales entre los días»; «…, con horario»; «…(acompaño como documentos»; «…, enviándole finiquito fechado el»; «…ancaria. Acompaño como documento números»; «…ta de extinción son totalmente inciertos»; «…to que se hace una referencia genérica a»; «…, acompañando como documentos»; «…, a»; …

## Elecciones que hay que hacer

- externa/o / interna/o
- Disminución de los ingresos de la unidad familiar o incremento de sus gastos por circunstancia sobrevenida / Modificación sustancial de las necesidades de la unidad familiar que justifican que se prescinda de la persona trabajadora del hogar / El comportamiento de la persona trabajadora que fundamente de manera razonable y proporcionada la pérdida de confianza de la persona empleadora
- sin avenencia / sin efecto

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 1, 2 y 3 de la Ley 36/2011
- art. 13 del RD 1620/2011
- artículo 24.1 de la CE
- artículo 103.1 de la LJS
- artículos 53, 55 y 59 ET
- art. 11 del RD 1620/2011
- artículo 49.1 del Estatuto de los Trabajadores
- art. 11.2 del RD 1620/2011
- artículos 54, 55 y 56 ET
- Real Decreto 1620/2011

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

### Formulario 0123 · Despido de empleada del hogar: demanda

- Año del modelo: 2022
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 37 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: Desistimiento en el hogar familiar: el art. 11 RD 1620/2011 (redacción RDL 16/2022) exige causa justificada (letras a-c del ap. 2), comunicación escrita, indemnización de 12 días por año con límite de seis mensualidades y preaviso de 20 días (7 si dura menos de un año); su incumplimiento formal hace presumir despido.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Otrosí I. Documentación
Otrosí II. Pruebas
Otrosí III. Representación
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto/a de D.N.I., con domicilio en [LOCALIDAD], de [COMPLETAR], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que por medio del presente escrito interpongo ante el Tribunal de Instancia de DEMANDA por despido contra D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], de [COMPLETAR], la cual deberá tramitarse por la modalidad procesal de los artículos 103 y siguientes de la Ley 36/2011, y ello con fundamento en los siguientes

HECHOS

PRIMERO.- La/El demandante ha venido prestando sus servicios para el/la demandado/a, con la categoría profesional de empleada/o de hogar, desde el día [FECHA], en virtud de contrato de trabajo [COMPLETAR] prestando sus servicios como empleada/o [ELEGIR: externa/o / interna/o], con un salario mensual bruto con prorrata de pagas extras de [IMPORTE] euros, con arreglo a una jornada, de [Nº] horas semanales entre los días [COMPLETAR], con horario [COMPLETAR] (acompaño como documentos [COMPLETAR] contrato de trabajo y nóminas).

SEGUNDO.- Con fecha [FECHA], el/la empleador/a remite carta de extinción del contrato de trabajo con efectos desde el día [FECHA], alegando [ELEGIR: Disminución de los ingresos de la unidad familiar o incremento de sus gastos por circunstancia sobrevenida / Modificación sustancial de las necesidades de la unidad familiar que justifican que se prescinda de la persona trabajadora del hogar / El comportamiento de la persona trabajadora que fundamente de manera razonable y proporcionada la pérdida de confianza de la persona empleadora]. Todo ello en base al art. 11.2 a), b) y c) del Real Decreto 1620/2011, de 14 de noviembre, y sin especificar los hechos motivadores de la extinción ni acreditar la supuesta causa de extinción.

La carta, asimismo, le insta a que finalice las vacaciones pendientes hasta el día [FECHA], enviándole finiquito fechado el [COMPLETAR] desglosado en los siguientes conceptos: Salario y vacaciones [IMPORTE] euros, importe que se ha hecho efectivo mediante transferencia bancaria.

Acompaño como documento números [COMPLETAR] copias de la carta de extinción y transferencia bancaria.

TERCERO.- Los hechos alegados en la carta de extinción son totalmente inciertos [COMPLETAR]

CUARTO.- Se ejercita la acción para que se declare la improcedencia del despido puesto que la voluntad de la empleadora fue la de despedir al/la demandante, ya que el motivo alegado en ningún momento se ha producido objetivamente. Es de aplicación, asimismo, la presunción establecida en el art. 11.3 del RD núm. 1620/2011, al no constar de modo claro e inequívoco la causa por la cual la empleadora adopta la decisión extintiva, puesto que se hace una referencia genérica a [COMPLETAR] sin mayor concreción y habida cuenta que en ningún momento se puso a disposición de la demandante la indemnización establecida en el art. 11.2 del RD. 1620/2011, con carácter simultáneo a la comunicación.

QUINTO.- Con fecha [FECHA] se celebró el preceptivo acto de conciliación con el resultado de [ELEGIR: sin avenencia / sin efecto], acompañando como documentos [COMPLETAR] copia de la solicitud y certificación del acta.

SEXTO.- En base a lo expuesto, debe declarase la IMPROCEDENCIA del despido, con todas las consecuencias legales inherentes, debiendo condenar a la demanda a las responsabilidades que se deriven de la presente acción legal.

A los anteriores hechos les son aplicables los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- JURISDICCIÓN Y COMPETENCIA.- El TRIBUNAL ante el cual se interpone la presente demanda tiene jurisdicción bastante y competencias territorial, funcional y objetiva o material para el conocimiento y decisión de la litis, según lo que disponen, los artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica del Poder Judicial en relación con los artículos 1, 2 y 3 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LJS), y art. 13 del RD 1620/2011, de 14 de noviembre, quedando configuradas la competencia objetiva y territorial en los artículos 6 y 10 de la citada LJS.

SEGUNDO.- LEGITIMACIÓN.- Al tratarse de una relación laboral de carácter especial, de acuerdo con lo previsto en el artículo 1, puntos 1 y 2, de la mencionada LJS, esta parte tiene legitimación activa para interponer la presente demanda, del mismo modo que la tiene, en su calidad de pasiva, la parte demandada.

TERCERO.- PROCEDIMIENTO.- Dada la naturaleza de la acción emprendida por esta parte y a tenor de la pretensión que se postula, es procedente que la presente litis se encauce por las reglas que, al efecto, determinan los artículos 103 y siguientes de la LJS, y, en su caso, atendiendo a las normas subsidiarias a que aluden los artículos 80 y siguientes de la tan reiterada Ley, por así indicarlo con carácter general su artículo 102.

CUARTO.- PLAZO.- En cuanto a la acción, ésta dimana del derecho que tiene la parte actora, desconocido por el/la demandado/a y, por tanto, recubierto del interés legítimo a que se refiere el artículo 24.1 de la CE, habiendo reaccionado frente a la decisión extintiva dentro del plazo de caducidad de veinte días a que se refiere el artículo 103.1 de la LJS, en relación con los artículos 53, 55 y 59 ET.

QUINTO.- FONDO DEL ASUNTO.- El art. 11 del RD 1620/2011 establece que la relación laboral de carácter especial del servicio del hogar familiar puede extinguirse por las causas establecidas en el artículo 49.1 del Estatuto de los Trabajadores, aplicándose la normativa laboral común, habiendo optado la empleadora por el despido, al basarse en una causa que no existe objetivamente, pues los supuestos del art. 11.2 del RD 1620/2011 no concurren en ningún caso, y al no exteriorizarse de modo claro e inequívoco la causa por la que se adopta la decisión extintiva, a lo que se añade que el despido se presume asimismo al no haberse puesto a disposición la indemnización establecida en el art. 11.3 del citado RD 1620/2011. Por tanto, son de aplicación los artículos 54, 55 y 56 ET que establecen los requisitos y efectos del despido, debiendo ser calificado en este caso como improcedente según se ha expuesto en los hechos de esta demanda.

SEXTO.- COSTAS Y MULTA.- El artículo 97.3 de la Ley reguladora de la jurisdicción social establece que la sentencia, motivadamente, podrá imponer al litigante que no acudió justificadamente al acto de conciliación ante el servicio administrativo correspondiente o a mediación, de acuerdo con lo establecido en el artículo 83.3, así como al que obró de mala fe o con temeridad, una sanción pecuniaria dentro de los límites que se fijan en el apartado 4 del artículo 75. En tales casos, y cuando el condenado fuera el empresario, deberá abonar también los honorarios de los abogados y graduados sociales de la parte contraria que hubieren intervenido, hasta el límite de seiscientos euros, por lo que procede la imposición de costas a la parte demandada, así como la de una multa en su cuantía máxima, en el caso de que se opusiere a las legítimas pretensiones que en esta demanda se actúan.

Por todo lo expuesto,

Al TRIBUNAL SUPLICO: Que, teniendo por presentada esta demanda, con los documentos que se adjuntan a la misma, se sirva admitirla y, previos los trámites legales oportunos dicte Sentencia por la que se declare la IMPROCEDENCIA del despido de D./Dª [NOMBRE Y APELLIDOS], con efectos del día [FECHA], con todas las consecuencias legales inherentes, condenando a el/la demandado/a a estar y pasar por dicha declaración a todos los efectos y a todas las responsabilidades económicas que se deriven de la presente acción legal.

PRIMER OTROSÍ DIGO que se acompaña en anexo relación de documentos, debidamente foliados y con índice electrónico, para su debida localización y consulta.

Por lo que, SUPLICO AL TRIBUNAL tenga hecha esta manifestación a los efectos oportunos y por aportados los documentos relacionados en el anexo.

SEGUNDO OTROSÍ DIGO.- Que sin perjuicio de las pruebas que pueda proponer en el acto del juicio oral, al amparo de lo dispuesto en el art. 90.3 de la Ley reguladora de la jurisdicción social, interesa al derecho de esta parte que se practiquen las diligencias de citación y requerimiento de la siguiente prueba que esta parte pretende proponer en el juicio:

- INTERROGATORIO de el/la demandado/a en el acto de juicio, interesa se acuerde citar y se cite a la empleadora, a fin de que comparezcan al acto del juicio que se señale para responder las preguntas que se le formulen, bajo apercibimiento de tenerse por admitidos tácitamente los hechos para el caso de incomparecencia.

AL TRIBUNAL SUPLICA: Admita las diligencias de citación y requerimiento para la práctica de las pruebas que esta parte pretende proponer en el acto del juicio.

TERCER OTROSÍ DIGO.- Que a los efectos de este procedimiento se designan para la representación y defensa de esta parte, tal como consta en la escritura de poder que a este escrito se acompaña como documento número [Nº DE DOCUMENTO], a [COMPLETAR] del Ilustre Colegio de [COLEGIO], D./Dña. [NOMBRE Y APELLIDOS], quien suscribe conmigo esta demanda a todos los efectos prevenidos en el artículo 80.1.e) de la Ley reguladora de la jurisdicción social, designándose el domicilio de dichos profesionales a efectos de notificaciones y citaciones, sito en [LOCALIDAD], y cuyos datos de contacto son [COMPLETAR].

AL TRIBUNAL SUPLICO que tenga por hechas las anteriores manifestaciones a los efectos oportunos.

Es Justicia que respetuosamente solicito en [COMPLETAR]

Firma demandante y letrado(a)/procurador(a)/graduado(a) social colegiado(a)

D./Dña. [NOMBRE Y APELLIDOS] D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
