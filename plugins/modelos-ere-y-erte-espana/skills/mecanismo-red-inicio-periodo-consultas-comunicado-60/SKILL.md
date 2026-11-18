---
name: mecanismo-red-inicio-periodo-consultas-comunicado-60
description: "Redacta el escrito «Mecanismo RED: inicio del periodo de consultas comunicado a la autoridad laboral» (formulario 60 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mecanismo RED: inicio del periodo de consultas comunicado a la autoridad laboral

> Formulario 0060 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] CORREO ELECTRÓNICO (2 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (4 veces)
- [ ] NÚMERO
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…el acuerdo de activación. A LA DIRECCIÓN»; «…ficaciones en el despacho profesional de»; «…en:»; «…bre y representación del grupo mercantil»; «…, (compuesto por las sociedades»; «…de su protocolo, ante la Dirección»; «…onsolidada, correspondiente al ejercicio»; «…allada en la memoria que se adjunta, son»; «…rantes del grupo ha estado integrada por»; «… como representantes ante esta Dirección»; «…zar cuantas gestiones sean pertinentes a»; «…OLICITAMOS A LA DIRECCIÓN TERRITORIAL DE»; …

## Elecciones que hay que hacer

- suspensión de contratos / reducción de jornada
- cíclica / sectorial

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Sólo en el supuesto de la modalidad sectorial del Mecanismo RED…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 47 bis del Estatuto de los Trabajadores
- artículo 47 bis del Estatuto de los Trabajadores
- Real Decreto 608/2023

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

### Formulario 0060 · Mecanismo RED: inicio del periodo de consultas comunicado a la autoridad laboral

- Año del modelo: 2023
- Revisión 17-11-2026: 4 desplegables y casillas convertidos en elección en blanco; 1 párrafos opcionales señalados; 27 campos de relleno marcados en blanco
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

DICE:
Firmas

Una vez activado el Mecanismo RED, las empresas podrán solicitar voluntariamente a la autoridad laboral competente la reducción de la jornada o la suspensión de los contratos de trabajo, mientras esté activado el Mecanismo, en cualquiera de sus centros de trabajo.

El contrato de trabajo podrá suspenderse cuando el cese de la actividad que venía desarrollando la persona trabajadora afecte a días completos, continuados o alternos, durante al menos una jornada ordinaria de trabajo.

Se entenderá por reducción de jornada la disminución temporal de la actividad laboral, que podrá computarse sobre la base de la jornada diaria, semanal, mensual o anual. La reducción de la jornada de trabajo diaria podrá conllevar el cese de actividad durante un máximo de horas al día; mientras que la reducción de la jornada semanal, mensual o anual podrá suponer el cese de actividad durante unas horas al día o durante jornadas completas, dentro del límite porcentual máximo, semanal, mensual o anual, fijado.

En la medida en que ello sea viable, se priorizará la adopción de medidas de reducción de jornada frente a las de suspensión de contratos.

Durante la aplicación de un expediente derivado del Mecanismo RED, cada persona trabajadora solo podrá verse afectada en exclusiva por una reducción de su jornada o por una suspensión de su contrato, sin que quepa una combinación de ambas, y sin perjuicio de la afectación o desafectación, o de la variación en el porcentaje de reducción de jornada, que se produzcan ante la alteración de las circunstancias alegadas como causa justificativa de las medidas.

El alcance y duración de las medidas de suspensión de los contratos o de reducción de jornada se adecuarán a la situación que se pretende superar, entendida en los términos del acuerdo de activación.

A LA DIRECCIÓN [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], con domicilio a efectos de citaciones y notificaciones en el despacho profesional de [COMPLETAR] en: [COMPLETAR], telf. y correo electrónico [CORREO ELECTRÓNICO], en nombre y representación del grupo mercantil [COMPLETAR], (compuesto por las sociedades [COMPLETAR]), según copia de poder otorgado al efecto por el Ilustre Notario del Colegio de [LOCALIDAD], D./Dña. [NOMBRE Y APELLIDOS], en fecha [FECHA] y obrante al número [NÚMERO] de su protocolo, ante la Dirección [COMPLETAR] comparece y como mejor proceda

DICE:

PRIMERO.- Que en fecha [FECHA] se ha iniciado el periodo de consultas con las personas trabajadoras del grupo mercantil indicado, respecto a la [ELEGIR: suspensión de contratos / reducción de jornada] como consecuencia del cese de actividad en el centro de trabajo sito en [LOCALIDAD], por las causas previstas en el acuerdo de activación del Mecanismo RED aprobado por Acuerdo del Consejo de Ministros de fecha [FECHA], todo ello al amparo de lo establecido en el art. 47 bis del Estatuto de los Trabajadores.

En dicha fecha se ha hecho entrega a la representación de las personas trabajadoras de la siguiente documentación, que se adjunta -igualmente- al presente escrito:

a) documentación acreditativa de la concurrencia de la situación [ELEGIR: cíclica / sectorial] establecida en el acuerdo de activación del Mecanismo RED aprobado por Acuerdo del Consejo de Ministros de fecha [FECHA].
b) Balance de situación consolidado y cuenta de pérdidas y ganancias consolidada, correspondiente al ejercicio [COMPLETAR].
c) Memoria explicativa de las causas para la [ELEGIR: suspensión de contratos / reducción de jornada], que incluye la relación de las personas trabajadoras afectadas por la medida, criterios utilizados para su elección, las medidas propuestas y el calendario mediante el cual se llevarán a efecto.

[OPCIONAL — incluir si procede]

Sólo en el supuesto de la modalidad sectorial del Mecanismo RED

d) plan de recualificación de las personas afectadas.

Se adjunta también el documento acreditativo de la recepción por parte de las personas trabajadoras de la citada documentación.

SEGUNDO.- En cuanto a las causas que motivan la presente solicitud, como consta de manera más detallada en la memoria que se adjunta, son [COMPLETAR].

Esta parte comunicará a la Dirección Territorial a la que nos dirigimos el resultado del periodo de consultas que hoy se inicia.

TERCERO.- Que las personas trabajadoras que se verán afectadas por la medida propuesta por la Dirección de la empresa, son:

EMPRESA	TRABAJADOR/A	N.I.F.	N.A.S.S.	CAT.PROF.

CUARTO.- Que en el último año la plantilla de las empresas integrantes del grupo ha estado integrada por [COMPLETAR] personas trabajadoras, cuyas categorías profesionales son las que se refieren:

EMPRESA	TRABAJADOR/A	N.I.F.	CAT.PROF.	ESTADO

QUINTO.- Que mediante la presente vengo a designar como representantes ante esta Dirección [COMPLETAR] y, ante cuantos más organismos deban comparecer en nombre de las mercantiles, al objeto de presentar, gestionar, consultar y realizar cuantas gestiones sean pertinentes a [COMPLETAR], con domicilio profesional en [LOCALIDAD], telf. y correo electrónico [CORREO ELECTRÓNICO].

En virtud de lo expuesto,

SOLICITAMOS A LA DIRECCIÓN TERRITORIAL DE [COMPLETAR], que atendidas las razones expuestas en el cuerpo del presente escrito, tenga por comunicado e iniciado el procedimiento establecido en el artículo 47 bis del Estatuto de los Trabajadores y en el Real Decreto 608/2023, de 11 julio, para la [ELEGIR: suspensión de contratos / reducción de jornada] derivados de las causas por las que se ha activado el mecanismo RED, durante el periodo [COMPLETAR] y el porcentaje [COMPLETAR] que se establece en la memoria explicativa que se acompaña, con todo cuanto más proceda en Derecho.

En [COMPLETAR].

════════════════════════════════════════════════════════════════════════
