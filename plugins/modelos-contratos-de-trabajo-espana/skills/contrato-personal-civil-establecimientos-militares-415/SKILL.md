---
name: contrato-personal-civil-establecimientos-militares-415
description: "Redacta el escrito «Contrato de personal civil de establecimientos militares» (formulario 415 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato de personal civil de establecimientos militares

> Formulario 0415 del plugin **Contratación laboral** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] Nº (3 veces)
- [ ] IMPORTE
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… contratación de un puesto de trabajo de»; «…por la Dirección de Servicios»; «… trabajadora prestará sus servicios como»; «…, incluido en el grupo»; «…y la categoría profesional de»; «…80, para la realización de las funciones»; «…tar sito en La jornada de trabajo será a»; «…. La duración del presente contrato será»; «…980 se establece un periodo de prueba de»; «…ADORA una especialización profesional en»

## Elecciones que hay que hacer

- año / mes / semana

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 14 del Real Decreto 2205/1980
- art. 7 del RD 2205/1980
- art. 12 del RD 2205/1980
- art. 49 del RD 2205/1980

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

### Formulario 0415 · Contrato de personal civil de establecimientos militares

- Año del modelo: 2015
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 16 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

En [LUGAR], a [FECHA].

EXPONEN

I. Que la EMPRESA es un Establecimiento Militar, estando autorizado a la contratación de un puesto de trabajo de [COMPLETAR] por la Dirección de Servicios [COMPLETAR], habiéndose cumplido el resto de requisitos establecidos en el art. 14 del Real Decreto 2205/1980

II. Que la PERSONA TRABAJADORA ha superado las pruebas de aptitud convocadas para el acceso al referido puesto, reuniendo los requisitos de capacidad establecidos en el art. 7 del RD 2205/1980.

III. Que concurriendo los elementos exigidos para la celebración del presente contrato acuerdan formalizarlo ajustado a lo dispuesto en el art. 8 del citado RD 2205/1980 y con arreglo a las siguientes

CLAÚSULAS

La persona trabajadora prestará sus servicios como [COMPLETAR], incluido en el grupo [COMPLETAR] y la categoría profesional de [COMPLETAR] incluida en el Anexo del RD 2205/1980, para la realización de las funciones [COMPLETAR] en el establecimiento militar sito en

La jornada de trabajo será a [COMPLETAR], con una duración de [Nº] horas semanales (durante [Nº] días al [ELEGIR: año / mes / semana]).

La duración del presente contrato será [COMPLETAR], iniciándose la relación laboral el día [FECHA]

De conformidad a lo dispuesto en el art. 12 del RD 2205/1980 se establece un periodo de prueba de [COMPLETAR] durante cuyo transcurso podrá resolverse la relación laboral a instancia de cualesquiera de las partes sin especificación de causa, necesidad de preaviso, ni derecho a indemnización

La PERSONA TRABAJADORA percibirá una retribución total de [IMPORTE] euros brutos que se distribuirán por los siguientes conceptos:

Asimismo percibirá las retribuciones por trienios y complementarias establecidas en el RD 2205/1980, de acuerdo con los requisitos y condiciones fijados en dicha norma.

La promoción, el tiempo trabajado, descansos, permisos y vacaciones, así como la modificación y suspensión se sujetarán al régimen previsto en el RD 2205/1980.

El contrato de trabajo se extinguirá por las causas establecidas en el art. 49 del RD 2205/1980.

El contrato se extinguirá asimismo por renuncia de la PERSONA TRABAJADORA, comunicando su propósito a la Jefatura del Establecimiento con una antelación no inferior a quince días respecto de la fecha en que deba cesar. Producida la baja, si posteriormente reingresase en cualquier Establecimiento Militar, será considerado como de nuevo ingreso a todos los efectos.

A estos efectos, tendrán también la consideración de renuncia en el trabajo: a) Las faltas de asistencia, ininterrumpidas o injustificadas, de seis o más días laborables de duración; b) La falta de incorporación dentro del plazo que se fije, cuando se trata de traslados o reingresos, salvo causa justificada de fuerza mayor; y c) La no reincorporación al puesto de trabajo, en los supuestos de excedencia voluntaria o forzosa, dentro de los plazos señalados en los artículos cuarenta y siete y cuarenta y ocho salvo fuerza mayor.

El personal que cause baja por decisión voluntaria sin comunicarlo previamente en la forma dispuesta, perderá la parte proporcional de pagas extraordinarias, vacaciones y otras retribuciones no básicas, que pudieran corresponderle.

En todas las cuestiones que afecten a la relación individual de trabajo así como a los derechos colectivos, se estará a lo dispuesto en el Real Decreto 2205/1980, de 13 de junio, por el que se regula el trabajo del personal civil no funcionario en los establecimientos militares.

Al haber adquirido la PERSONA TRABAJADORA una especialización profesional en [COMPLETAR] con cargo a la Administración Militar, se pacta un compromiso de permanencia de [Nº] años desde la finalización de la especialización.

El incumplimiento de este pacto por parte de la persona trabajadora dará derecho a que se exija la correspondiente indemnización por daños y perjuicios.

En prueba de conformidad, una vez leído el contrato, ambas partes firman el presente documento por duplicado a un solo efecto, en el lugar y fecha indicados en el encabezamiento.

LA EMPRESA LA PERSONA TRABAJADORA

================================================================================
