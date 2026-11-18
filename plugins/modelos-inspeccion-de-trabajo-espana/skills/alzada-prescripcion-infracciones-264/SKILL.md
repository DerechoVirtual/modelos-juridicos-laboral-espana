---
name: alzada-prescripcion-infracciones-264
description: "Redacta el escrito «Alzada por prescripción de infracciones» (formulario 264 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alzada por prescripción de infracciones

> Formulario 0264 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Alzada: un mes ante el órgano superior (art. 23.1 RD 928/1998, red. RD 688/2021; arts. 121-122 LPAC); no cabe si se pagó con la reducción del 40 % (art. 23.1, párr. 2.º); silencio desestimatorio a los tres meses (art. 23.2).
- Prescripción: 3 años general, 4 Seguridad Social, PRL 1/3/5 años y cooperativas 3/6/12 meses (art. 4 LISOS); interrupción por las causas del art. 7.2 RD 928/1998.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] ÓRGANO AL QUE SE DIRIGE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] FECHA (4 veces)
- [ ] ÓRGANO O PERSONA
- [ ] Nº DE EXPEDIENTE
- [ ] IMPORTE (2 veces)
- [ ] NÚMERO
- [ ] DESCRIBIR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, ya que, de conformidad con el artículo»; «…onstitutivos de la siguiente infracción:»; «…scripción de las infracciones en materia»; «…se cometió el»; «…do el plazo de prescripción aplicable de»; «…d a dictarse la resolución sancionadora:»; «…or tratarse de una infracción en materia»; «…RD 688/2021, BOE-A-2021-13382), art. 7.]»; «… sancionador. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 4 del Real Decreto Legislativo 5/2000
- artículos 23 del Real Decreto 928/1998
- Ley 39/2015

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

### Formulario 0264 · Alzada por prescripción de infracciones

- Año del modelo: 2017
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 1 desplegables y casillas convertidos en elección en blanco; 24 campos de relleno marcados en blanco
- Avisos de la revisión: Alzada: un mes ante el órgano superior (art. 23.1 RD 928/1998, red. RD 688/2021; arts. 121-122 LPAC); no cabe si se pagó con la reducción del 40 % (art. 23.1, párr. 2.º); silencio desestimatorio a los tres meses (art. 23.2). · Prescripción: 3 años general, 4 Seguridad Social, PRL 1/3/5 años y cooperativas 3/6/12 meses (art. 4 LISOS); interrupción por las causas del art. 7.2 RD 928/1998.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO SUPERIOR JERÁRQUICO DEL QUE DICTÓ LA RESOLUCIÓN, ARTS. 121.1 L 39/2015, 23 RD 928/1998 y 48 LISOS
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de recurso de alzada ante el órgano superior jerárquico del que dictó la resolución, por prescripción de infracciones, ante el órgano competente por razón de la materia, de conformidad con lo establecido en los artículos 4 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, y 7 y 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada la resolución sancionadora dictada por [ÓRGANO O PERSONA] en el expediente número [Nº DE EXPEDIENTE], y en la que se acuerda imponer a la empresa una multa de [IMPORTE] euros.

Que, contra dicha resolución, por considerarla no ajustada a Derecho, interpone RECURSO DE ALZADA en el plazo de un mes concedido al efecto, conforme establecen los artículos 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas, en base a los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que, con fecha [FECHA] se dictó resolución sancionadora que tiene su origen en el acta de infracción número [NÚMERO], en la que se impone una multa de [IMPORTE] euros, ya que, de conformidad con el artículo [COMPLETAR] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción: [COMPLETAR].

SEGUNDO.- Que, en el acta de infracción arriba referenciada es improcedente, por cuanto que se ha dictado una vez que ha superado el plazo de prescripción de las infracciones en materia [COMPLETAR], sin que exista interrupción alguna del mismo. En efecto, la infracción consistente en [DESCRIBIR] se cometió el [COMPLETAR], y el acta de la Inspección de Trabajo y Seguridad Social se levantó el día [FECHA], es decir, transcurrido el plazo de prescripción aplicable de [COMPLETAR].

TERCERO.- Que, para la demostración de las afirmaciones anteriormente manifestadas, se propone la práctica de los siguientes MEDIOS DE PRUEBA, que incomprensiblemente los órganos instructor y sancionador no admitieron con anterioridad a dictarse la resolución sancionadora: [COMPLETAR].

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

Son de aplicación los artículos 4 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, y 7 y 17 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social.

De conformidad con los cuales y por tratarse de una infracción en materia [COMPLETAR], el plazo de prescripción es de [NOTA DE REVISIÓN: Art. 4 LISOS: 3 años con carácter general; 4 años en Seguridad Social; PRL: 1 año leves, 3 graves, 5 muy graves; cooperativas: 3 meses leves, 6 graves, 1 año muy graves; desde la fecha de la infracción. Interrupción: art. 7.2 RD 928/1998; las sanciones impuestas prescriben a los 5 años desde la firmeza (art. 7.3). Fuente: RDLeg 5/2000 (LISOS), BOE-A-2000-15060, art. 4; RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 7.] [COMPLETAR], contados desde la fecha de la infracción, esto es, desde la fecha de la comisión de los supuestos hechos constitutivos del comportamiento infractor que acaecieron el día [FECHA].

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por interpuesto Recurso de Alzada con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que se deje sin efecto la resolución sancionadora impugnada y el acta de infracción, con el consiguiente archivo del expediente sancionador.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
