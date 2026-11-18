---
name: despido-nulo-vulnerar-derechos-conciliacion-demanda-369
description: "Redacta el escrito «Despido nulo por vulnerar derechos de conciliación: demanda» (formulario 369 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido nulo por vulnerar derechos de conciliación: demanda

> Formulario 0369 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (2 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] NIF
- [ ] FECHA (5 veces)
- [ ] IMPORTE
- [ ] NÚMERO (2 veces)
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…egalmente establecido, contra la empresa»; «…, NIF [NIF], C.C.C.»; «…a de aplicación el convenio colectivo de»; «…en el centro de trabajo de»; «…, en el grupo profesional de»; «… desglose es el siguiente: Salario Base:»; «…Plus:»; «…ulo, puesto que en realidad el motivo es»; «…manda por despido nulo contra la empresa»; «…en»; «…o. - Nóminas de los últimos doce meses -»; «…ón de que resultará útil para acreditar:»

## Elecciones que hay que hacer

- NIF / NIE
- disciplinario / por causas objetivas
- sin avenencia / sin efecto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- - INTERROGATORIO del representante legal de la empresa demandada, que deberá ser citado en el domicilio indica…
- - DOCUMENTAL, consistente en que se requiera a la empresa demandada para que aporte a juicio los siguientes do…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 55 ET
- art. 55.6 ET
- artículo 56 del Estatuto de los Trabajadores
- artículo 90.1 de la LRJS
- Ley Orgánica 1/2025
- Ley 36/2011

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

### Formulario 0369 · Despido nulo por vulnerar derechos de conciliación: demanda

- Año del modelo: 2016
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 2 párrafos opcionales señalados; 28 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Nulidad objetiva: los arts. 53.4.b) y 55.5.b) ET (redacción LO 1/2025, DF 26.ª, en vigor el 3-4-2025) incluyen permisos del 37.3.b), 4, 5 y 6, adaptaciones del 34.8 y excedencia del 46.3; el art. 55.5.a) incluye el permiso parental del 48 bis.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de demanda en reclamación de despido nulo en los supuestos establecidos en el art. 55.5.a), b) y c) del Estatuto de los trabajadores, de conformidad con el procedimiento específico establecido en los artículos 103 y siguientes de la Ley reguladora de la jurisdicción social.

Sera nulo el despido, salvo que se declare la procedencia por otros motivos, en los siguientes supuestos (art. 55 ET):

a) El de las personas trabajadoras durante los periodos de suspensión del contrato de trabajo por nacimiento, adopción, guarda con fines de adopción, acogimiento, riesgo durante el embarazo, riesgo durante la lactancia natural a que se refiere el artículo 45.1.d) y e), disfrute del permiso parental a que se refiere el artículo 48 bis, o por enfermedades causadas por embarazo, parto o lactancia natural, o cuando se notifique la decisión en una fecha tal que el plazo de preaviso concedido finalice dentro de dichos periodos.

b) El de las trabajadoras embarazadas, desde la fecha de inicio del embarazo hasta el comienzo del periodo de suspensión a que se refiere la letra a); el de las personas trabajadoras que hayan solicitado uno de los permisos a los que se refieren los apartados 3.b), 4, 5 y 6 del artículo 37, o estén disfrutando de ellos, o hayan solicitado o estén disfrutando de las adaptaciones de jornada previstas en el artículo 34.8 o la excedencia prevista en el artículo 46.3; y el de las personas trabajadoras víctimas de violencia de género o de violencia sexual, por el ejercicio de su derecho a la tutela judicial efectiva o de los derechos reconocidos en esta ley para hacer efectiva su protección o su derecho a la asistencia social integral.

c) El de las personas trabajadoras después de haberse reintegrado al trabajo al finalizar los periodos de suspensión del contrato por nacimiento, adopción, guarda con fines de adopción o acogimiento, a que se refiere el artículo 45.1.d), siempre que no hubieran transcurrido más de doce meses desde la fecha del nacimiento, la adopción, la guarda con fines de adopción o el acogimiento.

El efecto del despido nulo es la readmisión inmediata de la persona trabajadora, con abono de los salarios dejados de percibir (art. 55.6 ET).

Actualizado según las modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con [ELEGIR: NIF / NIE] número [DNI/NIE] y domicilio en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante el Tribunal de Instancia comparece y, como mejor proceda en Derecho, DICE:

Que mediante el presente escrito, interpone DEMANDA DE DESPIDO NULO, en tiempo y forma legalmente establecido, contra la empresa [COMPLETAR], NIF [NIF], C.C.C. [COMPLETAR], con domicilio en [LOCALIDAD], en la persona de su legal representante.

Se basa la demanda en los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que el/la demandante ha venido prestando servicios en la aludida empresa, a la que le resulta de aplicación el convenio colectivo de [COMPLETAR], desde el día [FECHA] en el centro de trabajo de [COMPLETAR], en el grupo profesional de [COMPLETAR], percibiendo un salario bruto mensual de [IMPORTE] euros, incluida la prorrata de pagas extras, que se abona mediante transferencia bancaria y cuyo desglose es el siguiente:

Salario Base: [COMPLETAR]

Plus: [COMPLETAR]

SEGUNDO.- Que, con fecha [FECHA], la empresa demandada despidió al/a la compareciente a través de la carta que a la presente demanda se acompaña como DOC. nº1, con efectos desde el [FECHA], alegando

TERCERO.- Que en la fecha en la que se le comunicó el despido

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Si en la fecha de despido la persona trabajadora tenía el contrato suspendido por nacimiento, adopción, guarda con fines de adopción o acogimiento)
— (Si en la fecha de despido la persona trabajadora tenía el contrato suspendido por riesgo durante el embarazo o durante la lactancia natural)
— (Si en la fecha de despido la persona trabajadora estaba de baja por enfermedad derivada de embarazo, parto o lactancia natural)
— (Si en la fecha de despido la persona trabajadora estaba embarazada)
— (Si en la fecha de despido la persona trabajadora estaba disfrutando del permiso por cuidado del lactante)
— (Si en la fecha de despido la persona trabajadora estaba disfrutando del permiso parental)
— (Si en la fecha del despido la persona trabajadora había comunicado su intención de disfrutar del permiso parental)
— (Si la persona trabajadora estaba disfrutando de una adaptación de jornada por conciliación de vida familiar y laboral)
— (Si en la fecha del despido la persona trabajadora había comunicado su intención de disfrutar de una adaptación de jornada por conciliación de vida familiar y laboral)
— (Si en la fecha de despido la persona trabajadora había comunicado su intención de disfrutar de una excedencia por cuidado de hijo o familiar)
— (Si en la fecha de despido la persona trabajadora se encontraba en situación de excedencia por cuidado de hijo o familiar)
— (Si en la fecha de despido la persona trabajadora estaba disfrutando de una reducción de jornada por cuidado de hijo, persona con discapacidad, familiar, menor con cáncer o enfermedad grave)
— (Si en la fecha de despido la persona trabajadora había solicitado su derecho a la asistencia social integral como víctima de violencia de género o de violencia sexual)
— (Si en la fecha de despido no habían transcurrido 12 meses desde que se había reincorporado al trabajo tras finalizar la suspensión de su contrato por nacimiento, adopción, guarda con fines de adopción o acogimiento)

Se acompaña como DOC. nº [NÚMERO], documento justificativo de los extremos señalados.

CUARTO.- Que los hechos alegados en la carta de despido no son ciertos, ocultándose como despido [ELEGIR: disciplinario / por causas objetivas] un despido que debe calificarse como nulo, puesto que en realidad el motivo es [COMPLETAR]. Los hechos alegados por la empresa son totalmente inciertos, carecen de fundamento o acreditación alguna y, además, la carta no cumple los requisitos formales mínimos exigibles legalmente.

QUINTO.- Que el día [FECHA] se celebró ante el Servicio de Mediación, Arbitraje y Conciliación el preceptivo acto de conciliación, de conformidad con los artículos 63 y siguientes de la Ley reguladora de la jurisdicción social, con el resultado de [ELEGIR: sin avenencia / sin efecto], según se acredita con la copia certificada del acta que a la presente demanda se acompaña como DOC. nº [NÚMERO].

A los anteriores hechos les son de aplicación los siguientes,

FUNDAMENTOS DE DERECHO

I.- Artículos 1, 2 a), 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, siendo competente dicho Tribunal de Instancia en razón de la materia y territorio.

II.- Artículo 55.5 del Estatuto de los trabajadores.

III.- Demás fundamentos legales y jurisprudenciales que se alegarán en el momento procesal oportuno.

En virtud de cuanto antecede es por lo que,

SUPLICA AL TRIBUNAL DE INSTANCIA que, teniendo por presentado este escrito con sus copias y documentos que se adjuntan, se digne admitirlo, tenga por formulada demanda por despido nulo contra la empresa [COMPLETAR], convoque a las partes para los actos de conciliación y juicio en debida forma, por el que, seguido de los trámites legales oportunos, dicte en su día sentencia estimando íntegramente la presente demanda,

Declare nulo el despido, condenando a la empresa demandada a que, conforme a lo dispuesto en el artículo 56 del Estatuto de los Trabajadores, readmita a este demandante en idénticas condiciones en las que venía prestando servicios, con abono de los salarios dejados de percibir, desde la fecha de efectos del despido hasta la efectiva reincorporación.

PRIMER OTROSI DICE: Que al acto de juicio este/a demandante comparecerá asistido de Letrado/a que le defienda, en conformidad con el artículo 21.2 de la Ley reguladora de la jurisdicción social, designando el domicilio profesional del Letrado/a D./Dña. [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

SUPLICA AL TRIBUNAL que tenga por hecha tal manifestación, a los efectos oportunos.

SEGUNDO OTROSI DICE: Que interesan al derecho de esta parte, y sin perjuicio de ampliación en el momento procesal oportuno, los siguientes medios de prueba:

[OPCIONAL — incluir si procede]

- INTERROGATORIO del representante legal de la empresa demandada, que deberá ser citado en el domicilio indicado, para que bajo juramento indecisorio absuelva las posiciones que se formularán y bajo apercibimiento de tenerle por confeso si no compareciere.

[OPCIONAL — incluir si procede]

- DOCUMENTAL, consistente en que se requiera a la empresa demandada para que aporte a juicio los siguientes documentos:

- Copia del contrato de trabajo.
- Nóminas de los últimos doce meses
- [COMPLETAR].

En cumplimiento de lo dispuesto por el artículo 90.1 de la LRJS entiende esta parte que la prueba documental solicitada por medio del presente escrito es útil y directamente pertinente al objeto del presente juicio, en razón de que resultará útil para acreditar: [COMPLETAR].

Por lo que,

SUPLICA AL TRIBUNAL DE INSTANCIA que tenga por hecha tal manifestación a los efectos oportunos, admita y declare pertinentes las pruebas que se dejan propuestas y acuerde cuanto sea preciso para llevarlas a efecto.

Es de Justicia que pide en [LUGAR], a [FECHA].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
