---
name: cargos-indisciplina-desobediencia-pliego-336
description: "Redacta el escrito «Cargos por indisciplina o desobediencia: pliego» (formulario 336 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cargos por indisciplina o desobediencia: pliego

> Formulario 0336 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] FECHA
- [ ] Nº
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…alizar un trabajo en un lugar concreto A»; «…Muy Sr./Sra. mío/a:»; «…Ud., tal y como exigen los los artículos»; «…t. 55.1 del Estatuto de los Trabajadores»; «…Su conducta ha producido:»; «…para la empresa, en tanto»; «…as instalaciones de la empresa, en tanto»; «…de la empresa, en tanto»; «…n de riesgos para las personas, en tanto»; «…nformidad con lo que dispone el artículo»; «…culo 54 del Estatuto de los Trabajadores»; «…cionadas, de conformidad con el artículo»

## Elecciones que hay que hacer

- grave / muy grave
- instrumentos / bienes / enseres / maquinarias / otros
- graves / muy graves

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: No utilización o utilización de forma negligente elementos de protección en materia de seguridad o prevención de riesgos / Desobedecer las órdenes sobre uso de sistemas de seguridad o prevención de riesgos / No realizar determinado trabajo / No realizar un trabajo de un modo concreto / No realizar un trabajo en un tiempo concreto / No realizar un trabajo en un lugar
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si a la empresa no le consta que la persona trabajadora sea afiliado/a a un sindicato / Si a la empresa le consta que el trabajador es afiliado/a a un sindicato — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- (Si los productos o servicios de la empresa pueden acarrear problemas sanitarios)…
- No queriendo firmar la pesona trabajadora interesada la mera recepción del anterior pliego de cargo, a ruego d…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 55.1 del Estatuto de los Trabajadores
- artículo 54 del Estatuto de los Trabajadores

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

### Formulario 0336 · Cargos por indisciplina o desobediencia: pliego

- Año del modelo: 2017
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 2 párrafos opcionales señalados; 16 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
HECHOS
CARGOS
Firmas

Modelo de pliego de cargos previo a la imposición de sanción disciplinaria a trabajador por la comisión de una falta grave o muy grave de indisciplina o desobediencia en el trabajo:

- No utilización o utilización de forma negligente elementos de protección en materia de seguridad o prevención de riesgos en el trabajo

- Desobedecer las órdenes sobre uso de sistemas de seguridad o prevención de riesgos en el trabajo

- No realizar determinado trabajo

- No realizar un trabajo de un modo concreto

- No realizar un trabajo en un tiempo concreto

- No realizar un trabajo en un lugar concreto

A [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

Muy Sr./Sra. mío/a: [COMPLETAR]

Ha venido en conocimiento de esta empresa en fecha [FECHA] la comisión por Ud. de una conducta, que más abajo se describirá detalladamente, que le obliga a iniciar el correspondiente expediente contradictorio contra Ud., tal y como exigen los los artículos [COMPLETAR] del del Convenio Colectivo y artículo 68 a) del Estatuto de los trabajadores y art. 55.1 del Estatuto de los Trabajadores [COMPLETAR], consistiendo básicamente la antedicha conducta en los siguientes

HECHOS

[ELEGIR UNA OPCIÓN Y REDACTARLA: No utilización o utilización de forma negligente elementos de protección en materia de seguridad o prevención de riesgos / Desobedecer las órdenes sobre uso de sistemas de seguridad o prevención de riesgos / No realizar determinado trabajo / No realizar un trabajo de un modo concreto / No realizar un trabajo en un tiempo concreto / No realizar un trabajo en un lugar concreto — el texto de cada opción no venía en el formulario original]

Su conducta ha producido: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

- Perjuicio [ELEGIR: grave / muy grave] para la empresa, en tanto [COMPLETAR].

- Causación de averías en las instalaciones de la empresa, en tanto [COMPLETAR].

- Causación de averías en los [ELEGIR: instrumentos / bienes / enseres / maquinarias / otros] de la empresa, en tanto [COMPLETAR].

- Causación de riesgos para las personas, en tanto [COMPLETAR].

En las mismas fechas y acontecimientos relatados en el párrafo anterior, se le hicieron las debidas advertencias verbales por los mandos de esta empresa, sin lograr el objetivo final de las mismas, cual es que Ud. utilizase debida, adecuada y temporáneamente los elementos de seguridad que la empresa le proporciona, creando con ello una situación general de peligro, no solo para su vida y/o integridad física o psíquica, sino para las de cuantos prestan sus servicios en esta empresa, con el consiguiente riesgo añadido de las responsabilidades, incluso sancionatorias, a las que se puede ver compelida esta empresa por su conducta reiterada y advertida.

[OPCIONAL — incluir si procede]

(Si los productos o servicios de la empresa pueden acarrear problemas sanitarios)

Es de advertir, además, que por las tareas y producción a que se encuentra dedicada esta empresa, la falta de medidas higiénicas acordes a cada caso, o el uso indebido de las mismas, o su dejación o, en fin, su negligente adopción y utilización, transciende los límites espaciales de la misma, ya que, como de Vd. es perfectamente conocido, los productos y servicios de ella tienen su destino final en el público en general, al que podrían acarrearle problemas sanitarios, de los que, en primera instancia, aparecería como primera y principal responsable esta empresa, con las consecuencias legales de todo tipo que de ello pudieran derivarse.

La adopción de tales medidas protectoras en el orden referente a la seguridad en el trabajo, por ende, no solo proviene de los usos establecidos en esta empresa, sino por imposición normativa e, incluso, convencional.

En virtud, por tanto, de tales antecedentes de hecho y acontecimientos, esta empresa le imputa a Ud. su comisión y los siguientes

CARGOS

Se le imputa a Ud. la comisión de las indicadas faltas, con perjuicio para la buena marcha de esta empresa, tipificadas como [ELEGIR: graves / muy graves] de conformidad con lo que dispone el artículo [COMPLETAR] del Convenio Colectivo y artículo 54 del Estatuto de los Trabajadores [COMPLETAR] y que pueden ser sancionadas, de conformidad con el artículo [COMPLETAR] del convenio colectivo y art. 54.2... del Estatuto de los Trabajadores con una sanción desde [Nº] días de suspensión de empleo y sueldo hasta con el despido.

Esta empresa le advierte, en relación con tales hechos y cargos, que, según la normativa citada en el párrafo primero de este pliego, tiene Ud. días, a contar desde la recepción de este pliego de cargos, a fin de que alegue en su defensa lo que estime oportuno, dirigiendo el pliego de descargo a D./Dña. [NOMBRE Y APELLIDOS], instructor del expediente contradictorio y disciplinario abierto contra Ud., así como proponiendo las pruebas y acreditaciones que considere precisas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si a la empresa no le consta que la persona trabajadora sea afiliado/a a un sindicato / Si a la empresa le consta que el trabajador es afiliado/a a un sindicato — el texto de cada opción no venía en el formulario original]

Este expediente disciplinario, que, en su caso, puede conllevar la imposición de una sanción en el grado de grave o muy grave, según proceda, seguirá su curso hasta su finalización, haya Ud. formulado o no el correspondiente pliego de descargos, de lo que se le advierte expresamente.

Rogándole que, a los exclusivos efectos de constancia de la recepción por Ud. de esta comunicación, firme un duplicado de la misma, le saluda atentamente.

La Empresa

Recibí

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

No queriendo firmar la pesona trabajadora interesada la mera recepción del anterior pliego de cargo, a ruego de la empresa firman, en la misma fecha y lugar, los siguientes testigos en prueba de que ello se ha intentado indicar º

════════════════════════════════════════════════════════════════════════
