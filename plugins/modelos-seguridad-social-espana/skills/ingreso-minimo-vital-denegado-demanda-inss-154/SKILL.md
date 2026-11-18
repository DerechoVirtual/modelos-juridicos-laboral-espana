---
name: ingreso-minimo-vital-denegado-demanda-inss-154
description: "Redacta el escrito «Ingreso mínimo vital denegado: demanda al INSS» (formulario 154 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Ingreso mínimo vital denegado: demanda al INSS

> Formulario 0154 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Citas literales de la Ley 19/2021 desfasadas: el art. 10 vigente (red. Ley 1/2026, desde 10-4-2026) remite al art. 11 y exige «acreditar haber vivido de forma independiente en España» dos años.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] LOCALIDAD (5 veces)
- [ ] FECHA (5 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…oral, donde consta el alta en la empresa»; «…a presente demanda asistiré dirigido por»; «…restación de renta mínima garantizada. -»

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 10.2 de la Ley 19/2021
- artículos 2.o), 6 y 10 de la Ley 36/2011
- art. 80 de la LRJS
- arts. 71 y 140 de la LRJS
- art. 10 y 11 de la Ley 19/2021
- art. 13 de la Ley 19/2021

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

### Formulario 0154 · Ingreso mínimo vital denegado: demanda al INSS

- Año del modelo: 2021
- Revisión 17-11-2026: 3 citas normativas corregidas tras comprobarlas en el BOE; 17 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: Citas literales de la Ley 19/2021 desfasadas: el art. 10 vigente (red. Ley 1/2026, desde 10-4-2026) remite al art. 11 y exige «acreditar haber vivido de forma independiente en España» dos años.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Parte
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
PRIMER OTROSÍ
SEGÚNDO OTROSÍ
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de D.N.I., con domicilio en [LOCALIDAD], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, DIGO:

Que, por medio del presente escrito, interpongo en tiempo y forma legal, DEMANDA EN RECLAMACIÓN DE RECONOCIMIENTO DE PRESTACIONES DE INGRESO MÍNIMO VITAL, contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, con domicilio en [LOCALIDAD], que deberá tramitarse por la modalidad procesal de prestaciones de Seguridad Social, a fin de que sean condenadas en los términos que en el suplico de esta demanda se dirán y todo ello sobre la base de los siguientes:

HECHOS

PRIMERO.- El demandante, nacido el día [FECHA], se encuentra en situación de vulnerabilidad económica en los términos definidos la Ley 19/2021, de 20 de diciembre por el que se establece el ingreso mínimo vital, al encontrarse sin domicilio y sin ningún tipo de ingresos desde hace más de dos años, en situación de paro, no siendo beneficiario de pensión contributiva ni de pensión no contributiva por invalidez o jubilación, viviendo solo, sin disponer de recursos económicos de ningún tipo, encontrándose en la actualidad sin domicilio y sin relación familiar de apoyo, habiendo intentando la búsqueda de empleo sin haber podido conseguirlo.

SEGUNDO.- Con fecha [FECHA], el demandante solicitó el reconocimiento de prestaciones por ingreso mínimo vital mediante la cumplimentación del formulario de solicitud y adjuntado la documentación justificativa de su solicitud.

TERCERO.- Por resolución de [FECHA], el INSS denegó la prestación con fundamento en que el demandante era menor de 30 años en la fecha de la solicitud y al no entenderse acreditado que hubiera vivido de forma independiente a los progenitores durante los dos años inmediatamente anteriores a la indicada fecha.

CUARTO.- Disconforme con dicha resolución, el demandante interpuso reclamación previa alegando que había acreditado que estaba viviendo de forma independiente a sus progenitores desde más de cinco años atrás, según constaba en los siguientes documentos que habían sido adjuntados a su solicitud:

1) certificado de empadronamiento histórico, donde consta que el empadronamiento desde hace más de cinco años en el domicilio sito en [LOCALIDAD], distinto al de sus progenitores,

2) certificado expedido por los servicios sociales del Ayuntamiento de [LOCALIDAD] donde consta la situación de vulnerabilidad, que desde hace unos meses el demandante carece de domicilio fijo y de soporte familiar, así como que sus necesidades básicas están siendo cubiertas por los citados servicios sociales;

3) informe de vida laboral, donde consta el alta en la empresa [COMPLETAR] durante dos años, habiendo finalizado las prestaciones por desempleo desde hace más de dos años;

4) certificado de inscripción como demandante de empleo en el Servicio de Empleo; y 5) declaración responsable de que carezco de ingresos y rentas.

Se alegaba el cumplimiento de lo dispuesto en el art. 10.2 de la Ley 19/2021, el cual resulta infringido, cuando establece que se entenderá que una persona ha vivido de forma independiente siempre que acredite que su domicilio ha sido distinto al de sus progenitores, tutores o acogedores durante los dos años inmediatamente anteriores a la solicitud, y en dicho periodo hubiere permanecido durante al menos doce meses, continuados o no, en situación de alta en cualquiera de los regímenes que integran el sistema de la Seguridad Social, cumpliéndose todos y cada uno los requisitos para que surja la presunción legal de vida independiente, a los cuales no se hace ninguna referencia en la resolución denegatoria.

QUINTO.- Que planteada la preceptiva reclamación previa ante el INSS fue desestimada por resolución expresa de fecha [FECHA], notificada en fecha [FECHA], la cual se acompaña como documento número 1.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- Es competente el Tribunal, tanto por razón de la condición de los litigantes, como por la materia y territorio, de conformidad a lo que determinan los artículos 2.o), 6 y 10 de la Ley 36/2011 [NOTA DE REVISIÓN: El art. 1 LRJS no tiene apartados; las prestaciones de Seguridad Social son la letra o) del art. 2 (la «b)» venía de la LPL de 1995). Fuente: arts. 1, 2.o) y 10.2.a) LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], Reguladora de la Jurisdicción Social (LRJS).

SEGUNDO.- Se han hecho constar en la presente demanda todos los requisitos formales exigidos por el art. 80 de la LRJS, debiendo tramitarse el procedimiento por la modalidad procesal de prestaciones de Seguridad Social.

TERCERO.- Los arts. 71 y 140 de la LRJS, en cuanto acreditación del cumplimiento del trámite de la reclamación previa ante la entidad gestora demandada.

CUARTO.- En cuanto al fondo del asunto, son de aplicación el art. 10 y 11 de la Ley 19/2021. En concreto el art. 10.1 de la Ley establece: “Todas las personas beneficiarias, estén o no integradas en una unidad de convivencia, deberán cumplir los siguientes requisitos: a) Tener residencia legal y efectiva en España y haberla tenido de forma continuada e ininterrumpida durante al menos el año inmediatamente anterior a la fecha de presentación de la solicitud. (…) b) Encontrarse en situación de vulnerabilidad económica por carecer de rentas, ingresos o patrimonio suficientes, en los términos establecidos en el artículo 11. [NOTA DE REVISIÓN: Cita literal desfasada: el art. 10.1.b) vigente remite al art. 11 (está dentro de comillas). Fuente: art. 10.1.b) Ley 19/2021 (red. Ley 1/2026, vigente 10-4-2026); Ley 19/2021 (IMV), BOE-A-2021-21007.] Por su parte, el art. 10.2 de la citada Ley 19/2021 establece: “Las personas beneficiarias a las que se refiere el artículo 4.1.b), que sean menores de 30 años en la fecha de la solicitud, deberán acreditar haber vivido de forma independiente en España, durante al menos los dos años [NOTA DE REVISIÓN: Cita literal ajustada al art. 10.2 vigente (está dentro de comillas). Fuente: art. 10.2 Ley 19/2021; Ley 19/2021 (IMV), BOE-A-2021-21007.] inmediatamente anteriores a la indicada fecha.

Este requisito no se exigirá a las personas de entre 18 y 22 años que provengan de centros residenciales de protección de menores de las diferentes Comunidades Autónomas.

A los efectos del párrafo anterior, se entenderá que una persona ha vivido de forma independiente siempre que acredite que su domicilio ha sido distinto al de sus progenitores, tutores o acogedores durante los dos años inmediatamente anteriores a la solicitud, y en dicho periodo hubiere permanecido durante al menos doce meses, continuados o no, en situación de alta en cualquiera de los regímenes que integran el sistema de la Seguridad Social, incluido el de Clases Pasivas del Estado, o en una mutualidad de previsión social alternativa al Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos”.

QUINTO.- En cuanto a la pretensión y efectos, son de aplicación los arts. 12 y siguientes de la Ley 19/2021, solicitándose una prestación mensual por el importe de la renta garantizada conforme al art. 13 de la Ley 19/2021, al carecer el demandante de ingresos, cuyo reconocimiento se solicita a partir del primer día del mes siguiente al de la fecha de presentación de la solicitud, según lo dispuesto en el art. 14.1 de la citada Ley 19/2021.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentada esta demanda de reconocimiento de prestaciones de ingreso mínimo vital, contra el INSS, con sus respectivas copias y documentos que se adjuntan, se sirva admitirla, darle el turno que corresponda, citar a las partes para la celebración del acto del juicio y, en definitiva, dictar sentencia por la que estimando la presente demanda se reconozca el derecho del demandante a la percepción de la prestación por ingreso mínimo por el importe mensual de la cuantía de la renta garantizada desde el primer día del mes siguiente al de la fecha de presentación de la solicitud.

PRIMER OTROSÍ DIGO: Que de conformidad a lo establecido en el art. 21.2 de la Ley reguladora de la jurisdicción social, hago constar que a los actos que se deriven de la presente demanda asistiré dirigido por [COMPLETAR] en ejercicio, designando a D./Dña. [NOMBRE Y APELLIDOS], con domicilio en [LOCALIDAD], el cual se señala a efectos de notificaciones.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos procedentes

SEGUNDO OTROSI DIGO que, sin perjuicio de las pruebas que en su día se propongan en el acto del juicio, interesa al derecho de esta parte la verificación de los siguientes medios de prueba:

- DOCUMENTAL consistente en que por el INSS se acompañe el correspondiente expediente tramitado referente a la solicitud de prestación de renta mínima garantizada.

- [COMPLETAR]

SUPLICO tenga por propuesto el medio de prueba solicitado y acuerde lo conducente para su práctica.

Por ser Justicia que pido para principal y otrosí, en [LUGAR], a [DÍA] de [MES] de [AÑO].

(firma)

════════════════════════════════════════════════════════════════════════
