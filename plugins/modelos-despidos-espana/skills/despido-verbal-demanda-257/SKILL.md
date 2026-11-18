---
name: despido-verbal-demanda-257
description: "Redacta el escrito «Despido verbal: demanda» (formulario 257 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido verbal: demanda

> Formulario 0257 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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
- [ ] LOCALIDAD (4 veces)
- [ ] FECHA (6 veces)
- [ ] IMPORTE (2 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] Otros 20 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, y con domicilio en [LOCALIDAD], de»; «… despido improcedente, contra la empresa»; «…, dedicada a la actividad de»; «…, con domicilio social en [LOCALIDAD] de»; «…ervicios durante los siguientes períodos»; «…profesional de»; «…iante transferencia bancaria a la cuenta»; «…, en la sección»; «… trabajo las siguientes características:»; «…, en su calidad de»; «…despedido/a y que no volviera al trabajo»; «…— La empresa se dedica a la actividad de»; …

## Elecciones que hay que hacer

- la categoría / el grupo
- circunstancias de la producción / sustitución

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 55.1 del Estatuto de los Trabajadores
- artículos 55.4 y 56 del Estatuto de los Trabajadores
- artículo 55 del ET
- artículo 56 del ET
- artículo 90.1 LRJS
- Ley 36/2011
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

### Formulario 0257 · Despido verbal: demanda

- Año del modelo: 2013
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 39 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Demandante
Interposición
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Firmas

El despido verbal constituye una forma de extinción de la relación laboral no ajustada a las exigencias formales previstas en el artículo 55.1 del Estatuto de los Trabajadores, que exige la notificación escrita al trabajador, con expresión de los hechos que lo motivan y la fecha de efectos. No obstante, la ausencia de comunicación escrita no impide que el trabajador pueda ejercitar la acción de despido mediante la interposición de la oportuna demanda ante el tribunal competente.

En el caso de despido verbal, el trabajador debe concretar en la demanda la fecha de efectividad del despido, la forma en que se produjo (en este caso, verbalmente) y los hechos alegados por el empresario, haciendo mención suficiente de su contenido, aunque no exista comunicación escrita.

La carga de la prueba del despido verbal recae sobre el trabajador demandante, conforme al artículo 217.2 de la Ley de Enjuiciamiento Civil. El trabajador debe acreditar tanto la existencia de la relación laboral como el hecho mismo del despido, que constituye el presupuesto esencial de su pretensión.

Si el trabajador acredita el despido verbal, este será declarado improcedente por incumplimiento de los requisitos formales, con derecho a la readmisión o a la indemnización correspondiente y al abono de los salarios de tramitación, conforme a los artículos 55.4 y 56 del Estatuto de los Trabajadores. Si no se acredita el despido, la demanda será desestimada, pudiendo considerarse la extinción como una dimisión o abandono voluntario si así lo justifican los hechos.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], y con domicilio en [LOCALIDAD], de [COMPLETAR], ante la Sección de lo Social del Tribunal de Instancia comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito, en tiempo y forma legal, formulo demanda en reclamación por despido improcedente, contra la empresa [COMPLETAR], dedicada a la actividad de [COMPLETAR], con domicilio social en [LOCALIDAD] de [COMPLETAR], demanda que fundamento en los siguientes

HECHOS

Primero.— Que ingresé a prestar servicios por cuenta de la demandada con fecha [FECHA], habiendo prestado servicios durante los siguientes períodos [COMPLETAR] ostentando [ELEGIR: la categoría / el grupo] profesional de [COMPLETAR], percibiendo un salario mensual de [IMPORTE] euros, que incluida la prorrata de pagas extras asciende a [IMPORTE] euros mensuales, salario que se me abona mensualmente mediante transferencia bancaria a la cuenta [COMPLETAR]. Mi contrato es temporal por [ELEGIR: circunstancias de la producción / sustitución], estando prevista su duración hasta el [FECHA] o bien hasta que se convierta en indefinido, siendo mi jornada de [Nº] horas semanales.

Segundo.— Los servicios los presté en el centro de trabajo de la demandada, sito en [LOCALIDAD], en la sección [COMPLETAR], teniendo el trabajo las siguientes características:

[COMPLETAR]

Tercero.— El día [FECHA] D./Dña. [NOMBRE Y APELLIDOS], en su calidad de [COMPLETAR], me dijo que estaba despedido/a y que no volviera al trabajo [COMPLETAR].

Cuarto.— Que no ostento ni he ostentado en el año anterior a producirse el despido la calidad de representante legal ni sindical de los trabajadores.

Quinto.— Que el despido se ha producido sin entregarme la preceptiva carta, por lo que habrá de ser calificado de improcedente.

Sexto.— La empresa se dedica a la actividad de [COMPLETAR] y ocupa [COMPLETAR] de personas trabajadoras.

Séptimo Se aportan nóminas donde consta la antigüedad, categoría y salario manifestados e informe de vida laboral actualizado como documentos [COMPLETAR].

Octavo.— Se presentó papeleta de demanda de conciliación ante el servicio administrativo correspondiente el día [FECHA], habiéndose celebrado el preceptivo acto conciliatorio el día [FECHA] con el resultado de [COMPLETAR].

FUNDAMENTOS DE DERECHO

Primero.— Artículos 1, 2, 80, 103, 108 y 110 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social.

Segundo.— Artículo 55 del Texto Refundido de la Ley del Estatuto de los Trabajadores, aprobado por Real Decreto Legislativo 2/2015, de 23 octubre, referente a la forma y efectos del despido disciplinario, cuyo apartado 1 establece que el despido debe ser notificado por escrito en el que han de figurar los hechos que lo motivan y la fecha en que tendrá efecto, y en el presente supuesto no se me ha entregado carta de despido, por lo que en virtud de lo establecido en el apartado 4 del citado artículo 55 del ET, el despido es improcedente, con las consecuencias legales establecidas en el artículo 56 del ET.

Tercero.— Convenio Colectivo de [COMPLETAR].

Cuarto.— Todas las normas concordantes y complementarias aplicables al caso.

Por todo ello,

SUPLICO AL TRIBUNAL que, teniendo por presentada esta demanda con los documentos que acompaño, se sirva admitirla, tenga por formulada demanda por despido improcedente contra la empresa [COMPLETAR], se proceda a citar a las partes para los actos de conciliación y subsiguiente juicio, por el que en definitiva, seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba que expresamente se solicita, se dicte en su día sentencia estimando íntegramente la presente demanda y declarando improcedente el despido de que he sido objeto y condenando a la empresa demandada a que a su opción, y dentro del plazo de cinco días, me readmita en mi antiguo puesto de trabajo o me indemnice en la cuantía legal con el abono de los salarios dejados de percibir, todo ello junto a los demás pronunciamientos legales que proceda.

PRIMER OTROSÍ DIGO que, al acto de juicio compareceré asistido de Letrado que Me defienda, en conformidad con el artículo 21.2 de la Ley reguladora de la jurisdicción social, designando el domicilio profesional del Letrado/a D./Dña. [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

Por lo que,

SUPLICO AL TRIBUNAL que tenga por hecha tal manifestación a los efectos oportunos.

SEGUNDO OTROSÍ DIGO que, interesa al derecho de esta parte, y sin perjuicio de ampliación en el momento procesal oportuno, los siguientes MEDIOS DE PRUEBA:

- INTERROGATORIO del representante legal de la empresa demandada, que deberá ser citado en el domicilio indicado con los apercibimientos de rigor, incluso el de tenerle por confeso en caso de incomparecencia.

- DOCUMENTAL, consistente en que se requiera a la demandada para que aporte al acto del juicio la siguiente documentación: [COMPLETAR].

En cumplimiento de lo dispuesto por el artículo 90.1 LRJS, entiende esta parte que la prueba documental solicitada por medio del presente escrito es útil y directamente pertinente al objeto del presente juicio, pues resultará útil para acreditar [COMPLETAR].

- TESTIFICAL, consistente en que se cite a las siguientes personas:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD].

Por lo que,

SUPLICO AL TRIBUNAL que tenga por hecha tal manifestación a los a los efectos oportunos, admita y declare pertinentes las pruebas que se dejan propuestas, y acuerde cuanto sea preciso para llevarlas a efecto.

En caso de que la empresa no hubiera acudido al acto de conciliación estando debidamente citada:

TERCER OTROSÍ DIGO, que si la sentencia que en su día dicte coincidiera esencialmente con la pretensión contenida en la papeleta de conciliación, y en virtud de lo establecido en el art. 66 de la Ley reguladora de la jurisdicción social, deberán imponerse las costas del proceso a la empresa por no haber comparecido al acto de conciliación.

SUPLICA AL TRIBUNAL que tenga por hecha la anterior manifestación a los efectos legales oportunos.

Todo ello por ser de Justicia que pido en el lugar y fecha ut supra

Es justicia que pido en [LUGAR], a [FECHA].

Firma

════════════════════════════════════════════════════════════════════════
