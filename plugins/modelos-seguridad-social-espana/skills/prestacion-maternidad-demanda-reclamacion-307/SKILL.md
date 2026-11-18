---
name: prestacion-maternidad-demanda-reclamacion-307
description: "Redacta el escrito «Prestación por maternidad: demanda de reclamación» (formulario 307 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prestación por maternidad: demanda de reclamación

> Formulario 0307 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- «Maternidad» es hoy «nacimiento y cuidado de menor» (arts. 177 a 180 LGSS); periodo mínimo del art. 178.1 (red. RDL 9/2025): 90 días en 7 años o 180 en la vida laboral entre 21 y 26 años, 180 en 7 años o 360 desde los 26; a tiempo parcial no hay coeficiente de parcialidad (art. 247.1).
- «Juzgado de lo Social» → Sección de lo Social del Tribunal de Instancia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] LOCALIDAD (2 veces)
- [ ] CALLE
- [ ] FECHA (3 veces)
- [ ] IMPORTE (2 veces)
- [ ] FECHA DE LA RESOLUCIÓN (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Dña»; «…GSS. Demanda que baso en los siguientes:»; «…e carencia exigible a mi defendida es de»; «…,»

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 4 y 21 LOPJ
- arts. 2.o), 6 y 10 Ley 36/2011
- Real Decreto Legislativo 8/2015

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

### Formulario 0307 · Prestación por maternidad: demanda de reclamación

- Año del modelo: 2011
- Revisión 17-11-2026: 6 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 10 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 4 huecos del original que se habían perdido sin marca, marcados (FECHA, FECHA DE LA RESOLUCIÓN, IMPORTE)
- Avisos de la revisión: «Maternidad» es hoy «nacimiento y cuidado de menor» (arts. 177 a 180 LGSS); periodo mínimo del art. 178.1 (red. RDL 9/2025): 90 días en 7 años o 180 en la vida laboral entre 21 y 26 años, 180 en 7 años o 360 desde los 26; a tiempo parcial no hay coeficiente de parcialidad (art. 247.1). · «Juzgado de lo Social» → Sección de lo Social del Tribunal de Instancia.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Demanda de reclamación de prestación de maternidad
Dice
HECHOS
FUNDAMENTOS DE DERECHO
Suplico al Tribunal
Otrosí digo
Segundo otrosí digo
Firmas

Demanda de reclamación de prestación de maternidad

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: Demanda: sin número de plaza. Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

Dña [COMPLETAR], mayor de edad, con domicilio en [LOCALIDAD], C/ [CALLE], provisto de D.N.I, ante ese Tribunal comparece y como mejor proceda en derecho D I C E:

Que mediante el presente escrito formulo demanda, que deberá ser tramitada por la modalidad procesal de prestaciones de la Seguridad Social, en reclamación de PRESTACIÓN DE MATERNIDAD del Régimen General, denegada por la resolución de fecha [FECHA] del INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, por la que se desestima la reclamación previa presentada por el que suscribe en fecha [FECHA], por estimar que la misma no se ajusta a derecho, y resultan perjudicial para mis intereses, dicho sea con los debidos respecto y en términos de defensa, la cual dirijo contra el INSS y la TGSS.

Demanda que baso en los siguientes: [COMPLETAR]

HECHOS

La demandante, afiliada a la Seguridad Social con el núm, presta servicios en la empresa de a en virtud de contrato a tiempo parcial con una jornada del % ( días).

Con anterioridad prestó servicios en la empresa en virtud de contrato a tiempo parcial con una jornada del % ( días).

En fecha tuvo lugar el nacimiento de su hijo, según acredito mediante certificado de nacimiento que acompaño como documento número, teniendo la madre una edad superior a los 26 años y hallándose en situación de alta en el régimen general.

En fecha [FECHA] inició el descanso maternal, siéndole denegado el derecho a la prestación por maternidad por no reunir el período mínimo de cotización.

La base reguladora diaria es de [IMPORTE] euros.

Interpuesta reclamación previa, por resolución de fecha [FECHA DE LA RESOLUCIÓN] se desestimó la misma, haciéndose constar que acredita días con inclusión de la parte proporcional de pagas extraordinarias, en el período legalmente establecido para los contratos a tiempo parcial (acompaño como documentos escrito de reclamación previa y resolución desestimatoria de fecha [FECHA DE LA RESOLUCIÓN]).

Por lo expuesto, y estando disconforme con la resolución administrativa impugnada, tal como se argumentará extensamente en la fundamentación jurídica de esta demanda, interpongo la presente acción en reclamación de la prestación de maternidad.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

.- En cuanto a los sujetos procesales y procedimiento, este órgano judicial al que se dirige la demanda tiene jurisdicción (arts. 4 y 21 LOPJ) y competencia objetiva, funcional y territorial (arts. 2.o), 6 y 10 Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social) para conocer del juicio que se suscita, quedando válidamente constituida la relación jurídico-procesal por ostentar las partes legitimación activa y pasiva; por otra parte, la pretensión deducida debe seguirse por los trámites de la modalidad procesal de prestaciones de Seguridad Social.

.- En cuanto a los requisitos para el reconocimiento del derecho es de aplicación el artículo 178.1. apartado c) del Real Decreto Legislativo 8/2015, de 30 de octubre, por el que se aprueba el texto refundido de la Ley General de la Seguridad Social (en adelante TRLGSS), el cual dispone que “si el trabajador es mayor de 26 años de edad en la fecha del parto o en la fecha de la decisión administrativa o judicial de acogimiento o de la resolución judicial por la que se constituye la adopción, el período mínimo de cotización exigido será de 180 días dentro de los siete años inmediatamente anteriores al momento de inicio del descanso. Se considerará cumplido el mencionado requisito si, alternativamente, el trabajador acredita 360 días cotizados a lo largo de su vida laboral, con anterioridad a esta última fecha”.

.- En relación al cómputo de los periodos de cotización en los contratos a tiempo parcial, es de aplicación el art. 247 TRLGSS que establece que a efectos de acreditar, entre otros, los períodos de cotización necesarios para causar derecho a la prestación de maternidad se deben tener en cuenta los distintos períodos durante los cuales el trabajador haya permanecido en alta con un contrato a tiempo parcial, cualquiera que sea la duración de la jornada realizada en cada uno de ellos y el coeficiente de parcialidad, que viene determinado por el porcentaje de la jornada realizada a tiempo parcial respecto de la jornada realizada por un trabajador a tiempo completo comparable, que se aplica sobre el período de alta con contrato a tiempo parcial, siendo el resultado el número de días que se considerarán efectivamente cotizados en cada período. Si se trata del subsidio por maternidad y paternidad, el coeficiente global de parcialidad [NOTA DE REVISIÓN: El art. 247.1 vigente computa los periodos a tiempo parcial «cualquiera que sea la duración de la jornada»; ya no hay coeficiente global de parcialidad. Además, «maternidad/paternidad» es hoy «nacimiento y cuidado de menor» (arts. 177 a 180 LGSS). Fuente: arts. 177, 178 y 247 LGSS (art. 247 red. RDL 11/2024, vigente 1-4-2025; art. 178 red. RDL 9/2025, BOE-A-2025-15741); LGSS (RDLeg 8/2015), BOE-A-2015-11724.] se calculará sobre los últimos siete años o, en su caso, sobre toda la vida laboral. Para determinar el periodo mínimo de cotización con arreglo a lo dispuesto en el citado art. 178.1.c) ha de aplicarse a dicho período el coeficiente global de parcialidad

En este caso, la aplicación del coeficiente global de parcialidad sobre los últimos siete años arroja un....% de manera que el periodo de carencia exigible a mi defendida es de [COMPLETAR], por lo que la resolución administrativa impugnada infringe las normas legales sobre el cálculo del periodo de carencia al no haberlo reducido en la proporción que resulta del coeficiente global de parcialidad.

.- En cuanto a la cuantía económica de la prestación, es de aplicación el artículo 179 TRLGSS, el cual establece que la prestación económica por maternidad consistirá en un subsidio equivalente al 100 % de la base reguladora correspondiente. A tales efectos, la base reguladora debe calcularse conforme al art. 248.1.b) TRLGSS [NOTA DE REVISIÓN: La base reguladora del subsidio por nacimiento y cuidado a tiempo parcial está en el art. 248.1.b); el 278 es la cuantía del subsidio por desempleo. Fuente: arts. 248 (red. RDL 11/2024) y 278 (red. RDL 2/2024) LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.], por todo lo cual se solicita su anulación y que se declare el derecho de la demandante a la prestación de maternidad solicitada.

Por lo expuesto, respetuosamente

SUPLICO AL TRIBUNAL Que tenga por presentado este escrito, con sus copias y documento, se sirva admitirlo, tener por interpuesta la presente demanda en reclamación sobre PRESTACIÓN DE MATERNIDAD, contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL y contra la TESORERÍA TERRITORIAL DE LA SEGURIDAD SOCIAL, y previo los trámites legales oportunos, señale día y hora para la celebración del oportuno Acto de Juicio, y en definitiva, dicte Sentencia por la que se declare:

A) Se deje sin efecto y anule la Resolución recurrida.

B) Se declare el derecho de la actora a la prestación de maternidad, con una base reguladora diaria de [IMPORTE] euros, condenando al INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL y a la TESORERIA GENERAL DE LA SEGURIDAD SOCIAL, a pasar por dicha declaración con todas las consecuencias legales inherentes a la misma.

OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por Letrado (graduado social colegiado/procurador), designando a D, con domicilio profesional en [LOCALIDAD], [COMPLETAR] el cual suscribe esta demanda y cuyo domicilio se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes.

SEGUNDO OTROSÍ DIGO: Que sin perjuicio de las pruebas que en su día pueda proponer en el acto del juicio oral interesa al derecho de esta parte que se requiera al organismo competente del INSS y de la TGSS se aporte el Expediente Administrativo, que dio origen a la presente demanda.

SUPLICO AL TRIBUNAL: Acuerde practicar los requerimientos interesados

Por ser de justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del demandante y letrado/procurador/graduado social colegiado

════════════════════════════════════════════════════════════════════════
