---
name: reclamacion-cantidad-demanda-371
description: "Redacta el escrito «Reclamación de cantidad: demanda» (formulario 371 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reclamación de cantidad: demanda

> Formulario 0371 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] NIF
- [ ] FECHA (3 veces)
- [ ] IMPORTE (3 veces)
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…egalmente establecido, contra la empresa»; «…y contra la entidad aseguradora»; «…a de aplicación el convenio colectivo de»; «…, en el grupo profesional de»; «… desglose es el siguiente: Salario Base:»; «… de aplicación del convenio colectivo de»; «…ción de la demanda se acuerde condenar a»; «…en»

## Elecciones que hay que hacer

- salarios / horas extraordinarias / indemnización por despido / compensación y absorción indebida / plus de antigüedad / indemnización derivada de contrato de seguro establecido por convenio colectivo / diferencias de indemnización derivada de contrato de seguro establecido por convenio colectivo / aplicación de un convenio diferente / diferencias de convenio
- sin avenencia / sin efecto
- insolvente / en concurso

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se reclaman salarios / Si se reclaman horas extras / Si se reclama indemnización por despido / Si se reclama por compensación y absorción indebida / Si se reclama plus de antigüedad / Si se reclama indemnización derivada de contrato de seguro establecido por convenio colectivo / Si se reclaman diferencias de indemnización derivada de contrato de seguro establecid
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se reclama también al FOGASA / Si se reclaman salarios / Si se reclaman horas extras / Si se reclama indemnización por despido / Si se reclama compensación y absorción indebida, plus de antigüedad o diferencias de convenio / Si se reclama indemnización o diferencias de indemnización derivada de contrato de seguro establecido por convenio colectivo — el texto de c
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (7)

Inclúyelos solo si encajan en los hechos:

- y contra la entidad aseguradora [COMPLETAR], en la persona de su representante legal…
- y contra el Fondo de Garantía Salarial, en la persona de su representante legal…
- [ELEGIR UNA OPCIÓN Y REDACTARLA: Si se reclaman salarios / Si se reclaman horas extras / Si se reclama indemni…
- (Si se demanda también al FOGASA, como consecuencia de insolvencia o concurso de la entidad demandada)…
- (Si se reclama por diferencias de convenio)…
- (Se detallan a continuación todos los medios de prueba (interrogatorio, documental, etc.) que interesen presen…
- (Para el caso de que la empresa no haya acudido al acto de conciliación)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 33 del Estatuto de los Trabajadores
- art. 33 ET
- artículo 90.1 de la LRJS
- art. 66 de la LRJS

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

### Formulario 0371 · Reclamación de cantidad: demanda

- Año del modelo: 2016
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); 3 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 5 párrafos opcionales señalados; 21 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de demanda en reclamación de cantidad en el ámbito Social, de conformidad con el procedimiento ordinario establecido en los artículos 80 y siguientes de la Ley reguladora de la jurisdicción social, que refunde los siguientes supuestos –no taxativos- que puede seleccionar individualmente:

- Reclamación de salarios.

- Reclamación de horas extras.

- Reclamación de indemnización por despido.

- Reclamación de compensación y absorción indebida.

- Reclamación de plus de antigüedad (trienios).

- Reclamación de indemnización derivada de contrato de seguro establecido por convenio colectivo.

- Reclamación de diferencia de indemnización derivada de contrato de seguro establecido por convenio colectivo.

- Reclamación por diferencias de convenio o aplicación de convenio diferente.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con NIF/NIE número [DNI/NIE] y domicilio en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante la Sección de lo Social del Tribunal de Instancia comparece y DICE:

Que mediante el presente escrito, interpone demanda en reclamación de cantidad por [ELEGIR: salarios / horas extraordinarias / indemnización por despido / compensación y absorción indebida / plus de antigüedad / indemnización derivada de contrato de seguro establecido por convenio colectivo / diferencias de indemnización derivada de contrato de seguro establecido por convenio colectivo / aplicación de un convenio diferente / diferencias de convenio], en tiempo y forma legalmente establecido, contra la empresa [COMPLETAR], CIF [NIF], C.C.C., en la persona de su representante legal

[OPCIONAL — incluir si procede]

y contra la entidad aseguradora [COMPLETAR], en la persona de su representante legal

[OPCIONAL — incluir si procede]

y contra el Fondo de Garantía Salarial, en la persona de su representante legal

Todo ello en base a los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que el demandante ha venido prestando servicios para la referida empresa a la que le resulta de aplicación el convenio colectivo de [COMPLETAR], desde el día [FECHA], en el grupo profesional de [COMPLETAR], percibiendo con un salario bruto mensual de [IMPORTE] euros, incluida la prorrata de pagas extras, que se abona mediante transferencia bancaria y cuyo desglose es el siguiente:

Salario Base: [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se reclaman salarios / Si se reclaman horas extras / Si se reclama indemnización por despido / Si se reclama por compensación y absorción indebida / Si se reclama plus de antigüedad / Si se reclama indemnización derivada de contrato de seguro establecido por convenio colectivo / Si se reclaman diferencias de indemnización derivada de contrato de seguro establecido por convenio colectivo / Si se reclama cantidad por aplicación de un convenio diferente o diferencias de convenio — el texto de cada opción no venía en el formulario original]

TERCERO.- Que en fecha [FECHA] se celebró el preceptivo Acto de Conciliación ante el Servicio de Mediación, Arbitraje y Conciliación, el cual finalizó [ELEGIR: sin avenencia / sin efecto], tal y como acredito mediante el Acta de la celebración de dicha conciliación que a este escrito se acompaña.

[OPCIONAL — incluir si procede]

(Si se demanda también al FOGASA, como consecuencia de insolvencia o concurso de la entidad demandada)

CUARTO.- Que, dada la situación económica de la empresa demandada y la elevada posibilidad de ser declarada [ELEGIR: insolvente / en concurso], de conformidad con lo establecido en el artículo 33 del Estatuto de los Trabajadores el FOGASA será responsable del abono de la cantidad reclamada en caso de que así se declare.

A los anteriores hechos les resultan de aplicación los siguientes:

FUNDAMENTOS DE DERECHO

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se reclama también al FOGASA / Si se reclaman salarios / Si se reclaman horas extras / Si se reclama indemnización por despido / Si se reclama compensación y absorción indebida, plus de antigüedad o diferencias de convenio / Si se reclama indemnización o diferencias de indemnización derivada de contrato de seguro establecido por convenio colectivo — el texto de cada opción no venía en el formulario original]

II.- Normativa de aplicación del convenio colectivo de [COMPLETAR].

III.- Demás fundamentos legales y jurisprudenciales que se expondrán en el momento procesal oportuno.

En virtud de cuanto antecede es por lo que,

SUPLICO AL TRIBUNAL, que teniendo por presentado este escrito, con sus copias y documentos que lo acompañan, se sirva admitirlo y citar a las partes para la celebración del Acto de Juicio y tras el intento previo de conciliación siga con los demás trámites hasta dictar sentencia por la que con estimación de la demanda se acuerde condenar a [COMPLETAR] al abono al demandante de la cantidad de [IMPORTE] euros, en concepto de salarios devengados y no abonados, más el diez por ciento en concepto de intereses por mora,

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Si se reclama indemnización o diferencias de indemnización derivadas de contrato de seguro)
— (Si se reclaman salarios, salarios de tramitación o indemnización por despido o extinción de contrato al FOGASA, a causa insolvencia o concurso del empresario, conforme al art. 33 ET)
— (Si se reclama por compensación y absorción indebida)
— (Si se reclama plus de antigüedad)

[OPCIONAL — incluir si procede]

(Si se reclama por diferencias de convenio)

y a abonar a la actora las cantidades salariales que se le adeudan, más el diez por ciento de recargo por mora en el pago dado lo injustificado del comportamiento empresarialy que se concretará en el acto del juicio, cantidad que a fecha de hoy asciende a un total de [IMPORTE] euros, con todo cuanto más proceda en Derecho.

PRIMER OTROSI DIGO: Que al acto de juicio este demandante comparecerá asistido de Letrado que le defienda, en conformidad con el artículo 21.2 de la Ley reguladora de la jurisdicción social, designando – sin perjuicio de las notificaciones via Lexnet- el domicilio profesional del Letrado D./Dña. [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

SUPLICO AL TRIBUNAL que tenga por hecha tal manifestación, a los efectos oportunos.

SEGUNDO OTROSI DIGO: Que interesan al derecho de esta parte, y sin perjuicio de ampliación en el momento procesal oportuno, los siguientes MEDIOS DE PRUEBA:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
(Se detallan a continuación todos los medios de prueba (interrogatorio, documental, etc.) que interesen presentar junto a la demanda)

En cumplimiento de lo dispuesto por el artículo 90.1 de la LRJS entiende esta parte que la prueba documental solicitada por medio del presente escrito es útil y directamente pertinente al objeto del presente juicio, en razón de que resultará útil para acreditar:

SUPLICO AL TRIBUNAL que tenga por hechas tales manifestaciones a los efectos oportunos, admita y declare pertinentes las pruebas propuestas, y acuerde cuanto sea preciso.

Para el caso de que la empresa no haya acudido al acto de conciliación:

[OPCIONAL — incluir si procede]

(Para el caso de que la empresa no haya acudido al acto de conciliación)

TERCER OTROSI DIGO, que si la sentencia que en su día dicte coincidiera esencialmente con la pretensión contenida en la papeleta de conciliación, y en virtud de lo establecido en el art. 66 de la LRJS, deberán imponerse las costas del proceso a la empresa por no haber comparecido al acto de conciliación.

SUPLICO AL TRIBUNAL que tenga por hecha la anterior manifestación a los efectos legales oportunos.

Es de Justicia que pide en [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
