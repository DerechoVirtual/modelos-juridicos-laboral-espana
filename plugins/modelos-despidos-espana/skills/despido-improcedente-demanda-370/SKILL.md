---
name: despido-improcedente-demanda-370
description: "Redacta el escrito «Despido improcedente: demanda» (formulario 370 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido improcedente: demanda

> Formulario 0370 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (2 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] NIF
- [ ] LUGAR (2 veces)
- [ ] FECHA (3 veces)
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…3 de octubre. IV.- Convenio colectivo de»; «…, condenando a la»; «…en»; «…TAL, consistente en que se requiera a la»; «…a de despido disciplinario, notificada a»; «…oras. • Vida laboral de la empresa desde»; «…. •»; «…. • [COMPLETAR]. •»; «…a [FECHA]. D./Dña. [NOMBRE Y APELLIDOS]:»

## Elecciones que hay que hacer

- 54 a 56 / 49.1 g y 56 / 45 y 46

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Despido improcedente por jubilación del empresario o reincorporación tras excedencia / Despido improcedente por causas disciplinarias / Despido improcedente de representante legal o sindical / Demanda de despido improcedente contra una Administración pública / Despido improcedente por resolución de contrato temporal / Despido de persona afiliada a un sindicato sin d

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- - INTERROGATORIO del representante legal de la demandada para que, bajo juramento indecisorio, conteste a las …
- - DOCUMENTAL, consistente en que se requiera a la [COMPLETAR] demandada para que aporte a juicio los siguiente…
- - TESTIFICAL, para que los testigos que a continuación se relacionan, sean citados por vía judicial, en los do…
- TERCER OTROSÍ DICE, que esta parte ha intentado cumplir con los requisitos legalmente exigidos para la present…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 103.1 LRJS
- artículo 103.1 de la Ley 36/2011
- artículos 66.3 y 97.3 de la Ley 36/2011
- artículo 90.1 de la LRJS
- art. 231 de la LEC
- Real Decreto Legislativo 2/2015

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

### Formulario 0370 · Despido improcedente: demanda

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 23 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de demanda en reclamación de despido improcedente, de conformidad con el procedimiento específico establecido en los artículos 103 y siguientes de la Ley reguladora de la jurisdicción social, que refunde los siguientes supuestos que puede seleccionar individualmente:

- Despido improcedente derivado de extinción por jubilación del empresario sin cierre empresarial inmediato o en un plazo razonable.

- No aceptación por parte de la empresa de la reincorporación tras la excedencia.

- Despido improcedente por razones disciplinarias.

- Despido improcedente de representante legal de las personas trabajadoras.

- Demanda de despido improcedente contra una Administración Pública.

- Despido improcedente por resolución de contrato temporal (por circunstancias de la producción o de sustitución).

- Despido de persona afiliada a un sindicato sin dar audiencia a los/las delegados/as sindicales

En virtud del art. 103.1 LRJS, el trabajador podrá reclamar contra el despido, dentro de los veinte días hábiles siguientes a aquel en que se hubiera producido. Dicho plazo será de caducidad a todos los efectos y no se computarán los sábados, domingos y los festivos en la sede del órgano jurisdiccional.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: Es una demanda: aún no hay plaza asignada. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con NIF/NIE número [DNI/NIE] y domicilio en [LOCALIDAD], teléfono [TELÉFONO], y correo electrónico [CORREO ELECTRÓNICO], ante el Tribunal de Instancia comparece y, como mejor proceda en Derecho, DICE:

Que, mediante el presente escrito y dentro del plazo de veinte días establecido por el artículo 103.1 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, interpone DEMANDA POR DESPIDO IMPROCEDENTE, en la forma legalmente establecida, contra [ACTO O RESOLUCIÓN], con NIF [NIF] y domicilio en [LOCALIDAD], en la persona de su legal representante, en base a los siguientes hechos y fundamentos legales:

HECHOS

[ELEGIR UNA OPCIÓN Y REDACTARLA: Despido improcedente por jubilación del empresario o reincorporación tras excedencia / Despido improcedente por causas disciplinarias / Despido improcedente de representante legal o sindical / Demanda de despido improcedente contra una Administración pública / Despido improcedente por resolución de contrato temporal / Despido de persona afiliada a un sindicato sin dar audiencia a los/las delegados/as sindicales — el texto de cada opción no venía en el formulario original]

A los anteriores hechos les resultan de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.-Artículos 1, 2 a), 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, siendo competente dicho Tribunal de Instancia en razón de la materia y territorio.

II.- En cuanto al procedimiento, los artículos 63 y siguientes y 103 a 113 de la misma Ley procesal.

III.- En cuanto a la reclamación sustantiva, son de aplicación los artículos [ELEGIR: 54 a 56 / 49.1 g y 56 / 45 y 46] del Texto refundido de la Ley del Estatuto de los trabajadores, aprobado por Real Decreto Legislativo 2/2015, de 23 de octubre.

IV.- Convenio colectivo de [COMPLETAR].

Demás fundamentos legales y jurisprudenciales que expondré en el momento procesal oportuno.

En virtud de lo expuesto,

SUPLICA AL TRIBUNAL que, teniendo por presentado este escrito con sus copias y documentos que se adjuntan, se sirva admitirlo, tenga por formulada demanda por DESPIDO IMPROCEDENTE contra [ACTO O RESOLUCIÓN], cite a las partes para los actos de conciliación y juicio en debida forma, y, seguidos los trámites legales oportunos, dicte en su día sentencia estimando íntegramente la presente demanda, declarando improcedente el despido de D./Dña. [NOMBRE Y APELLIDOS], condenando a la [COMPLETAR] demandada a que, a su elección y conforme a lo dispuesto en el artículo 56 del Estatuto de los trabajadores, le/la readmita en su antiguo puesto de trabajo, abonándole, en este caso, los salarios dejados de percibir desde el despido hasta la efectiva readmisión, o le indemnice en la cuantía legalmente establecida, con todo cuanto más proceda en Derecho.

 Asimismo solicitamos que se condene a la demandada al pago de las costas, así como que se la imponga multa por temeridad al amparo de los artículos 66.3 y 97.3 de la Ley 36/2011, reguladora de la jurisdicción social, por no haber acudido al acto de conciliación.

Por ser de Justicia que se pide en [LUGAR], a [FECHA].

PRIMER OTROSI DICE: Que al acto de juicio este/a demandante comparecerá asistido de Letrado que le defienda, en conformidad con el artículo 21.2 de la Ley reguladora de la jurisdicción social, designando el domicilio profesional del Letrado D./Dña. [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

SUPLICA AL TRIBUNAL que tenga por hecha tal manifestación, a los efectos oportunos.

SEGUNDO OTROSI DICE: Que interesan al derecho de esta parte, y sin perjuicio de ampliación en el momento procesal oportuno, que se practiquen los siguientes MEDIOS DE PRUEBA:

[OPCIONAL — incluir si procede]

- INTERROGATORIO del representante legal de la demandada para que, bajo juramento indecisorio, conteste a las preguntas que se le formularán en el acto del juicio, para lo que deberá ser citado en el domicilio indicado, bajo apercibimiento de tenerle por confeso si no compareciere.

[OPCIONAL — incluir si procede]

- DOCUMENTAL, consistente en que se requiera a la [COMPLETAR] demandada para que aporte a juicio los siguientes documentos:

• Copia del contrato de trabajo.
• Nóminas de los últimos doce meses.
• Carta de despido disciplinario, notificada a [COMPLETAR] en fecha [FECHA] y notificación de la misma a los representantes de las personas trabajadoras.
• Vida laboral de la empresa desde [COMPLETAR].
• [COMPLETAR].
• [COMPLETAR].

[OPCIONAL — incluir si procede]

- TESTIFICAL, para que los testigos que a continuación se relacionan, sean citados por vía judicial, en los domicilios que se indican, para ser examinados en dicho acto de juicio:

En cumplimiento de lo dispuesto por el artículo 90.1 de la LRJS entiende esta parte que la prueba documental solicitada por medio del presente escrito es útil y directamente pertinente al objeto del presente juicio, en razón de que resultará útil para acreditar:

SUPLICA AL TRIBUNAL tenga por hecha tal manifestación a los efectos oportunos, admita y declare pertinentes las pruebas que se dejan propuestas, y acuerde lo necesario para su práctica.

[OPCIONAL — incluir si procede]

TERCER OTROSÍ DICE, que esta parte ha intentado cumplir con los requisitos legalmente exigidos para la presentación de este escrito y, en caso de haber incurrido errores involuntarios, interesa que, de conformidad con lo establecido en el art. 231 de la LEC, se acuerde la posibilidad de la correspondiente subsanación dentro del plazo que la ley determina para tal fin.

SUPLICO AL TRIBUNAL que tenga por hecha la anterior manifestación a los efectos legales oportunos.

Es de Justicia que pide en [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
