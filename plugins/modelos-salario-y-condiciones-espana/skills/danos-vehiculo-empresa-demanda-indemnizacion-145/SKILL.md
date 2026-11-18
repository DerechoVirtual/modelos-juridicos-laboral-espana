---
name: danos-vehiculo-empresa-demanda-indemnizacion-145
description: "Redacta el escrito «Daños en vehículo de empresa: demanda de indemnización» (formulario 145 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Daños en vehículo de empresa: demanda de indemnización

> Formulario 0145 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NOMBRE DEL REPRESENTADO/A (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] DNI/NIE
- [ ] FECHA (4 veces)
- [ ] MARCA/MODELO (2 veces)
- [ ] MATRÍCULA
- [ ] NÚMERO
- [ ] IMPORTE
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, según escritura de poder»; «…trabajando para la Empresa»; «…desde el [FECHA] en el centro de trabajo»; «…inido, siendo su puesto de trabajo el de»; «…incluido en el grupo profesional»; «… persona trabajadora, en su condición de»; «…culo mientras circulaba por la carretera»; «…alizó el correspondiente atestado por la»; «…de»; «… acompaña como DOC. N.º 2 atestado de la»; «… del vehículo accidentado con la Entidad»; «…asa de alcohol en sangre que superaba en»

## Elecciones que hay que hacer

- ha venido / viene
- sin avenencia / sin efecto

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- — INTERROGATORIO de D./Dña. [NOMBRE Y APELLIDOS] para que bajo juramento indecisorio absuelva las posiciones q…
- — DOCUMENTAL, a fin de que se requiera a la parte demandada para que aporte al acto del juicio oral los siguie…
- [OPCIONAL — incluir si procede]…
- — La documental que esta parte aportará en el acto del juicio oral.…
- — TESTIFICAL, la que esta parte aportará al acto del juicio.…
- — Otros medios de prueba que esta parte aportará en el acto del juicio oral.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 1101 del Código Civil
- artículo 1101 del Código Civil

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

### Formulario 0145 · Daños en vehículo de empresa: demanda de indemnización

- Año del modelo: 2022
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 5 párrafos opcionales señalados; 34 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
MEDIOS DE PRUEBA

Modelo de demanda en reclamación de daños y perjuicios contra el trabajador por causar daños al vehículo de la empresa (en base al art. 5 del Estatuto de los trabajadores y al art. 1101 del Código Civil)

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], en nombre y representación de [NOMBRE DEL REPRESENTADO/A], según escritura de poder [COMPLETAR] cuya copia se adjunta a este escrito como DOC. N.º 1, y con domicilio en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo DEMANDA DE RECLAMACIÓN DE DAÑOS Y PERJUICIOS contra D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI n.º [DNI/NIE] y domicilio en [LOCALIDAD].

Se basa esta demanda en los siguientes

HECHOS

PRIMERO.— D./Dña. [ELEGIR: ha venido / viene] trabajando para la Empresa [COMPLETAR] desde el [FECHA] en el centro de trabajo [COMPLETAR], mediante un contrato de carácter indefinido, siendo su puesto de trabajo el de [COMPLETAR] incluido en el grupo profesional [COMPLETAR].

SEGUNDO.— La persona trabajadora, en su condición de [COMPLETAR], tenía asignado para su uso profesional y particular el vehículo marca [MARCA/MODELO], modelo [MARCA/MODELO], con matrícula [MATRÍCULA], propiedad de la empresa.

TERCERO.— Con fecha [FECHA], la parte demandada tuvo un accidente de tráfico con dicho vehículo mientras circulaba por la carretera [COMPLETAR], accidente que provocó daños en el vehículo.

CUARTO.— Como consecuencia de dicho accidente se realizó el correspondiente atestado por la [COMPLETAR] de [COMPLETAR], y las consiguientes diligencias previas, al haberse comprobado que el demandado circulaba con una tasa de alcohol en sangre superior a la permitida.

Se acompaña como DOC. N.º 2 atestado de la [COMPLETAR].

QUINTO.— Que aunque la empresa tiene suscrito un contrato de seguro del vehículo accidentado con la Entidad [COMPLETAR], póliza número [NÚMERO], en vigor en el momento del accidente, la compañía aseguradora no cubre los daños ocasionados por haber superado el conductor el índice de alcohol en sangre, por lo que el demandado es el responsable de los mismos, siendo el accidente culpa exclusiva suya.

Se acompaña como DOC. N.º 3 tasación de daños ocasionados al vehículo y como DOC. N.º 4 informe de la Compañía aseguradora rechazando el pago de los daños.

SEXTO.— Debe, por tanto, la persona trabajadora, abonar a la empresa los daños ocasionados en el vehículo. La responsabilidad de la persona trabajadora respecto al empresario que lo contrata está legalmente reconocida. De tal manera que los posibles efectos perniciosos que le cause "quedan sujetos a la indemnización de los daños y perjuicios causados los que en el cumplimiento de sus obligaciones incurrieren en dolo, negligencia o morosidad, y los que de cualquier modo contravinieren el tenor de aquéllas". Así consta en el artículo 1101 del Código Civil.

El Tribunal Supremo ha venido apoyando esta tesis basándose en el hecho de que la característica fundamental del contrato de trabajo es la ajenidad, tanto en frutos como en riesgos, lo que permite entender que en el ámbito laboral es necesario que el incumplimiento sea doloso o que la culpa sea "grave, cualificada o de entidad suficiente" para que dé lugar a la indemnización.

El trabajador debe efectivamente responder de sus actos, conforme al deber de cumplir las reglas de la buena fe y la diligencia establecidas en el Estatuto de los Trabajadores. La persona trabajadora conducía el vehículo con una tasa de alcohol en sangre que superaba en [COMPLETAR] el límite permitido. Su incumplimiento ha sido claramente negligente o incluso doloso. Por ello, no cabe ninguna duda que se cumple la condición necesaria para solicitar la indemnización por daños que en esta demanda se solicita.

SÉPTIMO.— Con fecha [FECHA] se ha celebrado el preceptivo acto de conciliación ante el SMAC con el resultado de [ELEGIR: sin avenencia / sin efecto]. Se adjunta copia del acta de conciliación como DOC. N.º 5.

En apoyo de la presente demanda se formularán en el acto del juicio oral los oportunos Fundamentos de Derecho.

Por todo lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA que teniendo por presentado este escrito con sus copias y los documentos que lo acompañan, se sirva admitirlo y, previos los trámites oportunos, tenga por interpuesta en nombre de [NOMBRE DEL REPRESENTADO/A] demanda por RECLAMACIÓN DE INDEMNIZACIÓN POR LOS DAÑOS CAUSADOS AL VEHÍCULO DE EMPRESA contra D. /Dña. [NOMBRE Y APELLIDOS], señalando día y hora para la celebración del acto de conciliación o, en su caso, juicio, y en su día, previos los trámites procesales oportunos, dicte Sentencia por la que se reconozca la responsabilidad de la parte demandada por los daños ocasionados al vehículo de empresa derivados del accidente de tráfico ocurrido con fecha [FECHA] y le condene a abonar a la empresa el importe de [IMPORTE] Euros en concepto de indemnización por daños y perjuicios.

PRIMER OTROSÍ DIGO, que la empresa acudirá al acto del juicio oral representada de Letrado/a.

SEGUNDO OTROSÍ DIGO, que interesa al derecho de esta parte que se practiquen en el acto del juicio oral los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

— INTERROGATORIO de D./Dña. [NOMBRE Y APELLIDOS] para que bajo juramento indecisorio absuelva las posiciones que se le formularán en el acto del juicio oral, y con el apercibimiento de tenerlo/a por confeso/a en caso de incomparecencia. Debe ser citado oportunamente en su domicilio sito en [LOCALIDAD].

[OPCIONAL — incluir si procede]

— DOCUMENTAL, a fin de que se requiera a la parte demandada para que aporte al acto del juicio oral los siguientes documentos:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

[OPCIONAL — incluir si procede]

— La documental que esta parte aportará en el acto del juicio oral.

[OPCIONAL — incluir si procede]

— TESTIFICAL, la que esta parte aportará al acto del juicio.

[OPCIONAL — incluir si procede]

— Otros medios de prueba que esta parte aportará en el acto del juicio oral.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones, por propuesta la prueba, la admita y la declare pertinente y acuerde su práctica, así como las citaciones y requerimientos oportunos.

Es de Justicia que reitero en el lugar y fecha ut supra.

════════════════════════════════════════════════════════════════════════
