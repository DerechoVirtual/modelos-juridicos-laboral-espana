---
name: demanda-empresa-contra-responsabilidad-pension-190
description: "Redacta el escrito «Demanda de la empresa contra la responsabilidad por pensión de jubilación en contrato de relevo» (formulario 190 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda de la empresa contra la responsabilidad por pensión de jubilación en contrato de relevo

> Formulario 0190 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- La imputación de responsabilidad empresarial en prestaciones es materia del art. 2.o) LRJS (modalidad de prestaciones, arts. 140 y siguientes, con reclamación previa del art. 71), no la impugnación de actos del art. 151: revisar la coherencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] FECHA (14 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] Nº DE DOCUMENTO (2 veces)
- [ ] arts. 2.o), 6 y 10 Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ribunales, en representación de sociedad»; «…o/a del Iltre. Colegio de la Abogacía de»; «…anule la resolución del INSS de fecha de»; «…tencia de responsabilidad empresarial de»; «…amiento. Por ser de justicia que pido en»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 12.6 ET
- artículo 12.6 y 7 del ET
- art. 215.2 LGSS
- art. 12.6 y 12.7 del Estatuto de los Trabajadores
- art. 215.2 de la LGSS
- art. 9.5 LOPJ
- arts. 2.o), 6 y 10 Ley 36/2011
- art. 71 de la Ley 36/2011
- art. 215 LGSS
- Real Decreto Legislativo 2/2015
- Real Decreto Legislativo 8/2015

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

### Formulario 0190 · Demanda de la empresa contra la responsabilidad por pensión de jubilación en contrato de relevo

- Año del modelo: 2020
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 34 campos de relleno marcados en blanco
- Avisos de la revisión: La imputación de responsabilidad empresarial en prestaciones es materia del art. 2.o) LRJS (modalidad de prestaciones, arts. 140 y siguientes, con reclamación previa del art. 71), no la impugnación de actos del art. 151: revisar la coherencia.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Demandante
Interposición
HECHOS
FUNDAMENTOS DE DERECHO
Petitum
Firmas

Con arreglo al art. 12.6 ET, en supuestos de jubilación parcial anticipada la empresa debe concertar un contrato de relevo indefinido y a tiempo completo, con un trabajador desempleado o con contrato de duración determinada en la empresa; y conforme al art. 215.2.e LGSS, debe mantener dicho contrato al menos hasta dos años después de la jubilación plena del trabajador relevado, so pena de responsabilidad en el reintegro de la pensión parcial si incumple tal obligación.

La presente demanda tiene por objeto la impugnación de la resolución del INSS que declara a la empresa responsable del reintegro de la pensión de jubilación parcial de un trabajador, por supuestas irregularidades en el contrato de relevo celebrado.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, en representación de sociedad [COMPLETAR], según acredito mediante copia digitalizada de poder que acompaño, y bajo la dirección letrada de D./Dña. [NOMBRE Y APELLIDOS], Abogado/a del Iltre. Colegio de la Abogacía de [COMPLETAR], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho,

DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA EN IMPUGNACIÓN DE LA RESOLUCIÓN ADMINISTRATIVA DE FECHA [FECHA], la cual declara la responsabilidad de la empresa que represento en el pago de la pensión de jubilación parcial, la cual dirijo contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], y contra la TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], la cual deberá tramitarse por la modalidad procesal de impugnación de actos administrativos en materia laboral y de Seguridad Social, a fin de que se anule dicha resolución en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

HECHOS

PRIMERO.- La resolución administrativa impugnada declara la responsabilidad de la empresa que represento con motivo de la contratación de D./Dña. [NOMBRE Y APELLIDOS] con quien la empresa formalizó en fecha [FECHA] un contrato de relevo para sustituir a la persona trabajadora D./Dña. [NOMBRE Y APELLIDOS] que, por acceder a la jubilación parcial, había reducido su jornada en un %.

SEGUNDO.- Por resolución del INSS, de fecha [FECHA] se declaró la responsabilidad de la empresa a que represento en el pago de la pensión de jubilación parcial de D./Dña. [NOMBRE Y APELLIDOS] durante el periodo comprendido entre el día [FECHA] y del día [FECHA], por un importe de [IMPORTE] euros (acompaño como documento número [Nº DE DOCUMENTO] copia de la citada resolución).

TERCERO.- La declaración de responsabilidad se funda en que la persona trabajadora relevista D./Dña. [NOMBRE Y APELLIDOS] estuvo de alta en el RETA en el periodo comprendido entre el día [FECHA] y el día [FECHA] No obstante, y tal como consta en el expediente, la persona trabajadora relevista tenía concertado anteriormente un contrato de trabajo temporal con la empresa que represento, de fecha [FECHA], por lo que reunía los requisitos establecidos en el artículo 12.6 y 7 del ET y en el art. 215.2 LGSS para ser sujeto de un contrato de relevo, sin que constituya obstáculo alguno que el relevista figurase de alta en el RETA.

CUARTO.- Disconforme con dicha resolución, y de acuerdo a los hechos expresados, esta parte interpuso reclamación administrativa previa en fecha [FECHA] en la cual exponían, en síntesis, los siguientes motivos de impugnación:

• Que el art. 12.6 y 12.7 del Estatuto de los Trabajadores permiten que el contrato de relevo se celebre con trabajador que tenga concertado con la empresa un contrato de duración determinada, sin exigir exclusividad ni prohibir el desempeño de otras actividades.

• Que el art. 215.2 de la LGSS no añade requisito alguno en cuanto a incompatibilidades del relevista con otras actividades, sino que se centra en la naturaleza (indefinida y a tiempo completo) y duración del contrato de relevo, así como en su mantenimiento hasta, al menos, los dos años posteriores a la jubilación plena del relevado.

QUINTO.- La reclamación previa interpuesta fue desestimada por resolución del INSS de fecha [FECHA], que declara la responsabilidad de la empresa, notificada el día [FECHA], y que ahora se impugna por medio de la presente demanda (acompaño como documentos nº [Nº DE DOCUMENTO] escrito de reclamación previa y copia de la resolución de fecha [FECHA]).

FUNDAMENTOS DE DERECHO

PRIMERO.- En cuanto a los sujetos procesales y procedimiento, este órgano judicial al que se dirige la demanda tiene jurisdicción (art. 9.5 LOPJ) y competencia objetiva, funcional y territorial [arts. 2.o), 6 y 10 Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social] para conocer del juicio que se suscita, quedando válidamente constituida la relación jurídico-procesal por ostentar las partes legitimación activa y pasiva; por otra parte, la pretensión deducida debe seguirse por los trámites de la modalidad procesal de impugnación de actos administrativos en materia laboral y de Seguridad Social.

SEGUNDO.- El art. 71 de la Ley 36/2011, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad demandada.

TERCERO.- El art. 12 del texto refundido de la Ley del Estatuto de los Trabajadores, aprobado por Real Decreto Legislativo 2/2015, que regula el contrato a tiempo parcial y el contrato de relevo. El contrato de relevo se concierta para sustituir la jornada dejada vacante por el trabajador que accede a la jubilación parcial. Puede celebrarse con un trabajador en situación de desempleo o que tuviese concertado con la empresa un contrato de duración determinada. En los supuestos de jubilación parcial anticipada, el contrato de relevo debe ser indefinido y a tiempo completo, y mantenerse al menos hasta los dos años posteriores a la jubilación plena, so pena de responsabilidad empresarial.

CUARTO.- El art. 215 LGSS (Real Decreto Legislativo 8/2015) regula la jubilación parcial. Su apartado 2.e) establece: [NOTA DE REVISIÓN: Coherente con el art. 215.2.e) vigente (RDL 11/2024): relevo indefinido y a tiempo completo, mantenido al menos dos años tras extinguirse la jubilación parcial. Para hechos anteriores al 1-4-2025 se aplica la redacción entonces vigente (antes letra f). Fuente: art. 215.2 LGSS (red. RDL 11/2024, BOE-A-2024-26917).]

- Que, para acceder a la jubilación parcial antes de la edad ordinaria, la empresa debe concertar simultáneamente un contrato de relevo indefinido y a tiempo completo, que se mantendrá al menos durante los dos años posteriores a la extinción de la jubilación parcial.

- Que, si el contrato de relevo se extingue antes de que el jubilado parcial acceda a la jubilación plena y no se celebra un nuevo contrato de relevo “en los mismos términos”, el empresario será responsable del reintegro de la pensión percibida por el pensionista parcial.

Petitum

Por lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA que teniendo por presentado este escrito, con sus copias y documentos adjuntos, se sirva admitirlo, tenga por interpuesta DEMANDA EN IMPUGNACIÓN DE RESOLUCIÓN ADMINISTRATIVA en materia de Seguridad Social contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL y la TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL, y, previos los trámites legales oportunos, dicte en su día sentencia por la que se declare no conforme a Derecho y se anule la resolución del INSS de fecha de [COMPLETAR] así como la resolución de [FECHA] que desestima la reclamación previa, ambas por las que se declara la responsabilidad de la empresa demandante en el pago de la pensión de jubilación parcial de D./Dña. [NOMBRE Y APELLIDOS] y se declare la inexistencia de responsabilidad empresarial de [COMPLETAR] en el pago o reintegro de la pensión de jubilación parcial de D./Dña. [NOMBRE Y APELLIDOS] dejando sin efecto la obligación de reintegro por importe de [IMPORTE] euros impuesta a la empresa.

OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda mi representada asistirá con la representación y defensa que figuran en el encabezamiento.

Por ser de justicia que pido en [COMPLETAR], en fecha [FECHA].

════════════════════════════════════════════════════════════════════════
