---
name: ejecucion-sentencia-acta-conciliacion-firme-solicitud-365
description: "Redacta el escrito «Ejecución de sentencia o acta de conciliación firme: solicitud» (formulario 365 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecución de sentencia o acta de conciliación firme: solicitud

> Formulario 0365 del plugin **Proceso laboral** · revisado el 17-11-2026.

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
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] DNI/NIE
- [ ] NÚMERO
- [ ] LOCALIDAD (2 veces)
- [ ] NIF
- [ ] IMPORTE (8 veces)
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… y conflictos colectivos. Procedimiento:»; «…a la EJECUCIÓN FORZOSA contra la empresa»; «…isto legalmente. Es justicia que pido en»; «…,»

## Elecciones que hay que hacer

- sentencia / acto de conciliación judicial firme
- a la que fue condenada / a la que se comprometió

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de ejecución de acto de conciliación judicial — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de ejecución de conciliación judicial — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de conciliación judicial — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de desconocerse bienes y derechos propiedad de la ejecutada / En caso de conocerse bienes y derechos propiedad de la ejecutada — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 68.1 y 84.5 LRJS

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

### Formulario 0365 · Ejecución de sentencia o acta de conciliación firme: solicitud

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 4 bloques de opciones sin texto dejados en blanco con sus rótulos; 16 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 3 huecos del original que se habían perdido sin marca, marcados (IMPORTE)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Modelo de solicitud de ejecución de sentencia firme en la vía jurisdiccional social, de conformidad con los artículos 237 y siguientes de la Ley reguladora de la jurisdicción social

La designación de bienes y derechos a embargar puede realizarse en cualquier momento en la que la ejecutante tenga conocimiento de los mismos.

En vía laboral, la ejecución forzosa puede fundarse tanto en una sentencia firme como en un acta de conciliación judicial aprobada. La sentencia firme abre la vía ejecutiva una vez alcanzada su firmeza y debe ejecutarse en sus propios términos; el acuerdo de conciliación judicial, por su parte, constituye título ejecutivo sin necesidad de ratificación adicional y se ejecuta por los trámites de la ejecución de sentencias, conforme a los arts. 68.1 y 84.5 LRJS. En ambos casos, la ejecución persigue la efectividad íntegra del derecho reconocido, con especialidades relevantes en despido, readmisión, nulidad, modificaciones sustanciales y conflictos colectivos.

Procedimiento: [COMPLETAR]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]
 [NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de DNI nº [DNI/NIE], con domicilio a efectos de notificaciones el despacho profesional de mi letrado D./Dña. [NOMBRE Y APELLIDOS] (Col nº [NÚMERO]), sito en [LOCALIDAD], ante el tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que por medio del presente escrito, de conformidad con lo dispuesto en el artículo 237 y siguientes de la LRJS, se solicita la EJECUCIÓN FORZOSA contra la empresa [COMPLETAR], provista de NIF [NIF], con domicilio, sito en [LOCALIDAD], en la persona de su representante legal, de:

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de ejecución de acto de conciliación judicial — el texto de cada opción no venía en el formulario original]

La presente ejecución tiene su base en los siguientes:

HECHOS

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de ejecución de conciliación judicial — el texto de cada opción no venía en el formulario original]

TERCERO.- Que siendo la anterior [ELEGIR: sentencia / acto de conciliación judicial firme], la empresa hoy ejecutada no ha satisfecho la cantidad [ELEGIR: a la que fue condenada / a la que se comprometió], motivo por el que se solicita la ejecución de la cantidad total de [IMPORTE] EUROS por los siguientes conceptos:

- [IMPORTE] EUROS en concepto de principal.

- [IMPORTE] EUROS en concepto de intereses.

- [IMPORTE] EUROS en concepto de costas de la ejecución.

Cantidades en concepto de intereses y costas que por el momento se estiman sin perjuicio de ulterior liquidación.

En su virtud,

SUPLICO AL TRIBUNAL.- Que teniendo por presentado este escrito junto con sus copias, se sirva admitirlo, por realizadas las manifestaciones en él contenidas y, en méritos del mismo, se tenga por promovida, en tiempo y forma, EJECUCIÓN POR VÍA DE APREMIO

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de ejecución de sentencia / En caso de conciliación judicial — el texto de cada opción no venía en el formulario original]

por la/el que, tras los trámites pertinentes, dicte resolución por la que acuerde la ejecución por vía de apremio contra la ejecutada por la cantidad total de [IMPORTE] EUROS de los que [IMPORTE] EUROS son en concepto de principal, [IMPORTE] EUROS en concepto de intereses y [IMPORTE] EUROS en concepto de costas de la ejecución, cantidades que por el momento se estiman sin perjuicio de ulterior liquidación y, para el caso de que no existiesen bienes suficientes para cubrir la presente ejecución, se inicien los trámites para la declaración de insolvencia de la ejecutada previa audiencia al FONDO DE GARANTÍA SALARIAL según lo previsto legalmente.

Es justicia que pido en [COMPLETAR], [COMPLETAR].

OTROSÍ DIGO.- Que al objeto de hacer efectiva la presente ejecución.

SUPLICO AL TRIBUNAL.- Acuerde:

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de desconocerse bienes y derechos propiedad de la ejecutada / En caso de conocerse bienes y derechos propiedad de la ejecutada — el texto de cada opción no venía en el formulario original]

Reitero justicia “ut supra”.

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
