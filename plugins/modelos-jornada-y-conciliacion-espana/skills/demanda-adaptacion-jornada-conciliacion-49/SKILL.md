---
name: demanda-adaptacion-jornada-conciliacion-49
description: "Redacta el escrito «Demanda de adaptación de jornada por conciliación» (formulario 49 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda de adaptación de jornada por conciliación

> Formulario 0049 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] NÚMERO
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] CORREO ELECTRÓNICO
- [ ] NIF
- [ ] IMPORTE (3 veces)
- [ ] FECHA (5 veces)
- [ ] DESCRIBIR
- [ ] LUGAR
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…caciones en el despacho del/la Letrado/a»; «… DE DAÑOS Y PERJUICIOS contra la empresa»; «…do para la empresa demandada, dedicada a»; «…establecido en el art. 34.8 del ET, para»; «…ación solicitaba la siguiente adaptación»; «…tados y me proponía como alternativa que»; «…Las razones alegadas por la empresa eran»; «… y familiar y ocuparme de forma adecuada»; «…bien conoce la empresa, es la siguiente:»; «…ibilidad de no adaptar mi jornada ya que»; «…que trabajar en un horario que le impide»; «… DE DAÑOS Y PERJUICIOS contra la empresa»; …

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- - INTERROGATORIO del representante legal de la demandada para que bajo juramento indecisorio absuelva las posi…
- - DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral la siguiente …
- - DOCUMENTAL y TESTIFICAL, la que se aporta con la demanda y la que se aportará en el acto del juicio oral.…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 139 LRJS
- artículo 139 de la LRJS
- art. 34.8 del ET
- artículo 139.1 a) LRJS
- artículo 14 CE
- artículo 39 CE

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

### Formulario 0049 · Demanda de adaptación de jornada por conciliación

- Año del modelo: 2024
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 3 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 huecos del original que se habían perdido sin marca, marcados (IMPORTE)
- Avisos de la revisión: Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]
HECHOS
MEDIOS DE PRUEBA
Firmas

Los arts. 34.8 (último párrafo) y 37.7 ET establecen que las discrepancias que surjan entre empresarios y trabajadores en relación con el ejercicio de los derechos de conciliación de la vida personal, familiar y laboral reconocidos legal o convencionalmente se resolverán por la jurisdicción social a través del procedimiento establecido en el art. 139 LRJS. [NOTA DE REVISIÓN: La disposición adicional 19.ª ET regula el cálculo de indemnizaciones con jornada reducida; la remisión al procedimiento del art. 139 LRJS está en los arts. 34.8 y 37.7 ET. Fuente: ET (RDLeg 2/2015), BOE-A-2015-11430, arts. 34.8 y 37.7 y DA 19.ª.]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], y con domicilio a efectos de notificaciones en el despacho del/la Letrado/a [COMPLETAR], Col. nº [NÚMERO] del Ilustre Colegio de Abogados de [COLEGIO], sito en [LOCALIDAD], tel. y correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA ADAPTACIÓN DE MI JORNADA PARA HACER EFECTIVO MI DERECHO A LA CONCILIACIÓN DE LA VIDA FAMILIAR Y LABORAL, ASÍ COMO AL PERCIBO DE UNA INDEMNIZACIÓN DE DAÑOS Y PERJUICIOS contra la empresa [COMPLETAR], con NIF [NIF], y domicilio en [LOCALIDAD], en la persona de su legal representante, que deberá tramitarse conforme al artículo 139 de la LRJS.

Se basa esta demanda en los siguientes

HECHOS

PRIMERO.- He trabajado para la empresa demandada, dedicada a [COMPLETAR], con las siguientes condiciones laborales:

• Antigüedad:
• Tipo de contrato:
• Jornada:
• Grupo profesional:
• Centro de trabajo:
• Salario: [IMPORTE] euros brutos anuales
• Convenio colectivo de aplicación:

SEGUNDO.- Con fecha [FECHA] solicité la adaptación de mi jornada de trabajo por razones de conciliación de la vida familiar y laboral, en virtud de lo establecido en el art. 34.8 del ET, para [COMPLETAR].

En mi comunicación solicitaba la siguiente adaptación [COMPLETAR].

Se acompaña como DOCS. 1 carta de solicitud.

TERCERO.- Con fecha [FECHA] la empresa me envió una carta en la que me comunicaba que no era posible adaptar mi jornada en los términos solicitados y me proponía como alternativa que [COMPLETAR].

Las razones alegadas por la empresa eran [COMPLETAR].

Se acompaña como DOC. 2 copia de dicha carta.

CUARTO.- Con fecha [FECHA] contesté a la empresa diciéndoles que para poder conciliar mi vida laboral y familiar y ocuparme de forma adecuada [COMPLETAR], no podía aceptar su propuesta ni hacer un horario que implicase la rotación pretendida en su carta siendo la adaptación solicitada por mí la única forma que me permite conciliar el trabajo con sus cuidados.

Se acompaña como DOC. 4 copia de dicha carta.

QUINTO.- Con fecha [FECHA] la empresa me comunicó la finalización del período de negociación y la imposibilidad de adaptar mi jornada, teniendo que continuar con la jornada y el horario que vengo haciendo.

Se acompaña como DOC. 5 copia de dicha carta.

SEXTO.- En cuanto a mi situación familiar, como bien conoce la empresa, es la siguiente: [COMPLETAR].

Se acompañan como DOCS. certificados acreditativos de los externos anteriores.

SÉPTIMO.- La empresa no justifica en absoluto la imposibilidad de no adaptar mi jornada ya que [COMPLETAR].

OCTAVO.- Las personas trabajadoras tienen derecho a solicitar las adaptaciones de la duración y distribución de la jornada de trabajo, en la ordenación del tiempo de trabajo y en la forma de prestación, incluida la prestación de su trabajo a distancia, para hacer efectivo su derecho a la conciliación de la vida familiar y laboral. Dichas adaptaciones deberán ser razonables y proporcionadas en relación con las necesidades de la persona trabajadora y con las necesidades organizativas o productivas de la empresa.

La delimitación temporal del derecho a la adaptación de jornada dependerá del presupuesto de hecho en que se funde. Por lo que respecta a las necesidades de conciliación derivadas del cuidado y atención de los hijos, el propio legislador señala que el derecho podrá ejercerse hasta que el menor cumpla los doce años. Pero si la solicitud de adaptación de jornada se basa en necesidades de conciliación derivadas de la atención y el cuidado de hijos mayores de esa edad o de otros familiares o personas del entorno, el legislador no prevé limitación temporal expresa, por lo que habrá que estar a cada caso en concreto.

Además, la última reforma aclaró que la titularidad del derecho era individual; si bien, permitió limitar su ejercicio por razones justificadas de funcionamiento de la empresa cuando dos o más trabajadores de la misma generaran este derecho por el mismo sujeto causante. Advirtió, finalmente, que la concreción horaria y la determinación del período de disfrute correspondía al trabajador dentro de su jornada ordinaria y que las discrepancias que pudieran surgir al respecto serían resueltas por la Jurisdicción Social a través de un proceso especial.

La empresa le ha denegado el derecho de adaptación de jornada al trabajador sin razón alguna que lo justifique, lo que supone una violación del art. 34.8 del ET. La negativa de la empresa únicamente estaría justificada en caso de imposibilidad, sacrificio excesivo o daño desproporcionado, no bastando la dificultad organizativa, el mero trastorno o la conveniencia.

NOVENO.- El artículo 139.1 a) LRJS prevé que en la demanda del derecho a la medida de conciliación puede acumularse la acción de daños y perjuicios causados al trabajador, exclusivamente por los derivados de la negativa del derecho o de la demora en la efectividad de la medida, de los que el empresario podrá exonerarse si hubiere dado cumplimiento, al menos provisional, a la medida propuesta por el trabajador.

El Tribunal Supremo (STS 310/2023, de 26/04/2023, rec. 1040/2020) afirma que cuando se impide la conciliación se están vulnerando derechos fundamentales como el de no discriminación por razón de circunstancias personales (artículo 14 CE) y a la protección de la familia y la infancia (artículo 39 CE), tal y como señala la sentencia del Tribunal Constitucional 26/2011 de 14 de marzo. La empresa ha «impedido indebidamente la conciliación de la vida familiar y laboral del trabajador», señalan los magistrados.

Toda vez que la empresa no ha aceptado ninguna de las propuestas del trabajador y tiene que trabajar en un horario que le impide [COMPLETAR] y le causa un gravísimo perjuicio, se solicita una indemnización de [IMPORTE] euros.

En apoyo de la presente demanda se formularán en el acto del juicio oral los oportunos Fundamentos de Derecho.

Por lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA que teniendo por presentado este escrito con sus copias y documentos que lo acompañan, se sirva admitirlo y tenga por formulada DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA ADAPTACIÓN DE MI JORNADA PARA HACER EFECTIVO MI DERECHO A LA CONCILIACIÓN DE LA VIDA FAMILIAR Y LABORAL, ASÍ COMO AL PERCIBO DE UNA INDEMNIZACIÓN DE DAÑOS Y PERJUICIOS contra la empresa [COMPLETAR], señalando día y hora para la celebración del acto de conciliación o, en su caso, juicio, y en su día, previos los trámites procesales oportunos, dicte Sentencia por la que se declare el derecho del actor a la adaptación de jornada consistente en [DESCRIBIR] y se condene a la empresa a que le abone una indemnización de daños y perjuicios de [IMPORTE] euros.

Por ser de justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO, que acudiré al acto del juicio oral asistido/a de Letrado/a.

SEGUNDO OTROSÍ DIGO, que interesa al derecho de esta parte que se practiquen en el acto del juicio oral los siguientes

MEDIOS DE PRUEBA

[OPCIONAL — incluir si procede]

- INTERROGATORIO del representante legal de la demandada para que bajo juramento indecisorio absuelva las posiciones que se le formularán en su momento, y con el apercibimiento de tenerlo por confeso en caso de incomparecencia, para lo que debe ser citado oportunamente en el domicilio de la empresa indicado en el encabezamiento.

[OPCIONAL — incluir si procede]

- DOCUMENTAL consistente en que se requiera a la empresa para que aporte al acto del juicio oral la siguiente documentación:

1º) [COMPLETAR]
2º) [COMPLETAR]

[OPCIONAL — incluir si procede]

- DOCUMENTAL y TESTIFICAL, la que se aporta con la demanda y la que se aportará en el acto del juicio oral.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones, por propuesta la prueba, la admita y la declare pertinente y acuerde su práctica, así como las citaciones y requerimientos oportunos.

Es de Justicia que reitero en el lugar y fecha ut supra.

════════════════════════════════════════════════════════════════════════
