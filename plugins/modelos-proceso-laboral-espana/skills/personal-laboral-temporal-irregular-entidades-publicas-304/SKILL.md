---
name: personal-laboral-temporal-irregular-entidades-publicas-304
description: "Redacta el escrito «Personal laboral temporal irregular de entidades públicas: demanda para ser fijo» (formulario 304 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Personal laboral temporal irregular de entidades públicas: demanda para ser fijo

> Formulario 0304 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La reclamación previa a la vía laboral desapareció con la Ley 39/2015 (art. 69 LRJS); jurisdicción por el art. 2.a) LRJS, no 2.d).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (9 veces)
- [ ] IMPORTE (2 veces)
- [ ] art. 2.a) LRJS
- [ ] arts. 2.a), 6 y 10 LRJS
- [ ] ÓRGANO O PERSONA
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 16 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con residencia en la ciudad de»; «…, en»; «…n [COMPLETAR], comparece respetuosamente»; «…actor/a con la entidad pública demandada»; «…r cuenta y orden de la entidad demandada»; «…, con la categoría/grupo profesional de»; «… se comprometía a prestar servicios como»; «…erinidad con las siguientes condiciones:»; «…ementos salariales; Objeto del contrato:»; «…s acreditativos acompaño como documentos»; «…contratos concertados de fechas»; «…lica demandada. (Acompaño como documento»; …

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 2.a) LRJS
- arts. 2.a), 6 y 10 LRJS
- art. 4.2.b) del RD 2720/1998
- artículo 94.2 LRJS
- artículo 80.1.e) de la LRJS

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

### Formulario 0304 · Personal laboral temporal irregular de entidades públicas: demanda para ser fijo

- Año del modelo: 2017
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 33 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (FECHA, IMPORTE)
- Avisos de la revisión: La reclamación previa a la vía laboral desapareció con la Ley 39/2015 (art. 69 LRJS); jurisdicción por el art. 2.a) LRJS, no 2.d).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Identificación del demandante
HECHOS
FUNDAMENTOS DE DERECHO
Suplica
Primer otrosí
Segundo otrosí
Tercer otrosí
Suplico
Firmas

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], DNI [DNI/NIE], con residencia en la ciudad de [COMPLETAR] y domicilio a efectos de notificaciones en el del despacho profesional de don/doña [NOMBRE Y APELLIDOS], en [COMPLETAR], comparece respetuosamente [COMPLETAR] y como mejor proceda en derecho, DICE:

Que, mediante el presente escrito, al amparo de lo dispuesto en el artículo 80 y otros concordantes de la LRJS, viene a interponer DEMANDA para que se declare que el carácter de indefinido no fijo de la relación laboral que une a el/la actor/a con la entidad pública demandada [COMPLETAR], con domicilio en [LOCALIDAD], en su condición de empleadora, en base a los siguientes

HECHOS

PRIMERO.- El/La actor/a presta servicios por cuenta y orden de la entidad demandada [COMPLETAR], con la categoría/grupo profesional de [COMPLETAR], desde el día [FECHA], en virtud de los siguientes contratos:

1). En fecha [FECHA], la actora y la entidad demandada suscribieron contrato temporal por obra o servicio determinado por el que la primera se comprometía a prestar servicios como [COMPLETAR], a cambio de retribución mensual de [IMPORTE] euros (parte proporcional de pagas extraordinarias incluidas), a tiempo completo ( horas semanales) para la realización de obra o servicio consistente en

2) En fecha [FECHA], al vencimiento del anterior contrato, las partes formalizaron contrato de interinidad, en el cual se pactaban las mismas condiciones laborales y que se mantendría el contrato hasta la nueva convocatoria de plazas.

3) En fecha [FECHA], dos años después, se suscribió un nuevo contrato de trabajo temporal por interinidad con las siguientes condiciones: [COMPLETAR]; Salario: [IMPORTE] euros brutos anuales, distribuidos en los conceptos salariales de salario base y complementos salariales; Objeto del contrato: [COMPLETAR].

A efectos acreditativos acompaño como documentos [COMPLETAR] contratos concertados de fechas [COMPLETAR].

SEGUNDO.- Habiendo transcurrido seis años desde la fecha de la formalización del último de los contratos, el/la actor/a sigue desempeñando el mismo puesto en el mismo centro de trabajo, sin que se haya convocado ningún proceso de selección de personal de nuevo ingreso ni de promoción interna para la cobertura del puesto de trabajo ocupado.

Ante ello, la actora presentó reclamación administrativa previa a la vía jurisdiccional solicitando el reconocimiento del carácter indefinido de su relación laboral en fecha [FECHA], como se relatará posteriormente.

TERCERO.- Se ejercita la acción para que se declare que la relación laboral que une a las partes es de carácter indefinido, con apoyo en la doctrina jurisprudencial (entre otras SSTS 14 de julio de 2014 y 14 de octubre de 2014 que indica que, en aplicación del artículo 70.1 EBEP y el artículo 4.2.b)), la relación laboral de las personas trabajadoras interinas por vacante deviene indefinida cuando se supera el límite temporal máximo de tres años para su cobertura, y la STS de 28 de junio de 2021 que declara que superados los tres años, da derecho a un indemnización de 20 días por año, con un máximo de doce mensualidades desde que la misma quedó desierta, límite que en el caso de autos se ha superado en exceso ya que el primero de los contratos entre las partes se suscribe el día [FECHA], como ha quedado relatado, sin que a la fecha de presentación de la demanda, cerca de diez años más tarde, se hubiera procedido a ningún proceso de selección de personal de nuevo ingreso ni de promoción interna para la cobertura del puesto ocupado por el/la actor/a.

Por tanto, el contrato de interinidad por vacante ha durado más de tres años, por lo que es claro que debe reconocerse la condición de trabajador/a indefinido/a no fijo/a.

CUARTO.- En fecha [FECHA] el/la actor/a presentó reclamación previa frente a la entidad demandada [NOTA DE REVISIÓN: La reclamación previa a la vía laboral desapareció con la Ley 39/2015 (art. 69 LRJS vigente desde 2-10-2016): contra la Administración empleadora solo se agota la vía administrativa «cuando así proceda»; demanda en dos meses (art. 69.2) o veinte días hábiles si hay caducidad (art. 69.3). Esos procesos están exentos de conciliación previa (art. 64.1). Fuente: arts. 64.1 y 69 LRJS (red. Ley 39/2015); LRJS (Ley 36/2011), BOE-A-2011-15936.] solicitando se reconozca que mantiene una relación laboral indefinida, sin que haya sido contestada por parte de la entidad pública demandada.

(Acompaño como documento [COMPLETAR] copia de la reclamación previa presentada).

FUNDAMENTOS DE DERECHO

PRIMERO.- JURISDICCIÓN Y COMPETENCIA

El órgano judicial al que se dirige la demanda tiene jurisdicción [art. 2.a) LRJS] [NOTA DE REVISIÓN: La letra d) es el régimen de los TRADE; la relación laboral con la Administración empleadora es la a). Fuente: art. 2.a) y d) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.] y competencia objetiva, funcional y territorial [arts. 2.a), 6 y 10 LRJS].

SEGUNDO.- LEGITIMACIONES ACTIVA Y PASIVA

Siendo evidente la existencia de una relación laboral con el/la actor/a, esta parte tiene legitimación activa para interponer la presente demanda contra la entidad pública empleadora para reclamar su condición de empleada laboral indefinida, del mismo modo que la tiene, en su calidad de pasiva, la parte demandada mencionada.

TERCERO.- PROCEDIMIENTO ADECUADO

Dada la naturaleza de la acción emprendida por esta parte y habida cuenta de la pretensión que se incardina en la demanda, debe seguirse el trámite del procedimiento ordinario, al no existir un cauce específico para la acción, según se reitera en la interpretación de los Tribunales.

CUARTO.- FUNDAMENTOS DE FONDO

La más moderna doctrina del Tribunal Supremo considera, en aplicación del art. 70.1 de RDLegislativo 5/2015, del EBEP y el art. 4.2.b) del RD 2720/1998, expresa que la relación laboral de la persona trabajadora interina por vacante deviene indefinida cuando se supera el límite temporal máximo de tres años para su cobertura desde que la misma quedó desierta; en tal sentido, lo ha dicho la STS de 14 de octubre de 2014 que afirma que, como el contrato de interinidad por vacante había durado más de tres años, se concluye que “es claro que debe reconocérseles la condición de trabajadores indefinidos no fijos”. En consecuencia, la pretensión de esta parte es que se declare que el/la demandante tiene una relación laboral indefinida con la entidad pública demandada desde el día [FECHA], condenando a la parte demandada a las consecuencias jurídicas inherentes.

Por lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA que se admita el presente escrito, con sus copias y documentos, teniendo así por interpuesta demanda frente a la entidad [COMPLETAR], y, en su día, previos los trámites procesales oportunos, se dicte sentencia fundamentada en derecho que, otorgando tutela judicial efectiva y resolviendo todas las cuestiones debatidas, declare que el/la actor/a está vinculado/a con una relación laboral indefinida con la entidad pública demandada desde el día [FECHA], con las consecuencias inherentes a dicha condición.

PRIMER OTROSÍ DIGO [COMPLETAR]: Que señalo como domicilio a efectos de notificaciones el despacho profesional de Don/Doña [NOMBRE Y APELLIDOS] sito en [LOCALIDAD]

SEGUNDO OTROSÍ DIGO: Que sin perjuicio de otros MEDIOS DE PRUEBA que pueda utilizar en el acto de juicio, la parte actora ahora propone, a los efectos legales pertinentes, la admisión de los siguientes:

A) Documental, consistente en los siguientes documentos:

1.

2.

Todos ellos se encuentran en poder de la demandada, por lo que de conformidad con el artículo 94.2 LRJS, procede requerirla para que los aporte al acto del juicio, con apercibimiento de tenerla por confesa en caso contrario.

TERCERO OTROSI DIGO: Que, a los efectos procesales oportunos, viene a efectuar las siguientes indicaciones:

I) ADVERTENCIA DE POSTULACIÓN Y DESIGNACIÓN DE DOMICILIO

A los efectos prevenidos en el artículo 80.1.e) de la LRJS, se manifiesta que acudiré al acto del Juicio representado por [ÓRGANO O PERSONA] D./Dña. [NOMBRE Y APELLIDOS] con despacho profesional en [COMPLETAR] designando este domicilio para las notificaciones que se deriven del procedimiento y firmando asimismo esta demanda.

II) DOCUMENTACIÓN QUE SE ACOMPAÑA

Al presente escrito de demanda se adjunta, como es exigible en el presente caso, la siguiente documentación ya citada:

a) En acreditación de cumplimiento de la vía preprocesal:

b) En acreditación de la representación aducida:

c) En acreditación de la pretensión de fondo:

Por todo ello,

SUPLICO AL TRIBUNAL DE INSTANCIA. Tenga por hechas las anteriores manifestaciones a los efectos procesales oportunos y, en su virtud, se dicte resolución en las que se acceda a las mismas, efectuándose las oportunas diligencias de requerimiento para la práctica de las pruebas solicitadas.

Es Justicia que pido,

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Fdo.: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
