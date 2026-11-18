---
name: demanda-contra-denegacion-erte-fuerza-mayor-temporal-179
description: "Redacta el escrito «Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED» (formulario 179 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED

> Formulario 0179 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NIF
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] FECHA (5 veces)
- [ ] ÓRGANO O PERSONA (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…dad de representante legal de la empresa»; «…la Dirección territorial»; «…sentado alegando los siguientes motivos:»; «…esa demandante se encuentra afectada por»; «… de conformidad. Es Justicia que pide en»

## Elecciones que hay que hacer

- por fuerza mayor temporal / en base al mecanismo RED de Flexibilidad y Estabilización del Empleo
- suspensión de los contratos / reducción de jornada

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 151 de la Ley 36/2011
- artículos 2, 6 y 10 de la Ley 36/2011
- artículos 16, 17 y 151.5 de la Ley 36/2011
- artículo 151 de la Ley 36/2011
- artículos 18 y 21 de la Ley 36/2011
- Real Decreto-ley 8/2024

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

### Formulario 0179 · Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED

- Año del modelo: 2020
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 19 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

DICE
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

La impugnación ante la jurisdicción social de los acuerdos y decisiones en materia de suspensión de contratos y reducción de jornada se rige por lo dispuesto en el art. 151 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social.

Formulario actualizado conforme a las novedades introducidas por el Real Decreto-ley 8/2024, de 28 de noviembre

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

[NOTA DE REVISIÓN: Es una demanda: aún no hay plaza asignada. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], en calidad de representante legal de la empresa [COMPLETAR], con NIF núm. [NIF], y domicilio a efectos de notificación en [DOMICILIO A EFECTOS DE NOTIFICACIONES], representación que se acredita mediante escritura de poder que se acompaña, ante este Tribunal de Instancia comparece y, como mejor proceda,

DICE

Que, por medio del presente escrito, y en aplicación del art. 151 de la Ley 36/2011, Reguladora de la Jurisdicción Social, interpongo DEMANDA DE IMPUGNACIÓN DE ACTO ADMINISTRATIVO contra la resolución de fecha [FECHA] dictada por [ÓRGANO O PERSONA], en base en los siguientes

HECHOS

PRIMERO.- La empresa demandante presentó en fecha [FECHA] un expediente de regulación temporal de empleo [ELEGIR: por fuerza mayor temporal / en base al mecanismo RED de Flexibilidad y Estabilización del Empleo] al amparo del art.
47.5 y 6
47 bis
 del Estatuto de los Trabajadores.

SEGUNDO.- En fecha [FECHA] la Dirección territorial [COMPLETAR] dictó resolución denegatoria del ERTE presentado alegando los siguientes motivos: [COMPLETAR].

Se acompaña a la presente demanda la citada resolución como Documento núm. [NÚMERO].

TERCERO.- Contra la anterior resolución se interpuso el correspondiente recurso de alzada, que ha sido desestimado por resolución de fecha [FECHA] dictada en el expediente núm. [NÚMERO].

CUARTO.- Los motivos alegados en la solicitud de expediente de regulación temporal de empleo se consideran suficientes y ajustados a lo previsto en el art. 47.5, 6 y 7y art. 47.bis del Estatuto de los Trabajadores, además de cumplir todos y cada uno de los requisitos legalmente establecidos para su aprobación.

La empresa demandante se encuentra afectada por [COMPLETAR]

Esto ha supuesto una situación que impide la ocupación efectiva de la plantilla en la forma descrita en sus contratos de trabajo que ha hecho necesario adoptar medidas de [ELEGIR: suspensión de los contratos / reducción de jornada].

A los anteriores hechos les son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.- Es competente el Tribunal de Instancia al que se dirige la presente demanda de conformidad a lo establecido en los artículos 2, 6 y 10 de la Ley 36/2011, Reguladora de la Jurisdicción Social.

II.- La demanda contiene los requisitos y exigencias de los artículos 16, 17 y 151.5 de la Ley 36/2011, Reguladora de la Jurisdicción Social.

III.- La administración demandada ostenta la legitimación pasiva en virtud de lo dispuesto en el artículo 151 de la Ley 36/2011, Reguladora de la Jurisdicción Social por ser la autora del acto administrativo impugnado.

IV.- La presente demanda se interpone dirigida por Letrado, en aplicación de los artículos 18 y 21 de la Ley 36/2011, Reguladora de la Jurisdicción Social.

V.- Se ha cumplido el trámite de agotamiento de la vía administrativa mediante recurso de alzada.

VI.-

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— En caso de fuerza mayor temporal determinada por impedimentos o limitaciones en la actividad normalizada de la empresa que sean consecuencia de decisiones adoptadas por la autoridad pública competente, incluidas aquellas orientadas a la protección de la salud pública
— Imposibilidad de acceder al centro de trabajo o transitar por las vías de circulación por recomendaciones, limitaciones o prohibiciones impuestas por la autoridad competente
— Imposibilidad de acceder al centro de trabajo o transitar por las vías de circulación por causa de fuerza mayor, catástrofe o fenómeno meteorológico que conlleva un riesgo grave e inminente para las personas trabajadoras
— En caso de Mecanismo RED

En su virtud,

SUPLICO AL TRIBUNAL, que tenga por presentado este escrito, con sus copias y los documentos que lo acompañan, lo admita, y teniendo por interpuesta en nombre de mi representada DEMANDA DE IMPUGNACIÓN DE ACTO ADMINISTRATIVO contra la resolución de fecha [FECHA] dictada por [ÓRGANO O PERSONA], cite a las partes para los actos de conciliación y, en su caso, juicio, y tras los trámites legales oportunos, dicte en su día sentencia por la que se estime la demanda y se acuerde revocar la resolución impugnada que ha denegado el expediente de regulación temporal de empleo.

OTROSÍ DIGO PRIMERO: Que, a fin de acreditar el fundamento de la pretensión, intereso la práctica de la prueba que a continuación se detalla:

- DOCUMENTAL: consistente en que se requiera a la Administración demandada a fin de que aporte a autos la totalidad del expediente administrativo

AL TRIBUNAL SUPLICO: Que tenga por efectuadas las anteriores manifestaciones y provea de conformidad.

Es Justicia que pide en [COMPLETAR].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
