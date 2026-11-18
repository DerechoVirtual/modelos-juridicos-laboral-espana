---
name: erte-etop-suspension-reduccion-jornada-comunicada-335
description: "Redacta el escrito «ERTE por ETOP: suspensión o reducción de jornada comunicada al trabajador» (formulario 335 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# ERTE por ETOP: suspensión o reducción de jornada comunicada al trabajador

> Formulario 0335 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (2 veces)
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nicas, organizativas o de producción. En»; «…Muy Sr./Sra. mío/mía:»

## Elecciones que hay que hacer

- representación legal de las personas trabajadoras / comisión representativa de las personas trabajadoras
- suspensión de contratos / reducción de jornada
- económicas / técnicas / organizativas / de producción
- quince / siete
- acordada / no acordada
- suspensión de su contrato de trabajo / reducción de su jornada
- suspensión de su contratos / reducción de su jornada

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de suspensión de contratos / Si se trata de reducción de jornada — el texto de cada opción no venía en el formulario original

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 47 del Estatuto de los Trabajadores
- artículos 47 del Real Decreto Legislativo 2/2015
- art. 23 del Real Decreto 1483/2012

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

### Formulario 0335 · ERTE por ETOP: suspensión o reducción de jornada comunicada al trabajador

- Año del modelo: 2017
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 2 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 6 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
Firmas

Comunicación del empresario a la persona trabajadora de su decisión final sobre la suspensión o reducción de jornada por las causas previstas en el artículo 47 del Estatuto de los Trabajadores, que refunde los siguientes supuestos:

- Suspensión del contrato por causas económicas, técnicas, organizativas o de producción.

- Reducción entre un 10% y un 70% de la jornada por causas económicas, técnicas, organizativas o de producción.

En [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

Muy Sr./Sra. mío/mía: [COMPLETAR]

Por medio de la presente le comunicamos que con fecha [FECHA] ha finalizado el periodo de consultas, iniciado el pasado día [FECHA] con la [ELEGIR: representación legal de las personas trabajadoras / comisión representativa de las personas trabajadoras], en relación con el expediente de [ELEGIR: suspensión de contratos / reducción de jornada] planteado por la empresa por causas [ELEGIR: económicas / técnicas / organizativas / de producción],

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

habiendo llegado las partes a un acuerdo sobre las medidas a adoptar.

no habiendo llegado las partes a un acuerdo sobre las medidas a adoptar.

Por ello y una vez transcurrido el plazo de [ELEGIR: quince / siete] días establecido para la duración máxima del periodo de consultas, en cumplimiento de lo establecido en los artículos 47 del Real Decreto Legislativo 2/2015, de 23 de octubre, del Texto Refundido de la Ley del Estatuto de los Trabajadores, y art. 23 del Real Decreto 1483/2012, de 29 de octubre, por el que se aprueba el Reglamento de los procedimientos de despido colectivo y de suspensión de contratos y reducción de jornada, le comunicamos la decisión de esta Dirección [ELEGIR: acordada / no acordada] con la representación de las personas trabajadoras de proceder a la [ELEGIR: suspensión de su contrato de trabajo / reducción de su jornada], en las condiciones que se indican a continuación:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de suspensión de contratos / Si se trata de reducción de jornada — el texto de cada opción no venía en el formulario original]

La informamos de que, en esta misma fecha y en cumplimiento de lo establecido en el reiterado artículo 47 del Estatuto de los Trabajadores, procedemos a comunicar la [ELEGIR: suspensión de su contratos / reducción de su jornada] a la autoridad laboral.

Le saluda atentamente,

Empresa

Recibí

Persona trabajadora

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
