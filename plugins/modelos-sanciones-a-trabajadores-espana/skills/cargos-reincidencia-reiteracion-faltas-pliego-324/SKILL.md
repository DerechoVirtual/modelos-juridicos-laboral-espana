---
name: cargos-reincidencia-reiteracion-faltas-pliego-324
description: "Redacta el escrito «Cargos por reincidencia o reiteración de faltas: pliego» (formulario 324 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cargos por reincidencia o reiteración de faltas: pliego

> Formulario 0324 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] Nº
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…r reincidencia o reiteración de faltas A»; «…Muy Sr./Sra. mío/a:»; «…tra Ud., tal y como exigen los artículos»; «…y 68 a) del Estatuto de los Trabajadores»; «…lo 55.1 del Estatuto de los Trabajadores»; «…echa, realizó Ud. la siguiente conducta:»; «…a sido Ud. sancionado por la comisión de»; «…echa se le comunicó a Ud. una sanción de»; «…por la comisión de una falta de»; «…la realización de los siguientes hechos:»; «…to, la comisión de faltas calificadas de»; «…nformidad con lo que dispone el artículo»; …

## Elecciones que hay que hacer

- graves / leves
- grave / leve
- Segunda / Tercera
- muy grave / grave
- graves / muy graves

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si a la empresa no le consta que la persona trabajadora sea afiliado/a a un sindicato / Si a la empresa le consta que la persona trabajadora es afiliado/a a un sindicato — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- Primera [ELEGIR: Segunda / Tercera] falta: En fecha se le comunicó a Ud. una sanción de [COMPLETAR] por la com…
- No queriendo firmar la persona trabajadora interesada la mera recepción del anterior pliego de cargo, a ruego …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 55.1 del Estatuto de los Trabajadores
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

### Formulario 0324 · Cargos por reincidencia o reiteración de faltas: pliego

- Año del modelo: 2017
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 3 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
HECHOS
CARGOS
Firmas

Modelo de pliego de cargos previo a la imposición de sanción disciplinaria a trabajador por la comisión de una falta grave o muy grave por reincidencia o reiteración de faltas

A [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

Muy Sr./Sra. mío/a: [COMPLETAR]

Ha venido en conocimiento de esta empresa en fecha [FECHA] la comisión por Ud. de una conducta, que más abajo se describirá detalladamente, que le obliga a iniciar el correspondiente expediente contradictorio contra Ud., tal y como exigen los artículos [COMPLETAR] del del Convenio Colectivo y 68 a) del Estatuto de los Trabajadores [COMPLETAR] y el artículo 55.1 del Estatuto de los Trabajadores [COMPLETAR], consistiendo básicamente la antedicha conducta en los siguientes

HECHOS

En fecha [FECHA], con pleno conocimiento de lo que llevaba a cabo y perfecto alcance de los efectos de su actitud y conducta, infringió Ud., una vez más y dentro del último año, los deberes de lealtad, buena fe y confianza recíproca que los usos y la normativa laborales le imponen.

Así, en la indicada fecha, realizó Ud. la siguiente conducta: [COMPLETAR].

Puesto que, dentro del último año, ha sido Ud. sancionado por la comisión de [COMPLETAR], al menos, dos faltas calificadas de [ELEGIR: graves / leves], es obvio que estamos a presencia de un caso de reincidencia o reiteración, entendiendo por tal la situación en la que, con anterioridad a la comisión de la última falta acabada de indicar, fue Ud. sancionado dos o más veces por falta [ELEGIR: grave / leve] durante el último año, sin que haya que tener en cuenta el hecho de que tales faltas antecedentes fueran de igual o diferente naturaleza.

En concreto, las dos faltas [ELEGIR: graves / leves] por las que Ud. fue sancionado dentro del último año, y de las que ha tenido perfecto y cabal conocimiento y que están acreditadas ante esta empresa, son las siguientes:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Primera [ELEGIR: Segunda / Tercera] falta: En fecha se le comunicó a Ud. una sanción de [COMPLETAR] por la comisión de una falta de [COMPLETAR], calificada de [ELEGIR: grave / leve], por la realización de los siguientes hechos: [COMPLETAR].

Siendo evidente, por tanto, la comisión de faltas calificadas de [COMPLETAR], al menos, [ELEGIR: graves / leves], así como sancionadas en igual medida, y siendo el número de ellas igual o superior a dos en el último año, procede apreciar reincidencia y/o reiteración, con la consiguiente elevación, en cualquier caso, de su reciente conducta, descrita en esta comunicación, a la categoría de falta [ELEGIR: muy grave / grave], con las consecuencias a ello inherentes.

En virtud, por tanto, de tales antecedentes de hecho y acontecimientos, esta empresa le imputa a Ud. su comisión y los siguientes

CARGOS

Se le imputa a Ud. la comisión de las indicadas faltas, con perjuicio para la buena marcha de esta empresa, tipificadas como [ELEGIR: graves / muy graves] de conformidad con lo que dispone el artículo [COMPLETAR] del Convenio Colectivo y el artículo 54 del Estatuto de los Trabajadores [COMPLETAR] y que pueden ser sancionadas, de conformidad con el artículo [COMPLETAR] del Convenio Colectivo y el art. 54.2. ... del Estatuto de los Trabajadores con una sanción desde [Nº] días de suspensión de empleo y sueldo hasta con el despido.

Esta empresa le advierte, en relación con tales hechos y cargos, que, según la normativa citada en el párrafo primero de este pliego, tiene Ud. días, a contar desde la recepción de este pliego de cargos, a fin de que alegue en su defensa lo que estime oportuno, dirigiendo el pliego de descargo a D./Dña. [NOMBRE Y APELLIDOS], instructor del expediente contradictorio y disciplinario abierto contra Ud., así como proponiendo las pruebas y acreditaciones que considere precisas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si a la empresa no le consta que la persona trabajadora sea afiliado/a a un sindicato / Si a la empresa le consta que la persona trabajadora es afiliado/a a un sindicato — el texto de cada opción no venía en el formulario original]

Este expediente disciplinario, que, en su caso, puede conllevar la imposición de una sanción en el grado de grave o muy grave, según proceda, seguirá su curso hasta su finalización, haya Ud. formulado o no el correspondiente pliego de descargos, de lo que se le advierte expresamente.

Rogándole que, a los exclusivos efectos de constancia de la recepción por Ud. de esta comunicación, firme un duplicado de la misma, le saluda atentamente.

La Empresa

Recibí

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

No queriendo firmar la persona trabajadora interesada la mera recepción del anterior pliego de cargo, a ruego de la empresa firman, en la misma fecha y lugar, los siguientes testigos en prueba de que ello se ha intentado.

════════════════════════════════════════════════════════════════════════
