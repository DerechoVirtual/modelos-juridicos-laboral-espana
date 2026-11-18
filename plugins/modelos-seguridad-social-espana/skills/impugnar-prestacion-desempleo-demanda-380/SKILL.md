---
name: impugnar-prestacion-desempleo-demanda-380
description: "Redacta el escrito «Impugnar la prestación por desempleo: demanda» (formulario 380 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impugnar la prestación por desempleo: demanda

> Formulario 0380 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Duración de la prestación: art. 269 LGSS (seis años, desde 360 días); el art. 3 del RD 625/1985 conserva una escala superada. Subsidio reformado por el RDL 2/2024 (cuantía 95/90/80 % del IPREM desde 1-11-2024, art. 278).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] FECHA (4 veces)
- [ ] IMPORTE (5 veces)
- [ ] NÚMERO (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] Nº (2 veces)
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, y contra la empresa»; «…, con la categoría profesional de»; «…e la empresa demandada a la actividad de»; «…, de»; «…io Público de Empleo y contra la empresa»; «…en»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si no está de acuerdo con la cantidad / Si no está de acuerdo con el tiempo de la prestación — el texto de cada opción no venía en el formulario original

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 71 LRJS
- Ley 36/2011
- Real Decreto Legislativo 8/2015
- Real Decreto 625/1985

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

### Formulario 0380 · Impugnar la prestación por desempleo: demanda

- Año del modelo: 2008
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 30 campos de relleno marcados en blanco
- Avisos de la revisión: Duración de la prestación: art. 269 LGSS (seis años, desde 360 días); el art. 3 del RD 625/1985 conserva una escala superada. Subsidio reformado por el RDL 2/2024 (cuantía 95/90/80 % del IPREM desde 1-11-2024, art. 278).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Se trata de la modalidad procesal de prestaciones de Seguridad Social (arts. 140 y ss LRJS).

Formulada reclamación previa, que es requisito necesario para formular demanda en materia de prestaciones de la Seguridad (con la excepción de la impugnación de altas médicas transcurridos 365 días), la Entidad deberá contestar expresamente a la misma en el plazo de cuarenta y cinco días. En caso contrario se entenderá denegada la reclamación por silencio administrativo.

La demanda habrá de formularse en el plazo de treinta días, a contar desde la fecha en que se notifique la denegación de la reclamación previa o desde el día en que se entienda denegada por silencio administrativo (art. 71 LRJS).

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI n.º [DNI/NIE], y con domicilio en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante el TRIBUNAL DE INSTANCIA comparece y, como mejor proceda en Derecho DICE:

Que mediante el presente escrito, interpone demanda de IMPUGNACIÓN DE LA PRESTACIÓN DE DESEMPLEO, en tiempo y forma legalmente establecido, contra el Servicio Público de Empleo Estatal, con domicilio en [LOCALIDAD], y contra la empresa [COMPLETAR] con domicilio social en [LOCALIDAD], todos ellos en la persona de sus representantes legales, en base a los siguientes hechos y Fundamentos de Derecho:

HECHOS

PRIMERO.- Que el/la demandante ha venido prestando servicios en la aludida empresa desde el día [FECHA], con la categoría profesional de [COMPLETAR] y un salario mensual de [IMPORTE] euros, incluida la prorrata de pagas extras, dedicándose la empresa demandada a la actividad de [COMPLETAR].

SEGUNDO.- Que el/la demandante fue despedido/a de dicha empresa, declarándose improcedente el despido por sentencia de fecha [FECHA] dictada por la Sección de lo Social del Tribunal de Instancia nº [NÚMERO], de [COMPLETAR], en el procedimiento nº [Nº DE PROCEDIMIENTO], y tras haberse llevado a efecto todos los trámites oportunos incluida la ejecución de sentencia, solicitó del Servicio Público de Empleo, en tiempo y forma, las prestaciones correspondientes.

TERCERO.- Que durante los últimos cinco años ha cotizado de forma ininterrumpida, incluida la contingencia por desempleo, en la empresa codemandada.

CUARTO.- Que la base reguladora de los 6 meses anteriores a la situación de desempleo asciende a la cantidad de [IMPORTE] euros, y proporcionalmente corresponde una cantidad diaria de [IMPORTE] euros.

QUINTO.- Que mediante resolución del Servicio Público de Empleo de fecha [FECHA], se me reconoce la prestación económica correspondiente a una base reguladora de [IMPORTE] euros diarios y por un período de [Nº] meses. Se acompaña copia de dicha Resolución como DOC. Nº [NÚMERO].

SEXTO.- Que no estoy conforme con dicha resolución por cuanto:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si no está de acuerdo con la cantidad / Si no está de acuerdo con el tiempo de la prestación — el texto de cada opción no venía en el formulario original]

SÉPTIMO.- Que ha agotado la reclamación previa ante el Servicio Público de Empleo, según se acredita en el documento que se adjunta como DOC. Nº [NÚMERO].

FUNDAMENTOS DE DERECHO

I.-Artículos 1, 2.o), 6, 10, 71 a 73 y 140 a 147 de la Ley 36/2011 [NOTA DE REVISIÓN: Erratas. Fuente: arts. 2.o), 71 y 140-147 LRJS; LRJS (Ley 36/2011), BOE-A-2011-15936.], reguladora de la jurisdicción social, siendo competente el Tribunal de Instancia al que me dirijo en razón de la materia y territorio.

II.-Artículo 269 del Real Decreto Legislativo 8/2015, de 30 de octubre, Texto refundido de la Ley General de la Seguridad Social.

III.-Artículo 3 o 4 del Real Decreto 625/1985 [NOTA DE REVISIÓN: El RD 625/1985 sigue vigente, pero la escala de su art. 3 (cuatro años, 180 días) está superada por el art. 269 LGSS (seis años, desde 360 días). La cuantía del subsidio cambió con el RDL 2/2024 (art. 278 LGSS, desde 1-11-2024). Fuente: art. 269 LGSS (red. RDL 2/2024, BOE-A-2024-10235); art. 3 RD 625/1985 (BOE-A-1985-8124).], de 2 de abril, que desarrolla la Ley de protección por desempleo.

En virtud de cuanto antecede es por lo que,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito con sus copias y documentos que se adjuntan, se digne admitirlo, tenga por formulada demanda de impugnación de la prestación de desempleo contra el Servicio Público de Empleo y contra la empresa [COMPLETAR], se proceda a convocar a las partes para los actos de conciliación y juicio, en la debida forma, por el que, seguido todos sus trámites, se dicte en su día sentencia estimando íntegramente la presente demanda, por la que se condene a los demandados en su respectivo carácter, a reconocer mi derecho al percibo de prestación por desempleo en la cantidad diaria de [IMPORTE] euros, y por un periodo de [Nº] meses.

OTROSI DIGO: Que al acto de juicio compareceré asistido de Letrado/a para que me defienda, en conformidad con el artículo 21.2 de la Ley reguladora de la jurisdicción social, designando el domicilio profesional del/de la Letrado/a D./Dña. [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

SUPLICO AL TRIBUNAL: Tenga por hecha tal manifestación a los efectos oportunos

SEGUNDO OTROSI DIGO: Que interesa al derecho de esta parte, y sin perjuicio de ampliación en el momento procesal oportuno, los siguientes MEDIOS DE PRUEBA:

- INTERROGATORIO del representante legal de la empresa demandada, que deberá ser citado en el domicilio indicado.
- DOCUMENTAL, consistente en que se requiera a la empresa demandada para que aporte a juicio los siguientes documentos:
1) Parte de alta y baja en la Seguridad Social.
2) Nóminas acreditativas de los salarios percibidos.
3) Boletines de cotización a la Seguridad Social.
- DOCUMENTAL, consistente en que se requiera al Servicio Público de Empleo para que aporte el expediente administrativo correspondiente.

SUPLICO AL TRIBUNAL DE INSTANCIA tenga por hecha tal manifestación a los efectos oportunos, admita y declare pertinentes las pruebas que se dejan propuestas, y acuerde cuanto sea preciso para llevarlas a efecto.

Es de Justicia que pide en [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
