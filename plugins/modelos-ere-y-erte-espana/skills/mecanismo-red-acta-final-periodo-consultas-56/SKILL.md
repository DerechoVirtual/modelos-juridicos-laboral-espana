---
name: mecanismo-red-acta-final-periodo-consultas-56
description: "Redacta el escrito «Mecanismo RED: acta final del periodo de consultas» (formulario 56 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mecanismo RED: acta final del periodo de consultas

> Formulario 0056 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] NIF (2 veces)
- [ ] Nº
- [ ] FECHA (5 veces)
- [ ] LOCALIDAD
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…OS EXPONEN ADOPTAN EL SIGUIENTE ACUERDO:»; «… periodo de consultas y su contenido. En»; «…dad de representante legal de la empresa»; «…con NIF [NIF] En»; «…con NIF [NIF] En [COMPLETAR] a»; «…por lo que ADOPTAN EL SIGUIENTE ACUERDO:»; «…DE»; «…diente reducción es el que se abonaba en»; «…s afectadas por este expediente: Firmas:»

## Elecciones que hay que hacer

- cíclico / sectorial
- suspensión de contratos / reducción de jornada
- suspensiones de los contratos de trabajo / reducciones de jornada
- reducción de jornada / suspensión de contratos
- REDUCIR LA JORNADA / SUSPENDER LOS CONTRATOS
- Segundo / Tercero
- realizar su jornada completa / incorporarse a su puesto
- Tercero / Cuarto
- Cuarto / Quinto

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la medida propuesta es de reducción de jornada / Si la medida propuesta es de suspensión de contratos — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de suspensions de contratos / En caso de reducciones de jornada — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS] con NIF [NIF]…
- Segundo.- Habida cuenta de que las personas trabajadoras y la empresa pactaron una reducción salarial en [LOCA…
- [ELEGIR: Tercero / Cuarto].- Si tuviera que realizarse alguna extinción por causas objetivas, vigente esta red…
- (Solo en el caso de modalidad sectorial del Mecanismo RED)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 47 bis del Estatuto de los Trabajadores
- artículo 11 del RD 608/2023

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

### Formulario 0056 · Mecanismo RED: acta final del periodo de consultas

- Año del modelo: 2023
- Revisión 17-11-2026: 8 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 2 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
ADOPTAN EL SIGUIENTE ACUERDO: [COMPLETAR]
Firmas

En el plazo de quince días naturales desde la finalización del periodo de consultas, si este concluye con acuerdo, la empresa lo remitirá íntegramente a la autoridad laboral, adjuntando las actas que permitan acreditar la celebración de las reuniones mantenidas durante el periodo de consultas y su contenido.

En [COMPLETAR]

REUNIDOS

De una parte D./Dña. [NOMBRE Y APELLIDOS], con DNI número [DNI/NIE], en calidad de representante legal de la empresa [COMPLETAR], con NIF [NIF].

De la otra parte, y en calidad de representantes de las personas trabajadoras:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] con NIF [NIF]

En [COMPLETAR] a [COMPLETAR] y siendo las [Nº] horas, se han reunido en el domicilio social de la empresa quienes se han acreditado recíprocamente como representantes de la misma y de las personas trabajadoras, cuyos nombres figuran al inicio de esta acta, reconociéndose todos ellos capacidad legal suficiente para el otorgamiento del presente documento.

EXPONEN

Habiéndose iniciado en fecha [FECHA] el correspondiente periodo de consultas para la reducción de jornada propuesta por la empresa ex art. 47 bis del Estatuto de los Trabajadores debido a causas previstas en el acuerdo de activación del Mecanismo RED [ELEGIR: cíclico / sectorial] acordado en el Consejo de Ministros de fecha [FECHA], la presente reunión tiene por objeto la continuación del periodo de consultas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la medida propuesta es de reducción de jornada / Si la medida propuesta es de suspensión de contratos — el texto de cada opción no venía en el formulario original]

Por las personas trabajadoras, tras un estudio pormenorizado de la documentación entregada por la empresa, resueltas las dudas planteadas y atendidas las propuestas realizadas en las reuniones previas, se decide, al entender como ciertas y justificadas las razones esgrimidas por la empresa, llegar a un acuerdo en este expediente de [ELEGIR: suspensión de contratos / reducción de jornada]. A tal efecto proponen a la empresa, el concreto e individualizado calendario de [ELEGIR: suspensiones de los contratos de trabajo / reducciones de jornada] de cada una de las personas trabajadoras afectadas.

El referido acuerdo, que se expondrá a continuación, se inscribe en el marco de lo que dispone el artículo 11 del RD 608/2023, de 11 julio, y es pactado por quienes legitimados por la Ley, se reconocen capacidad bastante para adoptar el mismo.

El acuerdo se ha alcanzado sobre los siguientes puntos:

Ambas partes reunidas entienden acreditada, en base a la documentación técnica y explicativa aportada, la existencia de una causa justificativa de la aplicación del Mecanismo RED motivadora del expediente de [ELEGIR: reducción de jornada / suspensión de contratos] instado por la empresa, por lo que

ADOPTAN EL SIGUIENTE ACUERDO: [COMPLETAR]

Primero.- Ante la referida causa coyuntural, LAS PARTES ACUERDAN [ELEGIR: REDUCIR LA JORNADA / SUSPENDER LOS CONTRATOS] DE [COMPLETAR] PERSONAS TRABAJADORAS que se refieren a continuación, y tal y como se refiere desde el [FECHA] hasta el [FECHA], de acuerdo con el siguiente resumen:

EMPRESA	PERSONA TRABAJADORA	N.I.F.	N.A.S.S.	CAT. PROF.

[ELEGIR UNA OPCIÓN Y REDACTARLA: En caso de suspensions de contratos / En caso de reducciones de jornada — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

Segundo.- Habida cuenta de que las personas trabajadoras y la empresa pactaron una reducción salarial en [LOCALIDAD], pero sin la correspondiente reducción de jornada, el salario a tener en cuenta, y sobre el que practicará la correspondiente reducción es el que se abonaba en [COMPLETAR].

[ELEGIR: Segundo / Tercero].- Si por necesidades organizativas o productivas se requiriera el trabajo efectivo y a jornada completa de personas trabajadoras afectadas por la [ELEGIR: reducción de jornada / suspensión de contratos], la empresa comunicará a dichas personas con un plazo mínimo de 48 horas que deben [ELEGIR: realizar su jornada completa / incorporarse a su puesto] y estos cumplirán con su obligación de prestar servicios en las fechas en las que para ello sean requeridos. En tal caso la empresa presentará la correspondiente comunicación ante la Dirección Territorial de Trabajo a los efectos oportunos.

[OPCIONAL — incluir si procede]

[ELEGIR: Tercero / Cuarto].- Si tuviera que realizarse alguna extinción por causas objetivas, vigente esta reducción de jornada o tras ella, el salario regulador a efectos del cálculo de la indemnización legalmente establecida para los despidos objetivos será el que percibiría la persona trabajadora a jornada completa, es decir sin tener en cuenta las reducciones de jornada y salariales acordadas en este documento.

[OPCIONAL — incluir si procede]

(Solo en el caso de modalidad sectorial del Mecanismo RED)

[ELEGIR: Cuarto / Quinto].- La empresa pondrá en marcha, en fecha [FECHA], el siguiente plan de recualificación de las personas trabajadoras afectadas por este expediente:

Firmas: [COMPLETAR]

Empresa	Personas trabajadoras
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
