---
name: acuerdo-voluntarios-412
description: "Redacta el escrito «Acuerdo con voluntarios» (formulario 412 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acuerdo con voluntarios

> Formulario 0412 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] Nº
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, con sede social en»; «…grama «», en las siguientes actividades:»; «… cumplimiento de los fines altruistas de»; «…varán a cabo en el centro de atención de»; «…en»; «…en [COMPLETAR], de»; «…, si bien tanto el/la voluntario/a como»

## Elecciones que hay que hacer

- Asociación / Fundación
- meses / años

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

### Formulario 0412 · Acuerdo con voluntarios

- Año del modelo: 2015
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 14 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

La [ELEGIR: Asociación / Fundación], con sede social en [COMPLETAR], y D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI núm. [DNI/NIE], acuerdan el siguiente COMPROMISO DE VOLUNTARIADO:

D./Dña. [NOMBRE Y APELLIDOS], como voluntario/a de la [ELEGIR: Asociación / Fundación] va a colaborar con la entidad, dentro del Programa «», en las siguientes actividades: [COMPLETAR].

Aunque la relación no tiene vinculación laboral ni mercantil, existen ciertas normas que el buen funcionamiento y cumplimiento de los fines altruistas de [COMPLETAR] requieren. Del mismo modo, el/la voluntario/a no debe asumir gastos en el desarrollo de su labor como tal, que se limita a colaborar altruistamente en la medida que le sea posible. Como consecuencia de ello,

ACUERDAN

PRIMERO. Las actividades de voluntariado se llevarán a cabo en el centro de atención de [COMPLETAR] en [COMPLETAR], de [COMPLETAR].

SEGUNDO. El/La voluntario/a se compromete a:

- Cumplir con los compromisos adquiridos con la organización, respetando los fines y su normativa.
- Guardar confidencialidad de la información recibida en el desarrollo de su actividad.
- Rechazar cualquier contraprestación material o económica.
- Respetar los derechos de los beneficiarios y actuar de forma diligente y solidaria.

TERCERO. Por su parte, la Asociación/Fundación se compromete a:

- Ofrecer al/a la voluntario/a la información, formación, apoyo y en su caso los medios materiales necesarios para el ejercicio de las funciones que se le asignen.
- Favorecer la participación activa del/de la voluntario/a en la organización, diseño, evaluación y programación de las actividades que realiza.
- Asegurar al/a la voluntario/a contra los riesgos de accidente y responsabilidad civil derivados del ejercicio de la actividad.
- Compensar económicamente al/a la voluntario/a por los gastos derivados de su actividad como tal.

CUARTO. El presente acuerdo tiene una duración de [ELEGIR: meses / años], si bien tanto el/la voluntario/a como [COMPLETAR] pueden dejar sin efecto este acuerdo en cualquier momento, siendo deseable que así se lo notifiquen entre ellos con una antelación de [Nº] días.

En [LUGAR], a [FECHA].

El/La voluntario/a

Por la Entidad

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

================================================================================
