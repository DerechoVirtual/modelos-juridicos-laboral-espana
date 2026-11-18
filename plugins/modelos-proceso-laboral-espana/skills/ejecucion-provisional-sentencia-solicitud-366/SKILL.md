---
name: ejecucion-provisional-sentencia-solicitud-366
description: "Redacta el escrito «Ejecución provisional de sentencia: solicitud» (formulario 366 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ejecución provisional de sentencia: solicitud

> Formulario 0366 del plugin **Proceso laboral** · revisado el 17-11-2026.

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
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] DNI/NIE
- [ ] NÚMERO
- [ ] LOCALIDAD
- [ ] Nº DE RESOLUCIÓN (2 veces)
- [ ] FECHA (5 veces)
- [ ] IMPORTE (2 veces)
- [ ] DESCRIBIR
- [ ] Nº DE PROCEDIMIENTO
- [ ] LUGAR
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… trabajo (art. 297 LRJS). Procedimiento:»; «…se dictó la sentencia»; «…, de»; «…, a [FECHA]. Firmas:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de ejecución de cantidades / Si se trata de prestaciones de la Seguridad Social de pago periódico / Si se trata de prestaciones de pago único de la Seguridad Social / Si se trata de obligaciones de hacer o no hacer en materia de Seguridad Social / Si se trata de materia de despido — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la sentencia condena al pago de cantidades dinerarias / Si la sentencia reconoce una prestación periódica de Seguridad Social / Si la sentencia reconoce una prestación de pago único de Seguridad Social / Si la sentencia reconoce una prestación de hacer o no hacer de Seguridad Social / Si la sentencia resuelve un despido — el texto de cada opción no venía en el fo

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 289 a 293 LRJS
- art. 294 LRJS
- art. 295 LRJS
- art. 296 LRJS
- art. 297 LRJS

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

### Formulario 0366 · Ejecución provisional de sentencia: solicitud

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 21 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Modelo de solicitud de ejecución provisional de sentencia en la vía jurisdiccional social, de conformidad con los artículos 289 a 297 de la Ley reguladora de la jurisdicción social, que refunde los siguientes supuestos que puede seleccionar individualmente:

- Ejecución provisional de sentencia de cantidad. Cuando el trabajador tuviere a su favor una sentencia en la que se hubiere condenado al empresario al pago de una cantidad y se interpusiere recurso contra ella, tendrá derecho a obtener anticipos a cuenta de aquélla(como máximo hasta el 50% de la cantidad reconocida y con el tope anual del doble del SMI), garantizando el Estado su reintegro y realizando, en su caso, su abono, en los términos establecidos en la Ley (arts. 289 a 293 LRJS)

- Ejecución provisional de sentencia de prestación periódica de Seguridad Social. Las sentencias recurridas, condenatorias al pago de prestaciones de pago periódico de Seguridad Social, serán ejecutivas, quedando el condenado obligado a abonar la prestación, hasta el límite de su responsabilidad, durante la tramitación del recurso (art. 294 LRJS)

- Ejecución provisional de sentencia de prestación de pago único de Seguridad Social. El beneficiario de prestaciones del régimen público de la Seguridad Social que tuviera a su favor una sentencia recurrida en la que se hubiere condenado al demandado al pago de una prestación de pago único, tendrá derecho a solicitar su ejecución provisional y obtener anticipos a cuenta de aquélla (art. 295 LRJS)

- Ejecución provisional de sentencia de prestación de hacer o no hacer de Seguridad Social. A petición del beneficiario favorecido por ellas, el juez o la Sala, ponderando las circunstancias concurrentes, podrá acordar también la ejecución provisional, sin exigencia de fianza, de las sentencias condenatorias a obligaciones de hacer o no hacer en materia de Seguridad Social (art. 296 LRJS)

- Ejecución provisional de sentencia de despido. Cuando en los procesos donde se ejerciten acciones derivadas de despido o de decisión extintiva de la relación de trabajo la sentencia declare su improcedencia y el empresario que hubiera optado por la readmisión interpusiera alguno de los recursos autorizados por la Ley, éste vendrá obligado, mientras dure la tramitación del recurso, a satisfacer al recurrido la misma retribución que venía percibiendo con anterioridad a producirse aquellos hechos y continuará el trabajador prestando servicios, a menos que el empresario prefiera hacer el abono aludido sin compensación alguna. Lo anteriormente dispuesto también será aplicable cuando, habiendo optado el empresario por la readmisión, el recurso lo interpusiera el trabajador. La misma obligación tendrá el empresario si la sentencia hubiera declarado la nulidad del despido o de la decisión extintiva de la relación de trabajo (art. 297 LRJS).

Procedimiento: [COMPLETAR]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]
 [NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de DNI nº [DNI/NIE], asistido/a por mi letrado/a D./Dña. [NOMBRE Y APELLIDOS] (Col nº [NÚMERO]), según tengo acreditado en los autos de referencia, con despacho profesional sito en [LOCALIDAD], ante el tribunal comparezco y, como mejor proceda en Derecho, DIGO:

Que habiéndose dictado la sentencia nº [Nº DE RESOLUCIÓN], de fecha [FECHA], en el procedimiento al margen referenciado mediante el presente escrito, se solicita su EJECUCIÓN PROVISIONAL de conformidad con lo dispuesto

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se trata de ejecución de cantidades / Si se trata de prestaciones de la Seguridad Social de pago periódico / Si se trata de prestaciones de pago único de la Seguridad Social / Si se trata de obligaciones de hacer o no hacer en materia de Seguridad Social / Si se trata de materia de despido — el texto de cada opción no venía en el formulario original]

La presente ejecución provisional tiene su base en los siguientes:

HECHOS

PRIMERO.- El día [FECHA] se dictó la sentencia [COMPLETAR] en el mencionado procedimiento, notificada a esta parte en fecha [FECHA], en cuyo fallo se estableció:

SEGUNDO.- Que la parte demandada y condenada en la referida sentencia formuló recurso contra la misma mediante escrito de fecha [FECHA], estando pendiente de resolución, por lo que la referida sentencia no es firme.

TERCERO.- Que interesa al derecho de esta parte instar la ejecución provisional de la sentencia dictada:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

al objeto de que por parte de D./Dña. [NOMBRE Y APELLIDOS] pueda cobrar de esta manera un anticipo reintegrable a cuenta de la cantidad objeto de condena en la cuantía de [IMPORTE] euros, haciendo constar en este momento que el aquí suscribiente se compromete a asumir solidariamente con el Estado la obligación de reintegro de lo anticipado indebidamente, si la sentencia fuera revocada.

se pueda cobrar por D./Dña. [NOMBRE Y APELLIDOS] la prestación hasta que la sentencia adquiera firmeza.

se pueda cobrar por D./Dña. [NOMBRE Y APELLIDOS] un anticipo a cuenta de la cantidad consignada en la cuantía de [IMPORTE] euros que le corresponden a esta parte legalmente.

se imponga a la demandada la obligación consistente en [DESCRIBIR] a favor de D./Dña. [NOMBRE Y APELLIDOS], mientras se tramita el recurso interpuesto.

con el objeto de exigir a la empresa demandada y condenada el cumplimiento de sus obligaciones de ocupación efectiva y pago del salario, salvo que, a su elección, opte por la efectividad de la retribución sin percibir contraprestación de servicios a cambio.

En su virtud,

SUPLICO AL TRIBUNAL.- Que teniendo por presentado este escrito, se sirva admitirlo, por realizadas las manifestaciones en él contenidas y, en méritos del mismo y tras los trámites legales oportunos, acuerde la ejecución provisional de la sentencia nº [Nº DE RESOLUCIÓN], de [COMPLETAR], recaída en el procedimiento núm. [Nº DE PROCEDIMIENTO] por la que se dicte resolución por la que se acuerde la obligación de la ejecutada de:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la sentencia condena al pago de cantidades dinerarias / Si la sentencia reconoce una prestación periódica de Seguridad Social / Si la sentencia reconoce una prestación de pago único de Seguridad Social / Si la sentencia reconoce una prestación de hacer o no hacer de Seguridad Social / Si la sentencia resuelve un despido — el texto de cada opción no venía en el formulario original]

Es justicia que pido en [LUGAR], a [FECHA].

Firmas: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
