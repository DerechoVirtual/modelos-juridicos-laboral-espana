---
name: demanda-inss-contra-devolver-prestacion-cese-autonomos-16
description: "Redacta el escrito «Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19» (formulario 16 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19

> Formulario 0016 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- Contra el INSS la reclamación previa sí es requisito (art. 71 LRJS): se llama «reclamación administrativa previa», no «judicial».

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] Nº DE COLEGIADO/A
- [ ] COLEGIO
- [ ] LOCALIDAD (2 veces)
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] NÚMERO (2 veces)
- [ ] FECHA (9 veces)
- [ ] IMPORTE (2 veces)
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, asistido/a por el/la Letrado/a»; «…SORERÍA GENERAL DE LA SEGURIDAD SOCIAL y»; «…ores por Cuenta Propia o Autónomos desde»; «…. hasta»; «…euros y una base reguladora de»; «…, y de alta en el epígrafe»; «…solicité a la Mutua»; «…uisitos para su percepción, alegando que»; «…, notificada el»; «…INSS no es ajustada a Derecho por cuanto»; «…TE EL COVID-19 contra el INSS; la TGSS y»; «…cita la reclamación de oficio a la Mutua»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 1, 2, 6 y 10 de la Ley 36/2011
- Ley 8/2020

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

### Formulario 0016 · Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19

- Año del modelo: 2025
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 35 campos de relleno marcados en blanco
- Avisos de la revisión: Contra el INSS la reclamación previa sí es requisito (art. 71 LRJS): se llama «reclamación administrativa previa», no «judicial».

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
MEDIOS DE PRUEBA
Firmas

Este formulario de demanda está diseñado para que los trabajadores autónomos presenten una impugnación contra el Instituto Nacional de la Seguridad Social (INSS) en relación con la devolución de ingresos percibidos como prestación de cese de actividad durante la pandemia de COVID-19. La situación surge principalmente a raíz de discrepancias sobre los cálculos y criterios utilizados por el INSS para solicitar la devolución de prestaciones ya abonadas.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE], asistido/a por el/la Letrado/a [COMPLETAR], colegiado/a nº [Nº DE COLEGIADO/A] del Ilustre Colegio de Abogados de [COLEGIO] y con domicilio a efectos de notificaciones en su despacho sito en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo DEMANDA DE IMPUGNACIÓN DE DEVOLUCIÓN DE INGRESOS DE LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS DURANTE EL COVID-19 contra el INSTITUTO NACIONAL DE LA SEGURIDAD SOCIAL, la TESORERÍA GENERAL DE LA SEGURIDAD SOCIAL y [COMPLETAR] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], con domicilio en [LOCALIDAD], en la persona de sus legales representantes.

Se apoya la presente demanda en los siguientes

HECHOS

PRIMERO.- Que soy trabajador/a autónomo/a,

afiliado/a, en alta, y al corriente de pago en el Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos (RETA) desde el pasado [FECHA],

estando dado de alta en el Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos desde [COMPLETAR]. hasta [COMPLETAR] con una base de cotización mensual de [IMPORTE] euros y una base reguladora de [COMPLETAR], y de alta en el epígrafe [COMPLETAR].

SEGUNDO.- Que con fecha [FECHA] solicité a la Mutua [COMPLETAR] la prestación extraordinaria por cese de actividad como consecuencia de la declaración del estado de alarma por la COVID-19.

TERCERO.- Mediante Resolución de fecha [FECHA], y conforme al art. 17 del Real Decreto Ley 8/2020, de 17 de marzo, de medidas urgentes extraordinarias para hacer frente al impacto económico y social del COVID-19.

Se acompañan como DOCS. Nº 1 y 2, copia de la solicitud de prestación y resolución de la Mutua.

CUARTO.- Con fecha [FECHA], el INSS me ha notificado Resolución de fecha [FECHA] por la que me reclama la devolución de la prestación reconocida, por importe de [IMPORTE] euros, al considerar supuestamente incumplidos los requisitos para su percepción, alegando que [COMPLETAR].

QUINTO.- Contra dicha comunicación de denegación interpuse reclamación previa a la vía judicial ante el órgano gestor, que fue desestimada por Resolución de fecha [FECHA], notificada el [COMPLETAR], que confirma el Acuerdo de [FECHA].

Se adjunta copia de la reclamación previa como DOC. Nº 3 y Resolución de la Mutua/INSS como DOC. Nº 4

SEXTO.- La Resolución del INSS no es ajustada a Derecho por cuanto [COMPLETAR], por lo que debe ser totalmente revocada.

FUNDAMENTOS DE DERECHO

I.- Es competente el Tribunal al que me dirijo en virtud de lo dispuesto en los artículos 1, 2, 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social.

II.- Se cumplen todos los requisitos formales para la presentación de la presente demanda en virtud de lo dispuesto en el artículo 80 de la Ley reguladora de la jurisdicción social, así como en los artículos 71 y 140 a 146 del mismo texto legal que regulan la reclamación administrativa previa. [NOTA DE REVISIÓN: La reclamación previa es administrativa, no «judicial». En cese de actividad es potestativa (art. 350.1 LGSS) y, si se dirige a una mutua, informa una comisión paritaria (art. 350.2 LGSS). Fuente: art. 71 LRJS; art. 350 LGSS (red. RDL 28/2018); LRJS (Ley 36/2011), BOE-A-2011-15936; LGSS (RDLeg 8/2015), BOE-A-2015-11724.]

III.- En cuanto al fondo del asunto es aplicable el arts. 17 y concordantes del Real Decreto Ley 8/2020 de 17 de marzo, de medidas urgentes extraordinarias para hacer frente al impacto económico y social del COVID-19 y normas concordantes.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito con los documentos que lo acompañan, lo admita y, en su virtud, tenga por interpuesta DEMANDA DE IMPUGNACIÓN DE DEVOLUCIÓN DE INGRESOS DE LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS DURANTE EL COVID-19 contra el INSS; la TGSS y [COMPLETAR] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], citando a las partes para los trámites previos de conciliación y, en su caso, juicio, concluyendo las actuaciones con una Sentencia en la que se revoque la Resolución/Acuerdo del órgano gestor de fecha [FECHA] acordando que no procede devolver cantidad alguna por la prestación por cese de actividad percibida como consecuencia del COVID-19, con lo que demás proceda en Derecho.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO que se solicita la reclamación de oficio a la Mutua [COMPLETAR] y al INSS del expediente y antecedentes que posea en relación con el contenido de la demanda.

SEGUNDO OTROSI DIGO que esta parte acudirá al acto del juicio oral acompañada y asistida de Letrado.

TERCER OTROSI DIGO que interesa al Derecho de esta parte que se practiquen en el acto del juicio oral los siguientes:

MEDIOS DE PRUEBA

- DOCUMENTAL: la que esta parte aportará en el acto del juicio, así como la documental aportada con esta demanda y el expediente administrativo.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones y por propuesta la prueba, la admita y la estime pertinente.

Por ser de Justicia que reitero en el lugar y fecha "ut supra"

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
