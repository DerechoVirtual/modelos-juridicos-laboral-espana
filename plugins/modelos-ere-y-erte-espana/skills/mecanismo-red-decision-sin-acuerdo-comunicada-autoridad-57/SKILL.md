---
name: mecanismo-red-decision-sin-acuerdo-comunicada-autoridad-57
description: "Redacta el escrito «Mecanismo RED: decisión sin acuerdo comunicada a la autoridad laboral» (formulario 57 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mecanismo RED: decisión sin acuerdo comunicada a la autoridad laboral

> Formulario 0057 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…RA. DELEGADO/A TERRITORIAL DE TRABAJO DE»; «…en nombre y representación de la entidad»; «…de fecha [FECHA] iniciado el»; «…esignación de las personas afectadas son»; «…es el»; «…y tendrá una duración hasta»; «…. Las medidas consistirán en»; «…eal Decreto 608/2023, de 11 de julio. En»

## Elecciones que hay que hacer

- suspensión de contratos de trabajo / reducción de jornada
- cíclica / sectorial
- suspensiones de contratos / reducciones de jornada
- suspensión de contratos / reducción de jornada
- suspensión de los contratos / reducción de jornada

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- (Sólo en el caso de la modalidad sectorial del mecanismo RED)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 14 del Real Decreto 608/2023

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

### Formulario 0057 · Mecanismo RED: decisión sin acuerdo comunicada a la autoridad laboral

- Año del modelo: 2023
- Revisión 17-11-2026: 5 desplegables y casillas convertidos en elección en blanco; 2 desplegables convertidos en elección en blanco; 1 párrafos opcionales señalados; 12 campos de relleno marcados en blanco
- Avisos de la revisión: ERTE: art. 47 ET en redacción del RDL 8/2024 (vigente 30-11-2024): consultas de hasta 15 días (7 si menos de 50 personas), fuerza mayor del 47.5 y 47.6 (incluida la imposibilidad de acceso tras los 4 días del 37.3.g), reducción del 10 al 70 %; Mecanismo RED en el art. 47 bis y RD 608/2023.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

EXPONE
Firmas

En el plazo de quince días naturales desde la finalización del periodo de consultas, si este concluye sin acuerdo, la empresa comunicará a la autoridad laboral y a los representantes legales de las personas trabajadoras su decisión final sobre la aplicación del Mecanismo RED, adjuntando las actas que permitan acreditar la celebración de las reuniones mantenidas durante el periodo de consultas y su contenido.

Las actas aportadas a la autoridad laboral deberán estar firmadas por todas las personas integrantes de la comisión negociadora.

AL/A LA SR./SRA. DELEGADO/A TERRITORIAL DE TRABAJO DE [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de DNI número [DNI/NIE], actuando en nombre y representación de la entidad [COMPLETAR], conforme tiene acreditado en el expediente de [ELEGIR: suspensión de contratos de trabajo / reducción de jornada] núm. abierto en esa Delegación Territorial, ante V.I. comparece y,

EXPONE

PRIMERO.- Que las partes no han alcanzado un acuerdo durante el periodo de consultas, en el procedimiento de [ELEGIR: suspensión de contratos de trabajo / reducción de jornada] por las causas previstas en el acuerdo de activación del Mecanismo RED, en su modalidad [ELEGIR: cíclica / sectorial] de fecha [FECHA] iniciado el [COMPLETAR] y comunicado debidamente a esa autoridad laboral, que obra en esa Delegación con el número de expediente indicado.

SEGUNDO.- Que la decisión final de la empresa sobre la aplicación del sistema RED es aplicar las siguientes medidas:

Las causas que motivan las [ELEGIR: suspensiones de contratos / reducciones de jornada], se detallan en la Memoria explicativa que se hace entrega junto a este escrito, así como la documentación que se adjunta acreditativa de la concurrencia de la situación [ELEGIR: cíclica / sectorial] establecida en el acuerdo de activación del Mecanismo RED aprobado por Acuerdo del Consejo de Ministros de fecha [FECHA].

El número y clasificación profesional de las personas trabajadoras afectadas por la medida de [ELEGIR: suspensión de contratos / reducción de jornada], son los siguientes:

Categorías	Afectados/as	No afectados/as	Total	Total general
Hombres	Mujeres	Hombres	Mujeres	Hombres	Mujeres

Los criterios que se han tenido en cuenta para la designación de las personas afectadas son [COMPLETAR].

La fecha prevista para la [ELEGIR: suspensión de los contratos / reducción de jornada] es el [COMPLETAR] y tendrá una duración hasta [COMPLETAR].

Las medidas consistirán en [COMPLETAR].

[OPCIONAL — incluir si procede]

(Sólo en el caso de la modalidad sectorial del mecanismo RED)

La empresa llevará a cabo el siguiente plan de recualificación de las personas afectadas

TERCERO.- Se adjuntan a este todas las actas, firmadas por la comisión negociadora, de las reuniones mantenidas en el período de consultas.

Por lo que,

SOLICITA DE V.I. que, teniendo por presentado este escrito, junto con los documentos que lo acompañan, tenga por efectuada comunicación de la decisión final sobre la aplicación del Mecanismo RED y por cumplida la obligación prevista en el art. 14 del Real Decreto 608/2023, de 11 de julio.

En [COMPLETAR].

════════════════════════════════════════════════════════════════════════
