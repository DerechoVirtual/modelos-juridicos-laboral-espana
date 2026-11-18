---
name: descargos-trabajador-pliego-327
description: "Redacta el escrito «Descargos del trabajador: pliego» (formulario 327 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Descargos del trabajador: pliego

> Formulario 0327 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] FECHA (2 veces)
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…o la gravedad de los hechos imputados En»; «…Muy Sr./Sra. mío/a:»; «…-»; «…-»

## Elecciones que hay que hacer

- muy grave / grave

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Justificando los hechos imputados / Negando la realidad de los hechos imputados / Negando la autoría de los hechos imputados / Negando la gravedad de los hechos imputados — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- - [COMPLETAR].…
- - [COMPLETAR].…

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0327 · Descargos del trabajador: pliego

- Año del modelo: 2017
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
ALEGACIONES
PRUEBAS QUE SE APORTAN
PRUEBAS QUE SE SOLICITAN
Firmas

Modelo de pliego de descargos del trabajador interesado evacuando el trámite de audiencia concedido en el expediente disciplinario y contradictorio abierto contra él con carácter previo a la imposición de sanción, mediante el cual procede a justificar las razones y a exponer los antecedentes que motivaron los hechos que se le imputan:

- Justificando los hechos imputados

- Negando la realidad de los hechos imputados

- Negando la autoría de los hechos imputados

- Negando la gravedad de los hechos imputados

En [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

Muy Sr./Sra. mío/a: [COMPLETAR]

El pasado día [FECHA] recibí pliego de cargos de fecha [FECHA], en el que, además de preavisarme de una posible sanción disciplinaria por falta [ELEGIR: muy grave / grave], me da Ud. audiencia y trámite para evacuar el correspondiente pliego de descargos, lo que paso a efectuar.

Doy mi total disconformidad con el pliego de cargos que me ha enviado, en virtud de las siguientes:

ALEGACIONES

[ELEGIR UNA OPCIÓN Y REDACTARLA: Justificando los hechos imputados / Negando la realidad de los hechos imputados / Negando la autoría de los hechos imputados / Negando la gravedad de los hechos imputados — el texto de cada opción no venía en el formulario original]

Al mismo tiempo, y con el fin de acreditar suficientemente las anteriores alegaciones, presento las siguientes:

PRUEBAS QUE SE APORTAN

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR].

Por otro lado, y habida cuenta que no está en mi mano presentar determinados medios de prueba que, por el contrario, sí que están al alcance de la empresa, propongo a la misma dentro del expediente disciplinario o contradictorio en curso la realización de las siguientes:

PRUEBAS QUE SE SOLICITAN

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR].

Manifiesto, por tanto, mi oposición y protesta, y solicito expresamente que se atiendan mis alegaciones, se admitan y valoren las pruebas que presento adjuntas y se admitan y practiquen las pruebas que, por no estar en mi mano, pero sí en la de la empresa, solicito, ordenando finalmente el sobreseimiento libre del expediente disciplinario que contra mí se sigue o, en su caso, la imposición de la señalada sanción leve de amonestación verbal.

En el caso de que así no se hiciere, pongo en conocimiento, respetuosa pero firmemente, de la empresa a la que este pliego de descargos, por conducto de Ud., se dirige, mi voluntad decidida de accionar contra la misma judicialmente los derechos que las normas constitucionales, legales y convencionales me otorguen.

Le saluda atentamente.

D./Dña. [NOMBRE Y APELLIDOS]

Para mi constancia, ruego que persona autorizada para ello firme un duplicado del presente pliego de descargo en acreditación de su recepción por esa empresa.

Por la empresa

════════════════════════════════════════════════════════════════════════
