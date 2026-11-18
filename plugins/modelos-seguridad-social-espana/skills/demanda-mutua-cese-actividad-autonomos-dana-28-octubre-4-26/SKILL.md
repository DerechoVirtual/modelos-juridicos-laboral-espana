---
name: demanda-mutua-cese-actividad-autonomos-dana-28-octubre-4-26
description: "Redacta el escrito «Demanda a la Mutua por cese de actividad de autónomos por la DANA (28 octubre a 4 noviembre de 2024)» (formulario 26 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda a la Mutua por cese de actividad de autónomos por la DANA (28 octubre a 4 noviembre de 2024)

> Formulario 0026 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Art. 24.4 RDL 6/2024: la prestación extraordinaria podía extenderse hasta el 31-1-2025; después, la ordinaria del art. 331.1.b).
- Cese de actividad: la reclamación previa ante el órgano gestor es potestativa (art. 350.1 LGSS); si resolvió una mutua, informa una comisión paritaria (art. 350.2).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (2 veces)
- [ ] TELÉFONO
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] FECHA (8 veces)
- [ ] IMPORTE (3 veces)
- [ ] Nº DE EXPEDIENTE
- [ ] LUGAR
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, asistido/a por el/la Letrado/a»; «…zco y como mejor proceda en Derecho DIGO»; «…Que he estado realizando la actividad de»; «…desde»; «…desde [COMPLETAR] hasta»; «…como consecuencia de la DANA acaecida en»; «…los días»; «…solicité a la Mutua»; «…, notificada el»; «… Niveles Altos (DANA) en el municipio de»; «…de»; «…e de mi actividad por fuerza mayor desde»; …

## Elecciones que hay que hacer

- parcialmente / totalmente
- temporal / definitiva
- Resolución / Acuerdo

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- que no he acreditado la imposibilidad para desarrollar la actividad…
- que no he acreditado el período mínimo de cotización establecido en el art. 338 de la LGSS…
- no es necesaria la aportación de documentos que acrediten la existencia de fuerza mayor…
- en estos casos se considerará cumplido el requisito de período mínimo de cotización de doce meses comprendidos…

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 2.o) de la LJS
- arts. 327 a 350 de la LGSS
- art. 331.1.b) de la LGSS
- art. 338 de la LGSS
- artículos 1, 2, 6 y 10 de la Ley 36/2011
- Ley 6/2024
- Real Decreto-ley 6/2024

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

### Formulario 0026 · Demanda a la Mutua por cese de actividad de autónomos por la DANA (28 octubre a 4 noviembre de 2024)

- Año del modelo: 2024
- Revisión 17-11-2026: 3 citas normativas corregidas tras comprobarlas en el BOE; 4 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 4 párrafos opcionales señalados; 37 campos de relleno marcados en blanco
- Avisos de la revisión: Art. 24.4 RDL 6/2024: la prestación extraordinaria podía extenderse hasta el 31-1-2025; después, la ordinaria del art. 331.1.b). · Cese de actividad: la reclamación previa ante el órgano gestor es potestativa (art. 350.1 LGSS); si resolvió una mutua, informa una comisión paritaria (art. 350.2).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
MEDIOS DE PRUEBA
Firmas

Los órganos jurisdiccionales del orden social conocerán de las cuestiones litigiosas que se promuevan en materia de prestaciones de Seguridad Social, incluidas la protección por desempleo y la protección por cese de actividad de las personas trabajadoras por cuenta propia o autónomos (art. 2.o) de la LJS).

La protección por cese de actividad se rige por lo dispuesto en los arts. 327 a 350 de la LGSS [NOTA DE REVISIÓN: El título V (protección por cese de actividad) abarca los arts. 327 a 350; el 350 regula jurisdicción y reclamación previa y el 351 ya es otro título. Fuente: arts. 327, 350 y 351 LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.], y en sus normas de desarrollo, así como, supletoriamente, por las normas que regulan el régimen especial de la Seguridad Social de encuadramiento.

Las personas trabajadoras por cuenta propia o autónomos podrán solicitar la prestación por cese de actividad por fuerza mayor ante su mutua sin necesidad de contar con la cotización mínima exigida para poder acceder a ella y sin necesidad de acreditar, en el momento de la solicitud, la imposibilidad para desarrollar la actividad. Todo como consecuencia directa e inmediata de los siniestros descritos en el artículo 1 del RD-Ley 6/2024, producidos en alguna de las localidades del anexo del RD-Ley 6/2024.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE], asistido/a por el/la Letrado/a [COMPLETAR], y con domicilio a efectos de notificaciones en su despacho sito en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico, ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO [COMPLETAR]:

Que por medio del presente escrito formulo DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS contra [ACTO O RESOLUCIÓN] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], en la persona de su legal representante, con domicilio en [LOCALIDAD].

Se apoya la presente demanda en los siguientes

HECHOS

PRIMERO.- Que soy trabajador/a autónomo/a, afiliado/a, en alta, y al corriente de pago en el Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos desde el pasado [FECHA], con una base de cotización mensual de [IMPORTE] euros y una base reguladora de [IMPORTE] euros.

SEGUNDO.- Que he estado realizando la actividad de [COMPLETAR] desde [COMPLETAR] hasta [COMPLETAR], fecha en la que como consecuencia de la DANA acaecida en [COMPLETAR] los días [COMPLETAR], he tenido que cesar [ELEGIR: parcialmente / totalmente] de forma [ELEGIR: temporal / definitiva] en mi actividad profesional ya que

TERCERO.- Que con fecha [FECHA] solicité a la Mutua [COMPLETAR] la prestación por cese de actividad derivada de fuerza mayor prevista en el art. 331.1.b) de la LGSS, que me ha sido denegada por [ELEGIR: Resolución / Acuerdo] de la citada Mutua con fecha [FECHA], expediente nº [Nº DE EXPEDIENTE], en base a

[OPCIONAL — incluir si procede]

que no he acreditado la imposibilidad para desarrollar la actividad

[OPCIONAL — incluir si procede]

que no he acreditado el período mínimo de cotización establecido en el art. 338 de la LGSS

Se acompañan como DOCS. Nº 1 y 2, copia de la solicitud de prestación y carta de denegación de la Mutua.

CUARTO.- Contra dicha comunicación de denegación interpuse reclamación previa a la vía judicial ante el órgano gestor, que fue desestimada por Resolución de fecha [FECHA], notificada el [COMPLETAR], que confirma el Acuerdo de [FECHA].

Se adjunta copia de la reclamación previa como DOC. Nº 3 y Resolución de la Mutua como DOC. Nº 4

QUINTO.- Que la resolución de la Mutua no es ajustada a Derecho toda vez que, en virtud de lo establecido en el art. 24
1
3
 del Real Decreto-ley 6/2024, de 5 de noviembre, por el que se adoptan medidas urgentes de respuesta ante los daños causados por la Depresión Aislada en Niveles Altos (DANA) en diferentes municipios entre el 28 de octubre y el 4 de noviembre de 2024, los trabajadores autónomos que cesen total o parcialmente, de forma definitiva o temporal, en su actividad como consecuencia directa e inmediata de los daños causados por la Depresión Aislada en Niveles Altos (DANA) en el municipio de [COMPLETAR] entre el 28 de octubre y el 4 de noviembre de 2024

[OPCIONAL — incluir si procede]

no es necesaria la aportación de documentos que acrediten la existencia de fuerza mayor

[OPCIONAL — incluir si procede]

en estos casos se considerará cumplido el requisito de período mínimo de cotización de doce meses comprendidos en los veinticuatro meses inmediatamente anteriores a la situación de cese de actividad [NOTA DE REVISIÓN: Redacción vigente del período mínimo (art. 338.1 LGSS desde 1-1-2023) y de las normas excepcionales (art. 24.3 RDL 6/2024, art. 6.3 RDL 20/2026, art. 39.3 RDL 22/2026). Fuente: art. 338.1 LGSS (red. RDL 13/2022); RDL 6/2024, BOE-A-2024-22928; RDL 20/2026, BOE-A-2026-16543; RDL 22/2026, BOE-A-2026-18429.]

SEXTO.- Por todo lo expuesto, teniendo el demandante derecho a la prestación que reclama, ha de estimarse la demanda y revocar la [ELEGIR: Resolución / Acuerdo] de [COMPLETAR] de fecha [FECHA] por infringir los arts. 329 y siguientes de la Ley General de la Seguridad Social.

FUNDAMENTOS DE DERECHO

I.- Es competente el Tribunal al que me dirijo en virtud de lo dispuesto en los artículos 1, 2, 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social.

II.- Se cumplen todos los requisitos formales para la presentación de la presente demanda en virtud de lo dispuesto en el artículo 80 de la Ley reguladora de la jurisdicción social, así como en los artículos 71 y 140 a 146 del mismo texto legal que regulan la reclamación administrativa previa. [NOTA DE REVISIÓN: La reclamación previa es administrativa, no «judicial». En cese de actividad es potestativa (art. 350.1 LGSS) y, si se dirige a una mutua, informa una comisión paritaria (art. 350.2 LGSS). Fuente: art. 71 LRJS; art. 350 LGSS (red. RDL 28/2018); LRJS (Ley 36/2011), BOE-A-2011-15936; LGSS (RDLeg 8/2015), BOE-A-2015-11724.]

III.- En cuanto al fondo del asunto son aplicables los arts. 331.1.b), 332.1 y concordantes de la Ley General de la Seguridad Social, y el art. 24
1
3
 del Real Decreto-ley 6/2024, de 5 de noviembre, por el que se adoptan medidas urgentes de respuesta ante los daños causados por la Depresión Aislada en Niveles Altos (DANA) en diferentes municipios entre el 28 de octubre y el 4 de noviembre de 2024.

Por lo expuesto,

SUPLICO AL TRIBUNAL que teniendo por presentado este escrito, con sus copias, se sirva admitirlo y, en su virtud, tenga por interpuesta DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS contra [ACTO O RESOLUCIÓN] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], en la persona de su legal representante, citando a las partes para los trámites previos de conciliación y, en su caso, de juicio, concluyendo las actuaciones con una Sentencia en la que se revoque la [ELEGIR: Resolución / Acuerdo] de dicho órgano gestor de fecha [FECHA] y se acuerde mi derecho a percibir la prestación por cese de mi actividad por fuerza mayor desde [COMPLETAR] hasta [COMPLETAR] conforme a una base reguladora de [IMPORTE] euros.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO que se solicita la reclamación de oficio a la Mutua [COMPLETAR] del expediente y antecedentes que posea en relación con el contenido de la demanda.

SEGUNDO OTROSI DIGO que esta parte acudirá al acto del juicio oral acompañada y asistida de Letrado.

TERCER OTROSI DIGO que interesa al Derecho de esta parte que se practiquen en el acto del juicio oral los siguientes:

MEDIOS DE PRUEBA

- DOCUMENTAL: la que esta parte aportará en el acto del juicio, así como la documental aportada con esta demanda y el expediente administrativo.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones y por propuesta la prueba, la admita y la estime pertinente.

Por ser de Justicia que reitero en el lugar y fecha "ut supra"

Fdo. D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
