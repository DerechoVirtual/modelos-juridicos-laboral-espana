---
name: ingreso-minimo-vital-denegado-reclamacion-previa-155
description: "Redacta el escrito «Ingreso mínimo vital denegado: reclamación previa» (formulario 155 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ingreso mínimo vital denegado: reclamación previa

> Formulario 0155 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Vida independiente de menores de 30 años: dos años (art. 10.2 Ley 19/2021), no tres; la cuantía es el art. 13.2.a), no el 24; el art. 7 no tiene apartado 2.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS
- [ ] LOCALIDAD (3 veces)
- [ ] DNI/NIE
- [ ] FECHA (3 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, mayor de edad, vecino de»; «…lución dictada por el INSS en expediente»; «…a la prestación por ingreso mínimo vital»; «…oral, donde consta el alta en la empresa»

## Correcciones de la revisión (4)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 10.2 de la Ley 19/2021
- art. 4.1.b) y 7.2 de la Ley 19/2021
- arts. 10 y 11 de la Ley 19/2021
- art. 14 de la Ley 19/2021

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

### Formulario 0155 · Ingreso mínimo vital denegado: reclamación previa

- Año del modelo: 2021
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 2 puntualizaciones normativas añadidas en el texto; 14 campos de relleno marcados en blanco
- Avisos de la revisión: Vida independiente de menores de 30 años: dos años (art. 10.2 Ley 19/2021), no tres; la cuantía es el art. 13.2.a), no el 24; el art. 7 no tiene apartado 2.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Encabezamiento
HECHOS
Solicitud
Firmas
AL INSTITUTO NACIONAL DE SEGURIDAD SOCIAL

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, vecino de [COMPLETAR], con domicilio en [LOCALIDAD] y con DNI [DNI/NIE], ante el INSS comparezco y, como mejor proceda en Derecho, DIGO:

Que me ha sido notificada la resolución dictada por el INSS en expediente [COMPLETAR], por la que se me deniega la prestación por ingreso mínimo vital [COMPLETAR], y no encontrando la misma ajustada a derecho, y lesiva para mis intereses, por medio del presente escrito, y de conformidad con lo establecido en el artículo 71.1 de la Ley reguladora de la jurisdicción social 36/2011, de 10 de octubre, interpongo la presente RECLAMACION PREVIA a la vía jurisdiccional laboral, en base a los siguientes:

HECHOS

PRIMERO.- Tal como consta en el expediente, quien suscribe se encuentra en situación de vulnerabilidad económica en los términos definidos en la Ley 19/2021, de 20 de diciembre, por el que se establece el ingreso mínimo vital, al encontrarse sin domicilio y sin ningún tipo de ingresos, en situación de paro, no siendo beneficiario de pensión contributiva ni de pensión no contributiva por invalidez o jubilación, viviendo solo, sin disponer de recursos económicos de ningún tipo, encontrándose en la actualidad sin domicilio y sin relación familiar de apoyo, y habiendo intentado la búsqueda de empleo sin haber podido conseguirlo.

SEGUNDO.- En fecha [FECHA] solicité ante el INSS el abono de la prestación de ingreso mínimo vital por la cuantía de [IMPORTE] euros y, tras la incoación del oportuno expediente se dictó resolución, con fecha [FECHA], por la que se me deniega la prestación, por ser menor de 30 años en la fecha de la solicitud y al no entender acreditado que hubiera vivido de forma independiente a los progenitores durante los dos años inmediatamente anteriores a la indicada fecha [NOTA DE REVISIÓN: Con la Ley 19/2021 son dos años (los tres años eran del RDL 20/2020). Fuente: art. 10.2 Ley 19/2021; Ley 19/2021 (IMV), BOE-A-2021-21007.].

TERCERO.- Frente a dicha resolución de fecha [FECHA] se presenta esta reclamación puesto que, tal como consta en el expediente, aporté la documentación justificativa de que estoy viviendo de forma independiente a mis padres desde hace más de cinco años, según consta en los siguientes documentos:

1) certificado de empadronamiento histórico, donde consta que desde cinco años antes estoy empadronado en el domicilio sito en [LOCALIDAD], distinto al de mis progenitores,

2) certificado expedido por los servicios sociales del Ayuntamiento de [LOCALIDAD] donde consta la situación de vulnerabilidad, que no tengo domicilio fijo, que carezco de soporte familiar y que mis necesidades básicas están siendo cubiertas por los citados servicios sociales;

3) informe de vida laboral, donde consta el alta en la empresa [COMPLETAR], en la cual estuve trabajando durante dos años, habiendo finalizado las prestaciones por desempleo y encontrándome sin ningún tipo de ingreso desde hace más de dos años;

4) certificado de inscripción como demandante de empleo en el Servicio de Empleo; y 5) declaración responsable de que carezco de ingresos y rentas.

Por tanto, se cumple lo dispuesto en el art. 10.2 de la Ley 19/2021 [NOTA DE REVISIÓN: El requisito de vida independiente de los menores de 30 años (dos años) está en el art. 10.2 de la Ley 19/2021; en el RDL 20/2020 estaba en el art. 7.2 y era de tres años. Fuente: art. 10.2 Ley 19/2021; art. 7.2 RDL 20/2020 (BOE-A-2020-5493); Ley 19/2021 (IMV), BOE-A-2021-21007.], el cual resulta infringido, cuando establece que se entenderá que una persona ha vivido de forma independiente siempre que acredite que su domicilio ha sido distinto al de sus progenitores, tutores o acogedores durante los dos años inmediatamente anteriores a la solicitud, y en dicho periodo hubiere permanecido durante al menos doce meses, continuados o no, en situación de alta en cualquiera de los regímenes que integran el sistema de la Seguridad Social, incluido el de Clases Pasivas del Estado, o en una mutualidad de previsión social alternativa al Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos, cumpliéndose todos y cada uno los requisitos para que surja la presunción legal de vida independiente, a los cuales no se hace ninguna referencia en la resolución denegatoria.

La resolución denegatoria se limita a afirmar genéricamente que no se dan los requisitos de acceso del art. 4.1.b) y 7.2 de la Ley 19/2021 [NOTA DE REVISIÓN: El art. 7 de la Ley 19/2021 («Situaciones especiales») no tiene apartado 2; el requisito discutido es el art. 10.2. Fuente: arts. 7 y 10.2 Ley 19/2021; Ley 19/2021 (IMV), BOE-A-2021-21007.], al integrarse el reclamante en una unidad de convivencia con recursos suficientes, de forma absolutamente inmotivada, prescindiendo de la valoración de los elementos probatorios aportados con la solicitud que han quedado expuestos.

CUARTO.- La documentación aportada pone de manifiesto la concurrencia de los requisitos establecidos en los arts. 10 y 11 de la Ley 19/2021 para el derecho a la prestación de ingreso mínimo vital, en la cuantía establecida en los arts. 12 y siguientes de la citada Ley 19/2021.

El solicitante reúne los requisitos para ser beneficiario individual del ingreso mínimo vital, al vivir solo, en la actualidad sin domicilio fijo y careciendo de todo tipo de ingresos, y encontrándose en una situación extrema de vulnerabilidad económica, solicitándose la prestación por la cuantía de la renta garantizada para un hogar unipersonal, que es el equivalente al 100 por ciento del importe anual de las pensiones no contributivas de la Seguridad Social vigente en cada momento, dividido por 12, al no tener ningún ingreso desde hace dos años, tal como se acredita con la solicitud y documentación justificativa aportada, conforme a lo dispuesto en los arts. 24 y siguientes de la Ley 19/2021 [NOTA DE REVISIÓN: La renta garantizada (100 % de la PNC anual / 12) es el art. 13.2.a); el art. 24 son normas de procedimiento. Fuente: arts. 13 y 24 Ley 19/2021 (art. 13 red. Ley 1/2026, BOE-A-2026-7967); Ley 19/2021 (IMV), BOE-A-2021-21007.].

QUINTO.- En consecuencia, la resolución que se recurre no es ajustada a derecho, en tanto mi situación es constitutiva de una situación legal de cese de actividad, solicitando por medio de la presente reclamación que se deje sin efecto y se reconozca mi derecho a la percepción de la prestación por ingreso mínimo vital desde el primer día del mes siguiente a la fecha de presentación de la solicitud, conforme a lo establecido en el art. 14 de la Ley 19/2021.

En su virtud,

AL INSS SOLICITA, que admita este escrito, y tenga por interpuesta, en tiempo y forma, la RECLAMACION PREVIA a la vía jurisdiccional en el orden social, contra la resolución indicada, y, a la vista de los hechos y fundamentos antes expuestos, dicte una nueva por la que, dejando sin efecto lo anterior, se reconozca mi derecho a la percepción de la prestación por ingreso mínimo vital en los términos que quedan expuestos.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma del interesado

════════════════════════════════════════════════════════════════════════
