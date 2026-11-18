---
name: incumplimiento-precontrato-trabajo-demanda-danos-244
description: "Redacta el escrito «Incumplimiento de precontrato de trabajo: demanda de daños y perjuicios» (formulario 244 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Incumplimiento de precontrato de trabajo: demanda de daños y perjuicios

> Formulario 0244 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Es una demanda: no hay todavía «autos» ni plaza; debe acreditarse la conciliación o mediación previa (arts. 63 y 80.2 LRJS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] COLEGIO
- [ ] NIF (3 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (4 veces)
- [ ] IMPORTE (3 veces)
- [ ] ACTO O RESOLUCIÓN
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…fectos de citaciones y notificaciones en»; «…, con número de colegiado/a»; «…ación que consta acreditada en los autos»; «…NIF [NIF]. — La entidad aseguradora»; «…NIF [NIF] Número de Póliza»; «… que la relación laboral se iniciaría el»; «…prestaba servicios para»; «… D./Dña. [NOMBRE Y APELLIDOS] comunicó a»; «…dejaba sin efecto el acuerdo suscrito el»; «…rtes acordaron, en virtud de la cláusula»; «…y»; «…euros»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 90.1 de la LRJS

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

### Formulario 0244 · Incumplimiento de precontrato de trabajo: demanda de daños y perjuicios

- Año del modelo: 2018
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 33 campos de relleno marcados en blanco
- Avisos de la revisión: Es una demanda: no hay todavía «autos» ni plaza; debe acreditarse la conciliación o mediación previa (arts. 63 y 80.2 LRJS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
HECHOS:
Firmas

Para la existencia de indemnización hará falta acreditar la existencia del precontrato y la de los daños y perjuicios. Y habrá que tener en cuenta que el Estatuto de los Trabajadores no define lo que se entiende por un precontrato ni regula el derecho a una indemnización en caso de incumplimiento contractual.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], con domicilio, a efectos de citaciones y notificaciones en [COMPLETAR], Letrado/a en ejercicio del Ilustre Colegio de Abogados de [COLEGIO], con número de colegiado/a [COMPLETAR] y de D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de NIF [NIF], representación que consta acreditada en los autos [COMPLETAR], ante la Sección de lo Social del Tribunal de Instancia de [SEDE], comparezco [NOTA DE REVISIÓN: Es una demanda: no hay todavía plaza ni «autos». Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.] y como mejor proceda en Derecho, DIGO:

Que mediante el presente escrito formulo demanda en reclamación de INDEMNIZACIÓN POR DAÑOS Y PERJUICIOS OCASIONADOS POR INCUMPLIMIENTO DE PRECONTATO DE TRABAJO, con resultado de lesiones frente a:

— con domicilio en [LOCALIDAD] NIF [NIF].
— La entidad aseguradora [COMPLETAR] con domicilio social en [LOCALIDAD] NIF [NIF] Número de Póliza [COMPLETAR].

A fin de que por este Tribunal se dicte Sentencia de conformidad con el suplico de la presente, lo que fundamento en los siguientes:

HECHOS:

PRIMERO.- Que D./Dña. [NOMBRE Y APELLIDOS], suscribió en fecha [FECHA], un acuerdo de precontrato o promesa de contrato de trabajo, en virtud del cual las partes acordaron que la relación laboral se iniciaría el [COMPLETAR], con las siguientes condiciones:

SEGUNDO.- Que previamente D./Dña [NOMBRE Y APELLIDOS] prestaba servicios para [COMPLETAR], bajo la modalidad de contrato de trabajo indefinido, percibiendo un salario anual bruto de [IMPORTE] euros.

TERCERO.- Que el día [FECHA], D./Dña. [NOMBRE Y APELLIDOS] comunicó a [COMPLETAR] que dejaba sin efecto el acuerdo suscrito el [COMPLETAR] por no interesarle la relación laboral.

CUARTO.- Que en el precontrato firmado la partes acordaron, en virtud de la cláusula [COMPLETAR], una indemnización de daños y perjuicios por importe de [IMPORTE], ante el incumplimiento de lo acordado.

QUINTO.- Que el día [FECHA] se celebró el preceptivo Acto de Conciliación ante el Servicio de Mediación, Arbitraje y Conciliación, el cual finalizó sin avenencia, tal y como se acredita mediante copia de la correspondiente acta que se acompaña como documento número tres a la presente demanda.

Los fundamentos legales y jurisprudenciales se alegarán en el momento procesal oportuno.

Por todo ello,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA, que [NOTA DE REVISIÓN: Demanda: sin número de plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.] teniendo por presentado este escrito, con sus copias y documentos que lo acompañan, lo admita a trámite y tenga por formulada DEMANDA en reclamación de INDEMNIZACIÓN POR LOS DAÑOS Y PERJUICIOS OCASIONADOS POR INCUMPLIMIENTO DE PRECONTATO DE TRABAJO contra [ACTO O RESOLUCIÓN] y [COMPLETAR], cite a las partes a los Actos de Conciliación y Juicio, se siga éste por sus trámites habituales, incluyendo el recibimiento del pleito a prueba que desde este momento se interesa y en su momento dicte sentencia mediante la cual condene a los codemandados a abonar a mi representado la cantidad de [IMPORTE] euros [COMPLETAR],con todo cuanto más proceda en Derecho.

PRIMER OTROSÍ DIGO: Que interesa al Derecho de esta parte valerse en el Acto del Juicio de los siguientes medios de prueba:

DOCUMENTAL

En cumplimiento de lo dispuesto por el artículo 90.1 de la LRJS entiende esta parte que la prueba documental y/o pericial solicitada por medio del presente escrito debe ser considerada útil y directamente pertinente al objeto del presente juicio, pues (a) acreditará la existencia del acuerdo, (b) los perjuicios generados por el incumplimiento.

SEGUNDO OTROSÍ DIGO: Que esta parte asistirá al Acto del Juicio, acompañada de Letrado que le defienda y cuyo domicilio a efectos de citaciones y notificaciones se designa:

D./Dña. [NOMBRE Y APELLIDOS]

Por todo lo expuesto,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA, que tenga por realizadas las anteriores manifestaciones y por solicitados las pruebas propuestas, admitiéndolas y ordenando lo necesario para su práctica.

En [LUGAR], a [FECHA].

════════════════════════════════════════════════════════════════════════
