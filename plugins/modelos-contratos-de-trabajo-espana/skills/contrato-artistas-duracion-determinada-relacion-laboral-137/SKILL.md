---
name: contrato-artistas-duracion-determinada-relacion-laboral-137
description: "Redacta el escrito «Contrato de artistas de duración determinada (relación laboral especial)» (formulario 137 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato de artistas de duración determinada (relación laboral especial)

> Formulario 0137 del plugin **Contratación laboral** · revisado el 17-11-2026.

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
- [ ] FECHA (4 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NIF
- [ ] Nº (5 veces)
- [ ] IMPORTE
- [ ] Otros 16 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nombre y representación de la productora»; «…, NIF/CIF [NIF], domiciliada en»; «…y constituida en»; «…ante el Notario de»; «…e inscrita en el Registro Mercantil de»; «…inscripción»; «…d la producción de espectáculos públicos»; «…, estando en la actualidad produciendo»; «…a contratar con carácter temporal, desde»; «…inada para la prestación de servicios de»; «…A prestará sus servicios como de la obra»; «…, producida por la EMPRESA, desde»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto 1435/1985

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

### Formulario 0137 · Contrato de artistas de duración determinada (relación laboral especial)

- Año del modelo: 2022
- Revisión 17-11-2026: 32 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Encabezamiento
INTERVIENEN
MANIFIESTAN
CLÁUSULAS
Firmas

Los contratos de duración determinada de artistas y del personal técnico y auxiliar se encuadran en la relación laboral especial de las personas artistas que desarrollan su actividad en las artes escénicas, audiovisuales y musicales, así como de quienes realizan actividades técnicas o auxiliares necesarias para el desarrollo de dicha actividad. Esta relación comprende tanto a las personas artistas como al personal técnico y auxiliar vinculado directamente a la actividad artística e imprescindible para su ejecución, siempre que estas actividades no sean estructurales o permanentes de la empresa, aunque se desarrollen de modo cíclico.

El contrato laboral artístico de duración determinada puede concertarse para una o varias actuaciones, por un tiempo cierto, por una temporada, por el tiempo que una obra permanezca en cartel o por el tiempo que duren las distintas fases de la producción. También pueden pactarse prórrogas sucesivas, pero únicamente mientras persista la necesidad temporal que justificó su celebración.

La temporalidad está sometida a una exigencia reforzada de causalidad. Para que exista causa justificada de temporalidad, debe especificarse con precisión en el contrato la causa habilitante de la contratación temporal, las circunstancias concretas que la justifican y su conexión con la duración prevista.

En [LUGAR], a [FECHA].

INTERVIENEN

D./Dña. [NOMBRE Y APELLIDOS], interviene en nombre y representación de la productora [COMPLETAR], NIF/CIF [NIF], domiciliada en [COMPLETAR] y constituida en [COMPLETAR] ante el Notario de [COMPLETAR] D./Dña. [NOMBRE Y APELLIDOS], en fecha [FECHA] e inscrita en el Registro Mercantil de [COMPLETAR] inscripción [COMPLETAR], en adelante la EMPRESA.

D/Dña. [NOMBRE Y APELLIDOS], interviene en su propio nombre y derecho, en adelante el/la ARTISTA.

MANIFIESTAN

Que reconociéndose mutuamente las partes la capacidad legal necesaria a los efectos de este CONTRATO DE TRABAJO DE RELACIÓN LABORAL ESPECIAL DE ARTISTAS DE DURACIÓN DETERMINADA, siendo responsables de la veracidad de sus manifestaciones, y de forma libre, espontánea y de mutuo acuerdo

EXPONEN

Que la EMPRESA tiene como actividad la producción de espectáculos públicos [COMPLETAR], estando en la actualidad produciendo [COMPLETAR], cuyo estreno está previsto en fecha [FECHA].

II. Que el/la ARTISTA se dedica profesionalmente a la dirección escénica.

III. La EMPRESA necesita contratar con carácter temporal, desde [COMPLETAR], estando previsto inicialmente un periodo de [Nº] meses, sin perjuicio de que pueda prolongarse en función de los resultados de público.

IV. Ambas partes están interesadas en concertar el presente contrato de duración determinada para la prestación de servicios de [COMPLETAR] en la obra producida por la EMPRESA, por lo que, reuniendo los requisitos exigidos para la celebración del presente contrato acuerdan formalizarlo con arreglo a las siguientes

CLÁUSULAS

PRIMERA.- Objeto: El/la ARTISTA prestará sus servicios como de la obra [COMPLETAR], producida por la EMPRESA, desde [COMPLETAR], con una previsión inicial de [Nº] meses.

El/la ARTISTA prestará sus servicios dentro del ámbito de organización y dirección de la EMPRESA, aplicando la diligencia específica que corresponde a sus personales aptitudes artísticas, y siguiendo las instrucciones de la EMPRESA en lo que afecte a la organización de la obra, así como a la forma y lugar ejecución de las actuaciones ante el público.

Los servicios artísticos objeto de este contrato serán los siguientes:

SEGUNDA,- Duración: La duración del presente contrato será de DURACIÓN DETERMINADA, por el tiempo en que la obra expresada permanezca en cartelera, iniciándose la relación laboral el día [FECHA] y finalizando el día que deje de representarse la obra para el público.

Ambas partes manifiestan expresamente que concurre causa justificada de temporalidad por concertarse la prestación de servicios en conexión con la producción y representación de la obra referenciada.

TERCERA- Periodo de prueba: Las partes conciertan un periodo de prueba de [Nº] DÍAS de duración. Transcurrido el periodo de prueba sin que se haya producido el desistimiento, el contrato producirá plenos efectos, computándose el tiempo de los servicios prestados en la antigüedad del ARTISTA en la empresa.

CUARTA- Retribución: El/la ARTISTA percibirá una retribución total de [IMPORTE] euros brutos en catorce mensualidades que se distribuirán por los siguientes conceptos salariales: [COMPLETAR].

La retribución engloba todos los conceptos, incluyendo los tiempos de disponibilidad.

QUINTA.- Jornada de trabajo: La jornada de trabajo será a tiempo completo, con una duración de [Nº] horas semanales, y con la siguiente distribución del tiempo de trabajo [COMPLETAR].

La jornada comprende tanto la prestación efectiva de su actividad artística ante el público, como el tiempo en que el/la ARTISTA está bajo las órdenes de la EMPRESA, a efectos de ensayos, producción o grabación de actuaciones.

SEXTA.- Descansos y vacaciones: El/la ARTISTA disfrutará de un descanso mínimo semanal de día y medio, que coincidirá con los días en que no se represente la obra en cartelera.

Cuando no puedan disfrutarse las fiestas incluidas en el calendario laboral por desarrollarse en ellas la actividad artística ante el público, el descanso se trasladará a una fecha a determinar dentro del mes siguiente en que no hayan de realizarse actividades artísticas ante el público.

El/la ARTISTA tendrá derecho a las vacaciones anuales retribuidas de [Nº] días naturales, que serán fijadas de mutuo acuerdo con arreglo a los criterios establecidos para la planificación anual de vacaciones.

SÉPTIMA.- Incumplimiento. El incumplimiento del contrato por la empresa o por la persona trabajadora, que conlleve la inejecución total de la prestación artística, se regirá por lo establecido al respecto en el Código Civil.

Por inejecución total se entenderán aquellos supuestos en los que ni siquiera hubiera empezado a realizarse el trabajo que constituye la prestación pactada

OCTAVA.- Extinción: El contrato de trabajo se extinguirá por las causas previstas en la normativa vigente.

La EMPRESA deberá observar un periodo de preaviso de la extinción en función de la duración del contrato según el tiempo de permanencia de la obra en cartel. Si la duración ha sido no superior a seis meses, la EMPRESA deberá preavisar al/a la ARTISTA con diez días de antelación, en tanto que si la duración del contrato ha sido superior a seis meses, la EMPRESA deberá preavisar con quince días de antelación. El incumplimiento de esta obligación por parte de la EMPRESA dará lugar al abono al/a la ARTISTA de una indemnización equivalente al salario de los días en que dicho plazo se hubiera incumplido.

A la finalización del contrato, ambas partes pactan expresamente que el/la ARTISTA tendrá derecho a recibir una indemnización de cuantía equivalente a la parte proporcional de la cantidad que resultaría de abonar veinte días de salario por cada año de servicio, con independencia de la duración del contrato.

NOVENA.- Comunicaciones: Ambas partes realizarán las comunicaciones derivadas de este contrato, de modo preferente, en las direcciones de correo electrónico que constan en el encabezamiento, sin perjuicio de utilizar otros medios que estimen pertinentes. En cualquier caso, la comunicación vía correo electrónico y su acuse de recibo producirá plenos efectos.

DÉCIMA.- Normativa supletoria: En lo no previsto en este contrato se estará a lo previsto en la normativa de aplicación y, en particular, a lo dispuesto en el Real Decreto 1435/1985, de 1 de agosto, por el que se regula la relación laboral especial de los artistas en espectáculos públicos. y en el Estatuto de los Trabajadores, así como a la regulación del Convenio Colectivo de [COMPLETAR].

UNDÉCIMA.- Comunicación al SEPE: El contenido del presente contrato se comunicará al Servicio Público de Empleo de [COMPLETAR] en el plazo de los diez días siguientes a su concertación.

DUODÉCIMA.- Jurisdicción competente: Los conflictos que surjan entre el/la ARTISTA y la EMPRESA como consecuencia del contrato de trabajo serán competencia de los jueces y tribunales del orden jurisdiccional social.

En prueba de conformidad, una vez leído el contrato, ambas partes firman el presente documento a un solo efecto, en el lugar y fecha indicados en el encabezamiento.

LA EMPRESAEL/LA ARTISTA

D./Dña. [NOMBRE Y APELLIDOS] D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
