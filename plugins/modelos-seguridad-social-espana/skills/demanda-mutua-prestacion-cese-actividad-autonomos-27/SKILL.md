---
name: demanda-mutua-prestacion-cese-actividad-autonomos-27
description: "Redacta el escrito «Demanda a la Mutua por prestación de cese de actividad de autónomos» (formulario 27 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda a la Mutua por prestación de cese de actividad de autónomos

> Formulario 0027 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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
- [ ] CORREO ELECTRÓNICO
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] FECHA (8 veces)
- [ ] IMPORTE (2 veces)
- [ ] DESCRIBIR
- [ ] Nº DE EXPEDIENTE
- [ ] LUGAR
- [ ] Otros 13 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, asistido/a por el/la Letrado/a»; «…euros y una base reguladora de»; «…Que he estado realizando la actividad de»; «…desde»; «…desde [COMPLETAR] hasta»; «…, con un local abierto al público en»; «…solicité a la Mutua»; «…, notificada el»; «…aciones del IRPF y del IVA del ejercicio»; «…de»; «…restación por cese de mi actividad desde»; «…hasta»; …

## Elecciones que hay que hacer

- Resolución / Acuerdo

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 2.o) de la LJS
- arts. 327 a 350 de la LGSS
- art. 331.1.a) de la LGSS
- art. 331 de la LGSS
- artículos 1, 2, 6 y 10 de la Ley 36/2011

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

### Formulario 0027 · Demanda a la Mutua por prestación de cese de actividad de autónomos

- Año del modelo: 2024
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 2 desplegables y casillas convertidos en elección en blanco; 37 campos de relleno marcados en blanco
- Avisos de la revisión: Cese de actividad: la reclamación previa ante el órgano gestor es potestativa (art. 350.1 LGSS); si resolvió una mutua, informa una comisión paritaria (art. 350.2).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
MEDIOS DE PRUEBA
Firmas

Los órganos jurisdiccionales del orden social conocerán de las cuestiones litigiosas que se promuevan en materia de prestaciones de Seguridad Social, incluidas la protección por desempleo y la protección por cese de actividad de las personas trabajadoras por cuenta propia o autónomos (art. 2.o) de la LJS).

La protección por cese de actividad se rige por lo dispuesto en los arts. 327 a 350 de la LGSS [NOTA DE REVISIÓN: El título V (protección por cese de actividad) abarca los arts. 327 a 350; el 350 regula jurisdicción y reclamación previa y el 351 ya es otro título. Fuente: arts. 327, 350 y 351 LGSS; LGSS (RDLeg 8/2015), BOE-A-2015-11724.], y en sus normas de desarrollo, así como, supletoriamente, por las normas que regulan el régimen especial de la Seguridad Social de encuadramiento.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE], asistido/a por el/la Letrado/a [COMPLETAR], y con domicilio a efectos de notificaciones en su despacho sito en [LOCALIDAD], teléfono [TELÉFONO] y correo electrónico [CORREO ELECTRÓNICO], ante ese Tribunal comparezco y como mejor proceda en Derecho DIGO:

Que por medio del presente escrito formulo DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS contra [ACTO O RESOLUCIÓN] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], en la persona de su legal representante, con domicilio en [LOCALIDAD].

Se apoya la presente demanda en los siguientes

HECHOS

PRIMERO.- Que soy trabajador/a autónomo/a, afiliado/a, en alta, y al corriente de pago en el Régimen Especial de la Seguridad Social de los Trabajadores por Cuenta Propia o Autónomos desde el pasado [FECHA], con una base de cotización mensual de [IMPORTE] euros y una base reguladora de [COMPLETAR].

SEGUNDO.- Que he estado realizando la actividad de [COMPLETAR] desde [COMPLETAR] hasta [COMPLETAR], con un local abierto al público en [COMPLETAR], fecha en la que por motivos [DESCRIBIR] he tenido que cesar definitivamente en la actividad por ser inviable proseguir con la misma.

TERCERO.- Que con fecha [FECHA] solicité a la Mutua [COMPLETAR] la prestación por cese de actividad, que me ha sido denegada por [ELEGIR: Resolución / Acuerdo] de la citada Mutua con fecha [FECHA], expediente nº [Nº DE EXPEDIENTE].

Se acompañan como DOCS. Nº 1 y 2, copia de la solicitud de prestación y carta de denegación de la Mutua.

CUARTO.- Contra dicha comunicación de denegación interpuse reclamación previa a la vía judicial ante el órgano gestor, que fue desestimada por Resolución de fecha [FECHA], notificada el [COMPLETAR], que confirma el Acuerdo de [FECHA].

Se adjunta copia de la reclamación previa como DOC. Nº 3 y Resolución de la Mutua como DOC. Nº 4

QUINTO.- Fundamenta la Mutua su denegación de la prestación en el hecho de que no se han acreditado las pérdidas alegadas y no se ha demostrado la inviabilidad del negocio según lo establecido en el art. 331.1.a) de la LGSS, extremo que es totalmente incierto ya que, como consta en el expediente, el demandante aportó justificante de cierre del establecimiento, la baja en el Censo tributario de empresarios, profesionales y retenedores y la baja en el RETA. Asimismo, constan aportadas las declaraciones del IRPF y del IVA del ejercicio [COMPLETAR] en la que se reflejan las pérdidas económicas alegadas y que son un fiel reflejo de la cuenta de pérdidas y ganancias del balance contable.

Todos estos se reflejan también en la declaración jurada aportada, cumpliéndose, por tanto, todos los requisitos legalmente establecidos en el apartado a) del art. 331 de la LGSS, para causar derecho a la prestación por cese de actividad solicitada, debiendo por tanto ser revocada la resolución/acuerdo de la Mutua por no ser ajustada a derecho.

SEXTO.- Por todo lo expuesto, teniendo el demandante derecho a la prestación que reclama, ha de estimarse la demanda y revocar la [ELEGIR: Resolución / Acuerdo] de [COMPLETAR] de fecha [FECHA] por infringir los arts. 329 y siguientes de la Ley General de la Seguridad Social.

FUNDAMENTOS DE DERECHO

I.- Es competente el Tribunal al que me dirijo en virtud de lo dispuesto en los artículos 1, 2, 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social.

II.- Se cumplen todos los requisitos formales para la presentación de la presente demanda en virtud de lo dispuesto en el artículo 80 de la Ley reguladora de la jurisdicción social, así como en los artículos 71 y 140 a 146 del mismo texto legal que regulan la reclamación administrativa previa. [NOTA DE REVISIÓN: La reclamación previa es administrativa, no «judicial». En cese de actividad es potestativa (art. 350.1 LGSS) y, si se dirige a una mutua, informa una comisión paritaria (art. 350.2 LGSS). Fuente: art. 71 LRJS; art. 350 LGSS (red. RDL 28/2018); LRJS (Ley 36/2011), BOE-A-2011-15936; LGSS (RDLeg 8/2015), BOE-A-2015-11724.]

III.- En cuanto al fondo del asunto son aplicables los arts. 331.1.a), 332.1 y concordantes de la Ley General de la Seguridad Social.

Por lo expuesto,

SUPLICO AL TRIBUNAL que teniendo por presentado este escrito, con sus copias, se sirva admitirlo y, en su virtud, tenga por interpuesta DEMANDA DE RECONOCIMIENTO DEL DERECHO A LA PRESTACIÓN POR CESE DE ACTIVIDAD DE TRABAJADORES AUTÓNOMOS contra [ACTO O RESOLUCIÓN] Mutua de Accidentes de Trabajo y Enfermedades Profesionales de la Seguridad Social nº [NÚMERO], en la persona de su legal representante, citando a las partes para los trámites previos de conciliación y, en su caso, de juicio, concluyendo las actuaciones con una Sentencia en la que se revoque la Resolución/Acuerdo de dicho órgano gestor de fecha [FECHA] y se acuerde mi derecho a percibir la prestación por cese de mi actividad desde [COMPLETAR] hasta [COMPLETAR] conforme a una base reguladora de [IMPORTE] euros.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSI DIGO que se solicita la reclamación de oficio a la Mutua [COMPLETAR] del expediente y antecedentes que posea en relación con el contenido de la demanda.

SEGUNDO OTROSI DIGO que esta parte acudirá al acto del juicio oral acompañada y asistida de Letrado.

TERCER OTROSI DIGO que interesa al Derecho de esta parte que se practiquen en el acto del juicio oral los siguientes:

MEDIOS DE PRUEBA

- DOCUMENTAL: la que esta parte aportará en el acto del juicio, así como la documental aportada con esta demanda y el expediente administrativo.

SUPLICO AL TRIBUNAL que tenga por hechas las anteriores manifestaciones y por propuesta la prueba, la admita y la estime pertinente.

Por ser de Justicia que reitero en el lugar y fecha "ut supra"

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
