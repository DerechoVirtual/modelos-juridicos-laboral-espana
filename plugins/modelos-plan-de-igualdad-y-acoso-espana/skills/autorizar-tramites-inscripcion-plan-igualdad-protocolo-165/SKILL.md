---
name: autorizar-tramites-inscripcion-plan-igualdad-protocolo-165
description: "Redacta el escrito «Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso» (formulario 165 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso

> Formulario 0165 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (6 veces)
- [ ] DNI/NIE (3 veces)
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… LABORAL (REGCON) REUNIDOS De una parte:»; «…, en representación de la empresa»; «…. De otra parte:»; «…e los trabajadores de la citada sociedad»; «…de la empresa»; «…, a [FECHA]. Firmado:»

## Elecciones que hay que hacer

- Plan de igualdad / Protocolo de prevención y actuación ante el acoso sexual y por razón de sexo
- NIF / NIE

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: (Autorización para la inscripción del Plan de Igualdad / (Autorización para la inscripción del Protocolo de prevención y actuación ante situaciones de acoso sexual y por razón de sexo — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS] con DNI nº [DNI/NIE], en representación de la empresa [COMPLETAR].…
- D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE], en representación de los trabajadores de la citada socieda…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 6 del Real Decreto 713/2010
- Ley Orgánica 3/2007

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

### Formulario 0165 · Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso

- Año del modelo: 2021
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 2 párrafos repetibles señalados; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 14 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
REUNIDOS
EXPONEN
Firmas

El artículo 6 del Real Decreto 713/2010, de 28 de mayo, sobre registro y depósito de convenios y acuerdos colectivos de trabajo, expresa que, para proceder a la inscripción del plan de igualdad de la empresa, la comisión negociadora o quien formule la solicitud, debidamente acreditada, deberá presentar a través de medios electrónicos ante el Registro de la autoridad laboral competente la solicitud de inscripción correspondiente.

A estos efectos, será solicitante de la inscripción del plan la persona designada por la comisión negociadora. La autorización será uno de los documentos en la relación a adjuntar en la solicitud de inscripción.

A través de este formulario podemos también autorizar a una persona a realizar el trámite de inscripción del Protocolo para la prevención del acoso sexual y el acoso por razón de sexo.

A LA AUTORIDAD LABORAL (REGCON)

REUNIDOS

De una parte: [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] con DNI nº [DNI/NIE], en representación de la empresa [COMPLETAR].

De otra parte: [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE], en representación de los trabajadores de la citada sociedad [COMPLETAR].

Las personas antes descritas, en su calidad de integrantes de la comisión paritaria negociadora encargada de la promoción, seguimiento y evaluación del plan de igualdad para la citada mercantil, previsto en los artículos 45 y siguientes de la Ley Orgánica 3/2007, de 22 de marzo, para la igualdad efectiva de mujeres y hombres, según consta la acreditación en el resto de documentación adjunta,

EXPONEN

[ELEGIR UNA OPCIÓN Y REDACTARLA: (Autorización para la inscripción del Plan de Igualdad / (Autorización para la inscripción del Protocolo de prevención y actuación ante situaciones de acoso sexual y por razón de sexo — el texto de cada opción no venía en el formulario original]

Por lo expuesto, las personas autorizantes

SOLICITAN se tenga por presentada AUTORIZACIÓN por la comisión negociadora para realizar los trámites de inscripción del [ELEGIR: Plan de igualdad / Protocolo de prevención y actuación ante el acoso sexual y por razón de sexo] de la empresa [COMPLETAR], en la siguiente persona:

D/Dña. [NOMBRE Y APELLIDOS], provisto/a de documento de identidad [ELEGIR: NIF / NIE] nº [DNI/NIE], y con domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], con quien deberán cumplimentarse los trámites derivados de la inscripción en el futuro, y que firma con los solicitantes en prueba expresa de su aceptación.

En [LUGAR], a [FECHA].

Firmado: [COMPLETAR]

Representantes de la comisión paritaria por la empresa

Representantes de la comisión paritaria por los trabajadores

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

Persona designada para los trámites de inscripción

Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
