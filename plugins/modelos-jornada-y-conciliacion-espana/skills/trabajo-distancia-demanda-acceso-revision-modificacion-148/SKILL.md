---
name: trabajo-distancia-demanda-acceso-revision-modificacion-148
description: "Redacta el escrito «Trabajo a distancia: demanda por acceso, revisión o modificación» (formulario 148 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Trabajo a distancia: demanda por acceso, revisión o modificación

> Formulario 0148 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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
- [ ] DNI/NIE
- [ ] PROVINCIA
- [ ] CORREO ELECTRÓNICO
- [ ] FECHA (5 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE
- [ ] ACTO O RESOLUCIÓN
- [ ] COLEGIO (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, domiciliado en la localidad de»; «…, provincia de [PROVINCIA], en»; «…, situado en»; «…, de la localidad de»; «…, teléfono móvil»; «…, teléfono móvil [COMPLETAR], fax»; «…, la cual dirijo contra la empresa»; «…restando sus servicios en la misma desde»; «…, en el centro de trabajo de»; «…ntando la categoría/grupo profesional de»; «… amplias que en derecho hubiere lugar, a»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 5 y 8 de la Ley 10/2021
- art. 10.1 de la LRJS
- art. 17 de la LRJS
- art. 138 bis de la LRJS
- art. 138 bis.1.c) de la LRJS
- art. 5.3 de la Ley 10/2021
- artículo 138.1.b) de la LJS

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

### Formulario 0148 · Trabajo a distancia: demanda por acceso, revisión o modificación

- Año del modelo: 2021
- Revisión 17-11-2026: 30 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
Presentación
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Primer otrosí. Representación
Segundo otrosí. Documentación
Tercer otrosí. ITSS
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./D.ª [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE], domiciliado en la localidad de [COMPLETAR], provincia de [PROVINCIA], en [COMPLETAR], y señalando a efectos de notificaciones el despacho profesional de D. / Dña. [NOMBRE Y APELLIDOS], situado en [COMPLETAR], de la localidad de [COMPLETAR], dirección de correo electrónico [CORREO ELECTRÓNICO], teléfono móvil [COMPLETAR], fax [COMPLETAR], ante el Tribunal de Instancia que por turno de reparto corresponda comparezco y, como mejor proceda en Derecho DIGO

Que mediante el presente escrito formulo demanda por la modalidad procesal sobre acceso, reversión y modificación del trabajo a distancia, al amparo de lo dispuesto del art. 138 bis de la Ley reguladora de la Jurisdicción Social (LRJS), en solicitud de [FECHA], la cual dirijo contra la empresa [COMPLETAR], con domicilio en [LOCALIDAD], en base a los siguientes

HECHOS

PRIMERO.- El/La demandante es trabajador/a de la empresa demandada prestando sus servicios en la misma desde [COMPLETAR], en el centro de trabajo de [COMPLETAR], ostentando la categoría/grupo profesional de [COMPLETAR] y percibiendo una retribución mensual de [IMPORTE] euros, incluida la parte proporcional de pagas extraordinarias.

SEGUNDO.- Desde el día [FECHA], el/la actor/a desempeña su puesto de trabajo mediante la modalidad de trabajo a distancia, de forma parcial durante tres días a la semana, de conformidad a lo dispuesto en el acuerdo suscrito entre la empresa y la representación legal de los trabajadores como consecuencia de los problemas derivados de la pandemia ocasionada por el COVID-19, habiéndose pactado en el citado acuerdo colectivo que, tras la finalización del estado de alarma, los trabajadores podían reincorporarse a su puesto presencial siempre y cuando comunicaran su decisión con una antelación mínima de 30 días naturales, estableciéndose expresamente en el pacto tercero que si el régimen del teletrabajo fuera inferior al 100% de la jornada, la reversibilidad implicaría la vuelta al centro y puesto de trabajo en el que cada persona desarrollaba su trabajo en modalidad presencial en idénticas condiciones.

En ejecución de este acuerdo colectivo, mi representado/a suscribió con la empresa, en fecha [FECHA], acuerdo individual de trabajo a distancia, a tiempo parcial durante tres días a la semana, en cuya cláusula octava consta lo siguiente: “Octava. Duración del acuerdo: El presente acuerdo tendrá vigencia hasta la finalización del estado de alarma. Una vez finalizado, el trabajador podrá reincorporarse a su puesto presencial en el centro de trabajo de origen y en las mismas condiciones, siempre que lo comunique a la empresa con una antelación mínima de treinta días. Asimismo, la empresa podrá revertir la modalidad con la misma antelación una vez finalizado el estado de alarma. fundada en necesidades organizativas, técnicas o de producción de la empresa”.

A efectos acreditativos, acompaño como documentos número 1 y 2 copia de los citados acuerdos.

TERCERO.- Habiendo finalizado la situación de estado de alarma contemplada en los referidos Acuerdos y dándose los requisitos para el retorno a la modalidad presencial, el/la demandante notificó a la empresa su voluntad de incorporarse a su puesto de trabajo de forma presencial en el centro de trabajo de origen con efectos del día [FECHA] y con propuesta de cumplimiento íntegro de la jornada en esta modalidad presencial, cumpliéndose por tanto los 30 días de preaviso establecidos en el acuerdo de empresa (acompaño como documentos número 2 y 3 copia del burofax remitido y del justificante de notificación del mismo).

CUARTO.- Transcurridos los treinta días, la empresa comunicó que no era posible acceder a la solicitud puesto que el centro de trabajo solo podía ser ocupado parcialmente por razones operativas y de fuerza mayor, y que en este momento estaba cubierto el cupo de puestos de trabajo que podían desarrollarse en el centro, indicando que de existir vacantes en un futuro se comunicaría oportunamente (acompaño como documentos número 4 y 5 contestación de la empresa y justificante de acuse de recibo)

QUINTO.- Ante la negativa de la empresa a la reversión a la modalidad presencial, y al amparo de lo dispuesto en el arts. 5 y 8 de la Ley 10/2021, se presenta esta demanda por lesionarse el derecho del/de la trabajador/a a la reversión al puesto de trabajo, sin que exista causa justificativa, puesto que ni hay la situación de fuerza mayor que indica la empresa, ni ninguna otra causa grave que pueda justificar la negativa empresarial, deduciéndose la impugnación en el plazo de veinte días hábiles previsto legalmente.

SEXTO.- La decisión empresarial ha producido graves perjuicios económicos al/a la demandante, cuya pretensión de resarcimiento se ejercita de forma acumulada en esta demanda, puesto que ha tenido que rescindir el contrato de arrendamiento de vivienda que había concertado para residir en la localidad con motivo de la nueva reincorporación al puesto de trabajo, habiendo satisfecho la cantidad de 3.000 euros, en concepto de comisiones e indemnización por desistimiento, tal como se acredita por los documentos 6 a 8 que se acompañan, solicitando que sea condenada la empresa al pago de dicha cantidad, la cual deberá incrementarse con los intereses legales correspondientes.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I. Competencia. Es competente el Tribunal al que nos dirigimos por ser el lugar de prestación de servicios conforme al art. 10.1 de la LRJS.

II. Legitimación. Están legitimados activa y pasivamente las partes conforme a lo dispuesto en el art. 17 de la LRJS.

III. Procedimiento. Es de aplicación el art. 138 bis de la LRJS, estableciendo el apartado 1.b) que el órgano jurisdiccional podrá recabar informe urgente de la Inspección de Trabajo y Seguridad Social, remitiéndole copia de la demanda y documentos que la acompañen, el cual versará sobre la negativa o la disconformidad comunicada por la empresa respecto de la propuesta realizada por la persona trabajadora y demás circunstancias concurrentes, el cual se solicitará por medio de otrosí.

IV. Tramitación preferente y urgente. En cuanto a la tramitación del procedimiento, el art. 138 bis.1.c) de la LRJS establece que el procedimiento será urgente y se le dará tramitación preferente.

V. Plazo. La presente demanda se formula dentro del plazo de caducidad de veinte días hábiles establecido en el artículo 138 bis, apartado 1.a), LRJS.

VI. Fondo: El art. 5.3 de la Ley 10/2021, de 9 de julio, de trabajo a distancia dispone que la decisión de trabajar a distancia desde una modalidad de trabajo presencial será reversible para la empresa y la persona trabajadora en los términos establecidos en la negociación colectiva o, en su defecto, en los fijados en el acuerdo de trabajo a distancia al que se refiere el artículo 7, en tanto que el art. 8.3 de la citada Ley 10/2021 establece que los convenios o acuerdos colectivos podrán establecer los mecanismos y criterios por los que la persona que desarrolla trabajo presencial puede pasar a trabajo a distancia o viceversa, estando en vigor el acuerdo colectivo de empresa de fecha [FECHA], en el cual se pactó expresamente la reversión de la jornada de los trabajadores que realizaban teletrabajo a tiempo parcial tan pronto finalizara la declaración de estado de alarma y únicamente condicionada al preaviso de treinta días naturales.

VII. Efectos. El art. 138 bis de la LRJS establece que la sentencia se pronunciará sobre la reclamación y que se puede acumular pretensión de resarcimiento de perjuicios.

En virtud de lo expuesto,

SUPLICO AL TRIBUNAL: Que teniendo por presentado este escrito, documentos que se acompañan y copias de todo ello, se sirva admitirlo, y tener por interpuesta demanda contra [ACTO O RESOLUCIÓN], y previos los trámites legales oportunos, dicte sentencia estimando la demanda, reconociendo el derecho del demandante a la reversión de su puesto de trabajo a la modalidad presencial en el centro de trabajo expresado y condenando a la empresa a que indemnice al actor en la cantidad de 3.000 euros por los daños y perjuicios sufridos, con más los intereses legales correspondientes.

PRIMER OTROSÍ DIGO.- Que a los efectos de este procedimiento se designan para la representación y defensa de esta parte, con las facultades más amplias que en derecho hubiere lugar, a [COMPLETAR] del Ilustre Colegio [COLEGIO] de [COLEGIO], D./Dña. [NOMBRE Y APELLIDOS] y Don/Doña [NOMBRE Y APELLIDOS], quien suscribe conmigo esta demanda a todos los efectos prevenidos en el artículo 80.1.e) de la Ley reguladora de la jurisdicción social, designándose el domicilio de dichos profesionales a efectos de notificaciones y citaciones, sito en [LOCALIDAD], así como la dirección de correo electrónico, número de teléfono y de fax que constan en el encabezamiento.

SEGUNDO OTROSÍ DIGO.- Que se acompaña en anexo relación de documentos, debidamente foliados y con índice electrónico, para su debida localización y consulta

TERCER OTROSÍ DIGO.- Que al amparo de lo dispuesto en el artículo 138.1.b) de la LJS intereso que se recabe informe urgente de la Inspección de Trabajo y Seguridad Social sobre la negativa o la disconformidad comunicada por la empresa respecto de la propuesta. remitiéndole copia de la demanda y documentos que se acompañan.

SUPLICO AL TRIBUNAL: Que tenga por hechas las manifestaciones de los anteriores otrosíes, a los efectos oportunos

Es justicia que respetuosamente solicito en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firmas

════════════════════════════════════════════════════════════════════════
