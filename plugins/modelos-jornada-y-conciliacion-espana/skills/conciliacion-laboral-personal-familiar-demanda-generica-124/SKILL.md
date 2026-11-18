---
name: conciliacion-laboral-personal-familiar-demanda-generica-124
description: "Redacta el escrito «Conciliación laboral, personal y familiar: demanda genérica de derechos» (formulario 124 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Conciliación laboral, personal y familiar: demanda genérica de derechos

> Formulario 0124 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- El art. 37.6 ET (reducción por cuidado de menor con cáncer o enfermedad grave) fue modificado por el RDL 31/2026 (BOE-A-2026-21872, vigente desde el 23-10-2026): extensión más allá de los 23 y 26 años con discapacidad del 65 % o grado III de dependencia, tratamiento continuado sin hospitalización y disfrute por ambos progenitores de forma alternativa o simultánea.
- Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] NIF
- [ ] FECHA (5 veces)
- [ ] IMPORTE (3 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] LUGAR
- [ ] Otros 16 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, provisto/a de DNI (NIE)»; «…con domicilio en [LOCALIDAD] de»; «…, y domicilio en [LOCALIDAD], de»; «…halla encuadrado/a profesionalmente como»; «…tes se rige por el Convenio colectivo de»; «…egal vigente iba a ejercer el derecho de»; «…o derecho en las siguientes condiciones:»; «…ho, en base a los siguientes argumentos:»; «… actora que se le reconozca el derecho a»; «…e su derecho por aplicación del artículo»; «…anda se declare el derecho del actor/a a»; «…en las siguientes condiciones»; …

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- PRIMER OTROSÍ DIGO: Que a efectos de práctica de prueba de interrogatorio de parte interesa que se cite al leg…
- SEGUNDO OTROSÍ DIGO: Que a efectos de práctica de prueba interesa esta parte que en el acto del juicio se apor…
- TERCER OTROSÍ DIGO: Que compareceré al acto del juicio asistido/a de letrado/a que me dirija y defienda, desig…
- CUARTO OTROSÍ DIGO: Que, de conformidad con lo previsto en el artículo 64.1 LRJS esta modalidad procesal está …
- QUINTO OTROSÍ DIGO: Que esta parte aportará a los actos de conciliación y juicio su propuesta y alternativa de…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 139 de la LRJS
- artículo 139 de la Ley 36/2011
- artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica 6/1985
- artículos 2, 6 y 10 LRJS
- artículo 17.1 LRJS
- artículo 139 LRJS
- artículo 91.2 LRJS
- artículo 64.1 LRJS

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

### Formulario 0124 · Conciliación laboral, personal y familiar: demanda genérica de derechos

- Año del modelo: 2022
- Revisión 17-11-2026: 5 párrafos opcionales señalados; 35 campos de relleno marcados en blanco
- Avisos de la revisión: El art. 37.6 ET (reducción por cuidado de menor con cáncer o enfermedad grave) fue modificado por el RDL 31/2026 (BOE-A-2026-21872, vigente desde el 23-10-2026): extensión más allá de los 23 y 26 años con discapacidad del 65 % o grado III de dependencia, tratamiento continuado sin hospitalización y disfrute por ambos progenitores de forma alternativa o simultánea. · Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
HECHOS
Fundamentos jurídicos
Firmas

Las demandas en materia de derechos de conciliación de la vida familiar y laboral deben tramitarse por la modalidad procesal especial regulada en el artículo 139 de la LRJS. Este procedimiento es de carácter urgente y preferente, y está específicamente diseñado para resolver discrepancias entre la persona trabajadora y la empresa en relación con el ejercicio de los derechos de conciliación reconocidos legal o convencionalmente, incluyendo la adaptación de jornada, la concreción horaria y otras medidas análogas.

Esta modalidad procesal se utiliza en supuestos en que se reclaman asuntos sobre reducción de jornada por lactancia, reducción de jornada por cuidado de hijo o familiar dependiente, suspensión del contrato por nacimiento, adopción, guarda con fines de adopción o acogimiento familiar, excedencia por cuidado de hijo o familiar, distribución de horario o cambio de turno, etc. Pero no corresponde a todas las cuestiones que puedan plantearse, sino únicamente respecto a la concreción horaria y la determinación del período de disfrute; otras cuestiones de contenido diverso sobre la materia (retribución, reparto del derecho, alternancia de su ejercicio, el derecho en sí mismo, etc.), deberán tramitarse mediante el proceso ordinario.

Este procedimiento es igualmente aplicable al ejercicio de los derechos de la trabajadora víctima de violencia de género establecidos en la ley, a la reducción de la jornada de trabajo con disminución proporcional del salario y a la reordenación del tiempo de trabajo, a través de la adaptación del horario, de la aplicación del horario flexible o de otras formas de ordenación del tiempo de trabajo que se utilicen en la empresa.

La demanda debe contener la identificación clara del derecho de conciliación que se reclama (por ejemplo, concreción horaria, adaptación de jornada, teletrabajo, cambio de centro de trabajo, etc.), los hechos en los que se fundamenta la pretensión, la referencia a la negativa o disconformidad empresarial y, en su caso, la cuantificación de los daños y perjuicios reclamados. Es relevante que la persona trabajadora y la empresa lleven al acto de conciliación y al juicio sus respectivas propuestas y alternativas de concreción, pudiendo acompañar informes de los órganos paritarios o de seguimiento de los planes de igualdad de la empresa.

En la demanda sobre derechos de conciliación puede acumularse la acción de daños y perjuicios causados al trabajador, exclusivamente por los derivados de la negativa del derecho o de la demora en la efectividad de la medida, de los que el empresario podrá exonerarse si hubiere dado cumplimiento, al menos provisional, a la medida propuesta por el trabajador.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], provisto/a de DNI (NIE) [COMPLETAR] con domicilio en [LOCALIDAD] de [COMPLETAR], ante ese Tribunal comparezco y, como mejor en Derecho proceda,

DIGO:

Que mediante el presente escrito vengo a interponer demanda de reclamación de derechos de conciliación de la vida laboral, personal y familiar reconocidos legal o convencionalmente al amparo del artículo 139 de la Ley 36/2011, de 10 de octubre, Reguladora de la Jurisdicción Social (LRJS) contra [ACTO O RESOLUCIÓN], con NIF [NIF], y domicilio en [LOCALIDAD], de [COMPLETAR].

La presente demanda se fundamenta en los siguientes

HECHOS

Primero.– Circunstancias contractuales entre las partes

El/La actor/a inició su relación laboral con la demandada en fecha [FECHA].

El/La actor/a se halla encuadrado/a profesionalmente como [COMPLETAR].

Su salario bruto con inclusión de pagas extraordinarias es de [IMPORTE] euros mensuales.

La relación laboral entre las partes se rige por el Convenio colectivo de [COMPLETAR].

Segundo.– Situación familiar de la parte actora

Tercero.– Comunicación a la empresa del ejercicio del derecho legal

En fecha [FECHA] comuniqué a la empresa que, de conformidad con el marco legal vigente iba a ejercer el derecho de [COMPLETAR].

En dicha comunicación puse en conocimiento de la demandada que iba a ejercer dicho derecho en las siguientes condiciones: [COMPLETAR].

Cuarto.– Respuesta empresarial

En fecha [FECHA] la demandada me remitió comunicación de fecha [FECHA] en la que se me manifestaba su oposición al ejercicio del mentado derecho, en base a los siguientes argumentos:

[COMPLETAR]

Quinto.– Oposición a los motivos aducidos por la empresa

Esta parte se opone a los razonamientos que se contienen en la referida comunicación, por cuanto

Sexto.– Pretensión de la demanda

En consecuencia, es objeto de la presente demanda y constituye pretensión de la parte actora que se le reconozca el derecho a [COMPLETAR]

Séptimo.– Indemnización por daños y perjuicios

Junto con la anterior petición se acumula la reclamación de la indemnización por los daños y perjuicios causados por la negativa del derecho o la demora en la medida por parte de la demandada, que señalo en la cuantía de [IMPORTE] €.

Dicha cantidad se determina en función de los siguientes parámetros de determinación:

Fundamentos jurídicos

Primero.– Jurisdicción y competencia

El conocimiento de esta demanda es competencia de ese tribunal, de conformidad con las reglas conformadoras de la jurisdicción y la competencia material y territorial aplicables, en aplicación de los artículos 2.1, 3.1, 4, 9.1 y 9.5 de la Ley Orgánica 6/1985, de 1 de julio, del Poder Judicial y los artículos 2, 6 y 10 LRJS.

Segundo.– Legitimación activa y pasiva

Ostenta legitimación activa el firmante en su condición de persona trabajadora y pasiva la demandada en su condición de empleador, de conformidad con el artículo 17.1 LRJS.

Tercero.– Modalidad procesal adecuada

Tratándose de una demanda resultan de aplicación las especificidades contempladas en el artículo 139 LRJS.

Cuarto.– Normativa sustantiva

En atención a los motivos expuestos anteriormente, la parte actora tiene derecho a la concreción horaria del ejercicio de su derecho por aplicación del artículo [COMPLETAR].

Por lo expuesto

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA

Que, teniendo por presentado este escrito con sus copias y documentos adjuntos, se sirva admitir la demanda y, tras los trámites procesales oportunos, se dicte sentencia por la que, con estimación de la demanda se declare el derecho del actor/a a [COMPLETAR] en las siguientes condiciones [COMPLETAR], condenando a la demandada a estar y pasar por dicha declaración con todas las consecuencias legales inherentes, así como al abono a la parte actora de la cantidad de [IMPORTE] € en concepto de los daños y perjuicios causados con su conducta.

[OPCIONAL — incluir si procede]

PRIMER OTROSÍ DIGO: Que a efectos de práctica de prueba de interrogatorio de parte interesa que se cite al legal representante de la empresa para que comparezca personalmente al acto del juicio, con la advertencia de que en caso de inasistencia sin justa causa se le podrá tener por confeso de los hechos de la presente demanda, de conformidad con aquello previsto en el artículo 91.2 LRJS.

[OPCIONAL — incluir si procede]

SEGUNDO OTROSÍ DIGO: Que a efectos de práctica de prueba interesa esta parte que en el acto del juicio se aporte por la demandada la siguiente documentación:

[COMPLETAR]

[OPCIONAL — incluir si procede]

TERCER OTROSÍ DIGO: Que compareceré al acto del juicio asistido/a de letrado/a que me dirija y defienda, designando al efecto a [COMPLETAR], con domicilio profesional en [LOCALIDAD] de [COMPLETAR], teléfono [TELÉFONO], fax [COMPLETAR] y dirección de correo electrónico [CORREO ELECTRÓNICO], a quien confiero poder tan amplio como en Derecho proceda a efectos de representación.

[OPCIONAL — incluir si procede]

CUARTO OTROSÍ DIGO: Que, de conformidad con lo previsto en el artículo 64.1 LRJS esta modalidad procesal está exenta de conciliación administrativa previa.

[OPCIONAL — incluir si procede]

QUINTO OTROSÍ DIGO: Que esta parte aportará a los actos de conciliación y juicio su propuesta y alternativa de concreción del derecho postulado, en relación a lo manifestado en el anterior hecho sexto, solicitando al tribunal que se requiera a la empresa demandada que aporte idéntica documentación. Asimismo,

En [LUGAR], a [FECHA].

Firma de la parte actora	Firma representante
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
