---
name: despido-reconocimiento-relacion-laboral-demanda-168
description: "Redacta el escrito «Despido y reconocimiento de relación laboral: demanda» (formulario 168 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido y reconocimiento de relación laboral: demanda

> Formulario 0168 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] LOCALIDAD
- [ ] NÚMERO (2 veces)
- [ ] Nº (2 veces)
- [ ] NIF
- [ ] IMPORTE (2 veces)
- [ ] FECHA (4 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 16 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…. de afiliación a la Seguridad Social»; «…TO DE RELACIÓN LABORAL contra la empresa»; «…, provista de NIF [NIF], c.c.c.»; «…, c.c.c. [COMPLETAR], y domiciliada en»; «…ta de la mercantil demandada, dedicada a»; «…, desde»; «…ntrega de una factura por el concepto de»; «…imismo, la empresa me abonaba los gastos»; «…enido desempeñando siguientes funciones:»; «…través de los documentos que numero como»; «…horas mensuales, prestadas en horario de»; «…a»; …

## Elecciones que hay que hacer

- DNI / NIE / Pasaporte
- sin efecto dada la incomparecencia de la ahora demandada / sin avenencia

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- - INTERROGATORIO del representante legal de [COMPLETAR], que deberá ser citado en el domicilio indicado, bajo …
- - DOCUMENTAL, consistente en que se requiera a la [COMPLETAR] para que aporte a juicio los siguientes document…
- - DOCUMENTAL, para que se tengan por aportados los documentos que se acompañan a este escrito de demanda y los…
- - TESTIFICAL, para que los testigos que a continuación se relacionan, sean citados por vía judicial para ser e…
- D./Dña. [NOMBRE Y APELLIDOS]…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 80 de la Ley Reguladora de la Jurisdicción Social
- artículos 1.1 y 8.1 y 54 a 56 del Texto refundido de la Ley del Estatuto de los Trabajadores
- Real Decreto Legislativo 2/2015

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

### Formulario 0168 · Despido y reconocimiento de relación laboral: demanda

- Año del modelo: 2021
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 rangos de artículos despegados («25 a31» → «25 a 31»); 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 párrafos opcionales señalados; 32 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 2 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS, Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Demanda del falso autónomo solicitando la consideración de la relación como laboral y reclamando indemnización por despido improcedente o readmisión

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: Es una demanda: aún no hay plaza asignada. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con domicilio en [LOCALIDAD], provisto de [ELEGIR: DNI / NIE / Pasaporte] nº [NÚMERO] y con nº [Nº]. de afiliación a la Seguridad Social [COMPLETAR], ante el Tribunal de Instancia comparece y, como mejor proceda en Derecho, DICE:

Que por medio del presente escrito vengo en formular DEMANDA DE DESPIDO Y RECONOCIMIENTO DE RELACIÓN LABORAL contra la empresa [COMPLETAR], provista de NIF [NIF], c.c.c. [COMPLETAR], y domiciliada en [COMPLETAR], en la persona de su representante legal, a fin de que por el Tribunal se dicte Sentencia de conformidad con el suplico de la presente, en base a los siguientes hechos y fundamentos de derecho.

HECHOS

PRIMERO.- He venido prestando mis servicios por cuenta de la mercantil demandada, dedicada a [COMPLETAR], desde [COMPLETAR], y percibiendo una retribución anual de [IMPORTE] euros.

La retribución por mi trabajo se me abonaba en doce mensualidades, por importe cada una de ellas, de [IMPORTE] euros, previa entrega de una factura por el concepto de [COMPLETAR], mediante transferencia bancaria.

Asimismo, la empresa me abonaba los gastos [COMPLETAR], previa presentación del correspondiente justificante.

Durante todos estos años he venido desempeñando siguientes funciones: [COMPLETAR].

Se adjunta prueba de todo ello a través de los documentos que numero como [COMPLETAR].

SEGUNDO.- Que desempeño todas mis funciones dentro del ámbito de organización y dirección del empresario, recibiendo instrucciones sobre cómo debo desempeñar mi trabajo y realizando informes sobre el desarrollo de éste con carácter periódico y siempre que mis superiores me los solicitan.

Además, mi trabajo lo realizo en las oficinas de la empleadora, con sus medios informáticos y en un puesto de trabajo físico idéntico al resto del personal de la empresa. Tengo un horario de trabajo fijo de [Nº] horas mensuales, prestadas en horario de [COMPLETAR] a [COMPLETAR] de lunes a viernes. Disfruto de un mes de vacaciones cuya fecha de disfrute tiene que ser autorizada por el responsable del Departamento de [COMPLETAR].

TERCERO.- Que dicha relación, en la cual se dan las notas de dependencia y ajenidad, ha sido fraudulentamente estructurada como si de una por cuenta propia se tratara, habiéndome obligado la empresa a que me diera de alta en el Régimen Especial de Trabajadores Autónomos, cuando en realidad se trata de una relación laboral por cuenta ajena.

CUARTO.- Que no ha existido nunca contrato escrito entre las partes de ningún tipo, pese a las reiteradas solicitudes por mi parte para que se regularizara mi situación laboral.

QUINTO.- Que con fecha [FECHA] la empresa me ha comunicado, mediante correo electrónico, que a este escrito se acompaña como documento, que con efectos desde esa misma fecha prescindía de mis servicios, sin alegar causa alguna motivadora de dicha extinción.

Entiendo que la relación que me une a la empresa es de carácter laboral por darse todas las notas definitorias de la misma y la extinción constituye un verdadero despido que, al carecer de causa, debe considerarse improcedente.

SEXTO.- Que se ha celebrado el preceptivo acto de conciliación, el cual finalizó [ELEGIR: sin efecto dada la incomparecencia de la ahora demandada / sin avenencia], tal y como se acredita con el acta de dicha conciliación que se adjunta bajo el número [NÚMERO] de documento.

A los anteriores hechos le resultan de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I/ Es competente el Tribunal de Instancia al que se dirige el presente escrito de conformidad con los artículos 1, 2.a), 6, 10.1 de la Ley Reguladora de la Jurisdicción Social.

II/ Contiene los requisitos y exigencias del artículo 80 de la Ley Reguladora de la Jurisdicción Social.

III/ En cuanto a la reclamación sustantiva, son de aplicación los artículos 1.1 y 8.1 y 54 a 56 del Texto refundido de la Ley del Estatuto de los Trabajadores, aprobado por Real Decreto Legislativo 2/2015, de 23 de octubre.

IV/ Demás fundamentos legales y jurisprudenciales se alegarán en el momento procesal oportuno.

Por todo ello,

SUPLICO AL TRIBUNAL DE INSTANCIA, que teniendo por presentado este escrito, con sus copias y documentos que se acompañan, lo admita a trámite, tenga por formulada DEMANDA DE DESPIDO Y RECONOCIMIENTO DE EXISTENCIA DE RELACIÓN LABORAL contra [ACTO O RESOLUCIÓN], cite a los Actos de Conciliación y Juicio a las partes, se siga éste por sus trámites, incluyendo el recibimiento a prueba que desde este momento se interesa, y en su momento dicte sentencia por la que se condene a la demandada a reconocer la existencia de relación laboral desde el [FECHA], con los efectos legales inherentes a dicho reconocimiento, y se declare la improcedencia del despido con efectos desde el [FECHA], condenando a la empresa a que me abone la indemnización establecida en el art. 56 del Estatuto de los trabajadores o me readmita en mi puesto de trabajo con el abono de los salarios de tramitación desde la fecha del despido.

PRIMER OTROSÍ DIGO: Que interesa al Derecho de esta parte valerse en el Acto del Juicio de los siguientes medios de prueba:

[OPCIONAL — incluir si procede]

- INTERROGATORIO del representante legal de [COMPLETAR], que deberá ser citado en el domicilio indicado, bajo apercibimiento de tenerle por confeso si no compareciere.

[OPCIONAL — incluir si procede]

- DOCUMENTAL, consistente en que se requiera a la [COMPLETAR] para que aporte a juicio los siguientes documentos:

[OPCIONAL — incluir si procede]

- DOCUMENTAL, para que se tengan por aportados los documentos que se acompañan a este escrito de demanda y los que en su momento se aportarán.

[OPCIONAL — incluir si procede]

- TESTIFICAL, para que los testigos que a continuación se relacionan, sean citados por vía judicial para ser examinados en dicho acto de juicio:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

SEGUNDO OTROSÍ DIGO: Que esta parte asistirá al Acto del Juicio, acompañada de Letrado que le defienda y cuyo domicilio a efectos de citaciones y notificaciones se designa:

D./Dña. [NOMBRE Y APELLIDOS], [COMPLETAR].

Por todo lo expuesto,

SUPLICO AL TRIBUNAL DE INSTANCIA, que se tengan por hechas las anteriores manifestaciones y por solicitadas las pruebas propuestas, admitiéndolas y ordenando lo necesario para su práctica.

En [LUGAR], a [FECHA].

Fdo.: D. /Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
