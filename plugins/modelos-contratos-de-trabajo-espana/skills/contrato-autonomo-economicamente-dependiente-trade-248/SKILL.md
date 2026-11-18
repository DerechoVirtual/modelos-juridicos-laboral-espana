---
name: contrato-autonomo-economicamente-dependiente-trade-248
description: "Redacta el escrito «Contrato del autónomo económicamente dependiente (TRADE)» (formulario 248 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato del autónomo económicamente dependiente (TRADE)

> Formulario 0248 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] NIF
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] LOCALIDAD
- [ ] DNI/NIE (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] Nº (5 veces)
- [ ] FECHA (2 veces)
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a de prevención de riesgos laborales. En»; «…UNIDOS De una parte, el CLIENTE, empresa»; «…, domiciliada en»; «…, mayor de edad, vecino/a de»; «…, mayor de edad, vecino/a de»; «…con domicilio»; «… prestará sus servicios profesionales de»; «…o realizará el encargo u obra de»; «… realización de la obra o el servicio de»; «…con la siguiente distribución»; «… género el horario de la jornada será de»; «…pondiente de los festivos aplicable será»

## Elecciones que hay que hacer

- diarias / semanales / mensuales

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (6)

Inclúyelos solo si encajan en los hechos:

- (Supuesto en que TRADE sea víctima de violencia de género)…
- (Acuerdo de interés profesional aplicable)…
- Obligaciones en materia de prevención de riesgos laborales.- El trabajador autónomo declara que ha recibido y …
- Si el trabajador autónomo contratare personas trabajadoras por cuenta ajena deberá comunicarlo de inmediato a …
- El autónomo no podrá subcontratar con otros trabajadores autónomos o con otra empresa la realización de los tr…
- Y para que conste, se extiende este contrato por triplicado ejemplar en el lugar y fecha indicados en el encab…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 15 y 16 de la Ley 20/2007
- artículo 15 de la Ley 20/2007

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

### Formulario 0248 · Contrato del autónomo económicamente dependiente (TRADE)

- Año del modelo: 2018
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 6 párrafos opcionales señalados; 30 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
CLÁUSULAS
CLÁUSULAS ADICIONALES
Firmas

El contrato deberá formalizarse siempre por escrito y deberá ser registrado en el Servicio Público de Empleo Estatal.

El trabajador tiene un plazo de 10 días hábiles para registrarlo desde la firma del contrato. Una vez registrado deberá comunicar su inscripción al cliente en el plazo de 5 días hábiles.

Transcurrido el plazo de 15 días hábiles desde la firma del contrato sin que se haya producido la comunicación de registro del contrato por el trabajador autónomo económicamente dependiente, será el cliente quien deberá registrar el contrato en el Servicio Público de Empleo Estatal en el plazo de 10 días hábiles siguientes.

Este modelo además de hacer constar explícitamente la condición de TRADE del trabajador recoge las distintas cláusulas que regulan la relación: actividad, duración, jornada, extinción, etc., e incluye una cláusula para las obligaciones en materia de prevención de riesgos laborales.

En [COMPLETAR]

REUNIDOS

De una parte,

el CLIENTE, empresa [COMPLETAR], domiciliada en [COMPLETAR], y con NIF nº [NIF], en cuyo nombre y representación actúa D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, vecino/a de [COMPLETAR] con domicilio en [LOCALIDAD], y con DNI/NIE nº [DNI/NIE],

De otra,

el TRABAJADOR AUTÓNOMO, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, vecino/a de [COMPLETAR] con domicilio [COMPLETAR], y con DNI/NIE nº [DNI/NIE]

Ambas partes se reconocen mutuamente la capacidad legal necesaria para contratar y a tal efecto

EXPONEN

1. Que el trabajador autónomo, hace constar expresamente la condición de trabajador autónomo económicamente dependiente respecto del cliente.

2. Que el trabajador autónomo declara que su actividad como trabajador autónomo económicamente dependiente no se ejecuta de manera indiferenciada con las personas trabajadoras que presten servicio bajo cualquier modalidad de contratación laboral por cuenta del cliente y que desarrolla la actividad con criterios organizativos propios sin perjuicio de las indicaciones técnicas que pudiera percibir de su cliente, asumiendo el riesgo y ventura de la misma.

3. Que el trabajador autónomo percibe del cliente rendimientos de la actividad económica o profesional por un importe de [IMPORTE], al menos, el 75% de los ingresos totales que aquel percibe por rendimientos de trabajo y de actividades profesionales, que no tiene a su cargo personas trabajadoras por cuenta ajena ni va a subcontratar parte o toda la actividad contratada con el cliente ni las actividades que pudiera contratar con otros clientes, que dispone de infraestructura productiva y material propios, necesarios para el ejercicio de la actividad e independientes de los de su cliente, cuando en la actividad a realizar sean relevantes económicamente, que comunicará por escrito a su cliente las variaciones en la condición de dependiente económicamente que se produzcan durante la vigencia del contrato, que no es titular de establecimientos o locales comerciales e industriales y de oficinas y despachos abiertos al público y que no ejerce profesión conjuntamente con otros profesionales en régimen societario o bajo cualquier otra fórmula jurídica admitida en derecho.

4. Que ambas partes acuerdan formalizar el presente contrato de conformidad con las siguientes

CLÁUSULAS

Primera.- El trabajador autónomo económicamente dependiente prestará sus servicios profesionales de [COMPLETAR] o realizará el encargo u obra de [COMPLETAR] para el cliente, del que percibirá una contraprestación económica por la ejecución de su actividad profesional o económica o del encargo u obra por un importe de [IMPORTE] euros, cuyo abono se producirá en el tiempo y forma convenidos. El pago se efectuará en el plazo de [Nº] días desde la recepción de la factura correspondiente. En defecto de pacto, el plazo de pago será de 30 días.

Segunda.- La duración del presente contrato será de:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Por la realización de la obra o el servicio de [COMPLETAR] a contar desde el [FECHA] hasta el [FECHA] o por la finalización de la obra o servicio.

Tercera.- La jornada de la actividad profesional o económica del trabajador autónomo económicamente dependiente podrá tener una duración máxima de [Nº] horas [ELEGIR: diarias / semanales / mensuales] con la siguiente distribución [COMPLETAR].

[OPCIONAL — incluir si procede]

(Supuesto en que TRADE sea víctima de violencia de género)

En el supuesto de que la trabajadora autónoma económicamente dependiente sea víctima de la violencia de género el horario de la jornada será de [COMPLETAR].

El régimen de descanso semanal y el correspondiente de los festivos aplicable será [COMPLETAR]

El trabajador autónomo económicamente dependiente tendrá derecho a una interrupción anual de la actividad de [Nº] días.

Cuarta.- En caso de extinción contractual por desistimiento del trabajador autónomo económicamente dependiente, éste deberá preavisar al cliente en el plazo de [Nº] días. En caso de extinción contractual por voluntad del cliente por causa justificada, el cliente deberá preavisar a aquél en el plazo de [Nº] días.

Quinta.- Serán causas de extinción o de interrupción justificada del contrato, además de las establecidas en los artículos 15 y 16 de la Ley 20/2007, de 11 de julio, las siguientes:

Sexta.- La cuantía de la indemnización para el trabajador autónomo económicamente dependiente o para el cliente en virtud de lo dispuesto en el artículo 15 de la Ley 20/2007, de 11 de julio, será de [IMPORTE] euros.

[OPCIONAL — incluir si procede]

(Acuerdo de interés profesional aplicable)

Séptima.- Acuerdo de interés profesional aplicable (en el caso de existir y con la conformidad del trabajador autónomo económicamente dependiente):

.- El trabajador autónomo económicamente dependiente y el cliente se comprometen a mejorar la efectividad del derecho a la integridad física, la protección adecuada de su seguridad y salud en el trabajo, así como formación preventiva del trabajador autónomo económicamente dependiente y para ello, acuerdan las siguientes acciones:

.- El presente contrato será registrado en el Servicio Público de Empleo Estatal o en el órgano correspondiente de la Comunidad Autónoma a la que se haya encomendado la gestión, por el trabajador autónomo económicamente dependiente en el plazo de 10 días hábiles desde su perfección. El trabajador autónomo económicamente dependiente comunicará al cliente que el contrato ha sido registrado en el plazo de 5 días hábiles siguientes al registro. Transcurrido el plazo de 15 días hábiles desde la celebración del contrato, sin que se haya producido la comunicación de registro por el trabajador autónomo económicamente, el cliente deberá registrarlo en el Servicio Público de Empleo Estatal en el plazo de 10 días hábiles siguientes. Las modificaciones del contrato y su terminación serán objeto de comunicación en los mismos plazos señalados.

CLÁUSULAS ADICIONALES

[OPCIONAL — incluir si procede]

Obligaciones en materia de prevención de riesgos laborales.- El trabajador autónomo declara que ha recibido y ha comprendido la información facilitada por la empresa de los riesgos existentes en el centro de trabajo de esta, las medidas de emergencia que tiene que adoptar y las instrucciones necesarias para realizar su trabajo en condiciones de seguridad.

El trabajador autónomo, con carácter previo al inicio de sus trabajos, deberá acreditar:

- Haber realizado la evaluación de riesgos correspondientes a sus tareas y en su caso a requerimiento de la empresa una evaluación de riesgos específica en la que se contemple los riesgos derivados del ejercicio de su actividad en el centro de trabajo de la empresa.
- Tener la formación preventiva adecuada y suficiente para el desempeño de su trabajo. Esta formación será equiparable a la que debiera tener una persona trabajadora por cuenta ajena que realizara el mismo trabajo.
- Ser apto desde el punto de vista médico para el desempeño de su trabajo. El certificado de aptitud deberá ser expedido por un médico especialista en medicina del trabajo.
- Que los equipos de trabajo por él utilizada tienen marcado CE o el correspondiente certificado de adecuación.

[OPCIONAL — incluir si procede]

Si el trabajador autónomo contratare personas trabajadoras por cuenta ajena deberá comunicarlo de inmediato a la empresa quien establecerá los requisitos que en materia de prevención de riesgos laborales deberá cumplir. Mientras no se cumplan estos requisitos, la persona trabajadora contratada por el autónomo no podrá acceder al centro de trabajo de la empresa ni realizar ningún tipo de trabajo.

[OPCIONAL — incluir si procede]

El autónomo no podrá subcontratar con otros trabajadores autónomos o con otra empresa la realización de los trabajos objeto de este contrato.

[OPCIONAL — incluir si procede]

Y para que conste, se extiende este contrato por triplicado ejemplar en el lugar y fecha indicados en el encabezamiento, firmando las partes interesadas,

TRABAJADOR AUTÓNOMO

D./Dña. [NOMBRE Y APELLIDOS]

CLIENTE

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
