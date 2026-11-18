---
name: novacion-fijo-discontinuo-indefinido-ordinario-acuerdo-46
description: "Redacta el escrito «Novación de fijo discontinuo a indefinido ordinario: acuerdo» (formulario 46 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Novación de fijo discontinuo a indefinido ordinario: acuerdo

> Formulario 0046 del plugin **Contratación laboral** · revisado el 17-11-2026.

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
- [ ] FECHA (4 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD (2 veces)
- [ ] NIF
- [ ] DNI/NIE
- [ ] IMPORTE
- [ ] Nº
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en su calidad de»; «…s los conceptos y realiza una jornada de»; «…n un contrato indefinido común a jornada»; «…horas al»; «…horas al [COMPLETAR] prestadas de»; «…prestadas de [COMPLETAR] a»; «…a [COMPLETAR] en horario de»; «… establecido en el Convenio Colectivo de»; «… retribución tendrá efectos a partir del»

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0046 · Novación de fijo discontinuo a indefinido ordinario: acuerdo

- Año del modelo: 2024
- Revisión 17-11-2026: 24 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
MANIFIESTAN
CLAUSULAS
Firmas

Acuerdo entre empresa y persona trabajadora de novación contractual de un contrato de trabajo fijo discontinuo a uno indefinido a tiempo completo.

En [LUGAR], a [FECHA].

REUNIDOS

De una parte, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, actuando en representación de [NOMBRE DEL REPRESENTADO/A] en su calidad de [COMPLETAR], con domicilio en [LOCALIDAD] y NIF nº [NIF], (en adelante, la Empresa).

Y de otra, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con domicilio en [LOCALIDAD], provisto/a de DNI nº [DNI/NIE], (en adelante, la persona trabajadora).

Ambas partes se reconocen, la primera en la representación que ostenta y la segunda en su propio nombre y derecho, mutua y plena capacidad para otorgar el presente documento de ACUERDO DE NOVACIÓN DEL CONTRATO DE TRABAJO, y

MANIFIESTAN

I.- Las partes tienen suscrito un contrato de trabajo, de fecha [FECHA], de carácter indefinido fijo discontinuo, contrato que al día de hoy está vigente.

II.- La persona trabajadora está percibiendo actualmente un salario fijo bruto anual de [IMPORTE] euros, incluidos todos los conceptos y realiza una jornada de [COMPLETAR].

III.- Ambas partes están interesadas en transformar el contrato de trabajo fijo discontinuo en un contrato indefinido de carácter ordinario y por ello firman el presente acuerdo en base a las siguientes

CLAUSULAS

PRIMERA.- Las partes acuerdan convertir el actual contrato fijo discontinuo de la persona trabajadora en un contrato indefinido común a jornada [COMPLETAR], que tendrá efectos desde el día [FECHA].

SEGUNDA.- La nueva jornada de trabajo será de [Nº] horas al [COMPLETAR] prestadas de [COMPLETAR] a [COMPLETAR] en horario de [COMPLETAR], aplicándose, en todo caso, el calendario laboral de la Empresa.

TERCERA.- La persona trabajadora percibirá el salario anual correspondiente a su Grupo y Nivel Profesional establecido en el Convenio Colectivo de [COMPLETAR].

La nueva retribución tendrá efectos a partir del [COMPLETAR].

CUARTA.- El presente acuerdo se adjuntará al contrato de trabajo celebrado entre las partes en fecha [FECHA], que quedará modificado conforme a lo así pactado, manteniéndose el resto de condiciones laborales actuales de la persona trabajadora.

Y para que conste, firman el presente documento, por duplicado, en el lugar y fecha al inicio consignados.

LA EMPRESA

EL/LA TRABAJADOR/A

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
