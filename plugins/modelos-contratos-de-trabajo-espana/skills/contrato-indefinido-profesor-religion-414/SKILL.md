---
name: contrato-indefinido-profesor-religion-414
description: "Redacta el escrito «Contrato indefinido de profesor de religión» (formulario 414 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato indefinido de profesor de religión

> Formulario 0414 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] LOCALIDAD
- [ ] Nº (3 veces)
- [ ] IMPORTE
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… EMPRESA es titular del centro educativo»; «…donde se imparten enseñanzas regladas de»; «…d y propuesto por la Confesión religiosa»; «…ligión, incluido en el grupo profesional»; «…unicará al Servicio Público de Empleo de»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 3 del Real Decreto 696/2007
- Ley Orgánica 2/2006

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

### Formulario 0414 · Contrato indefinido de profesor de religión

- Año del modelo: 2015
- Revisión 17-11-2026: 12 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

En [LUGAR], a [FECHA].

EXPONEN

I.Que la EMPRESA es titular del centro educativo [COMPLETAR] donde se imparten enseñanzas regladas de [COMPLETAR], estando interesada en la contratación de un/a profesor/a de religión

II. Que la PERSONA TRABAJADORA es profesor/a de religión, con declaración de idoneidad y propuesto por la Confesión religiosa [COMPLETAR], reuniendo los demás requisitos establecidos en el artículo 3 del Real Decreto 696/2007.

III. Que reuniendo ambas partes las condiciones exigidas para la celebración del presente contrato acuerdan formalizarlo con arreglo a las siguientes

CLAÚSULAS

La persona trabajadora prestará sus servicios como Profesor/a de Religión, incluido en el grupo profesional [COMPLETAR], para la realización de las funciones docentes en el centro educativo sito en [LOCALIDAD] de

La jornada de trabajo será a tiempo completo, con una duración de [Nº] horas semanales, y con la siguiente distribución del tiempo de trabajo:

La duración del presente contrato será INDEFINIDA, iniciándose la relación laboral el día [FECHA] y estableciéndose un periodo de prueba de [Nº] meses.

La PERSONA TRABAJADORA percibirá una retribución total de [IMPORTE] euros brutos que se distribuirán por los siguientes conceptos salariales:

La duración de las vacaciones anuales será de [Nº] días.

El contrato de trabajo se extinguirá por las siguientes causas:

a) cuando la Administración competente adopte resolución en tal sentido, previa incoación de expediente disciplinario;

b) por revocación ajustada a derecho de la acreditación o de la idoneidad para impartir clases de religión por parte de la Confesión religiosa que la otorgó;

c) por las demás causas de extinción previstas en el Estatuto de los Trabajadores; y

d) en el caso de personas trabajadoras extranjeras, por la extinción o la no renovación de la autorización de residencia o de residencia y trabajo, como consecuencia de la concurrencia de alguno de los supuestos para dicha extinción o el incumplimiento de alguno de los requisitos para la renovación establecidos en la normativa de extranjería e inmigración.

En lo no previsto en este contrato se estará a lo previsto en la normativa de aplicación y, en particular, a lo dispuesto en el Real Decreto 696/2007, de 1 de junio, por el que se regula la relación laboral de los/las profesores/as de religión prevista en la disposición adicional tercera de la Ley Orgánica 2/2006, de 3 de mayo, de Educación, y en el Estatuto de los Trabajadores.

El contenido del presente contrato se comunicará al Servicio Público de Empleo de [COMPLETAR] en el plazo de los diez días siguientes a su concertación.

En prueba de conformidad, una vez leído el contrato, ambas partes firman el presente documento a un solo efecto, en el lugar y fecha indicados en el encabezamiento.

LA EMPRESA LA PERSONA TRABAJADORA

================================================================================
