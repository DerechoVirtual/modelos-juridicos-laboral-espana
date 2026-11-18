---
name: acta-reunion-comision-seguimiento-plan-igualdad-141
description: "Redacta el escrito «Acta de reunión de la Comisión de seguimiento del Plan de Igualdad» (formulario 141 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acta de reunión de la Comisión de seguimiento del Plan de Igualdad

> Formulario 0141 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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
- [ ] Nº (2 veces)
- [ ] FECHA (2 veces)
- [ ] LUGAR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… intermedia y otra final. Orden del día:»; «…cursada por su presidente/a, se reúne en»; «…horas del día [FECHA]. Acuerdos tomados:»; «…Ruegos y preguntas:»; «…Documentación que se adjunta:»

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- Revisión detallada del grado de implantación de las medidas que incluye el Plan de Igualdad.…
- Fijar medidas para la corrección de las posibles desviaciones observadas.…
- Ruegos y preguntas.…
- Integrantes de la Comisión que asisten:…
- - D./Dña. [NOMBRE Y APELLIDOS] ().…
- - D./Dña. [NOMBRE Y APELLIDOS] ().…
- - D./Dña. [NOMBRE Y APELLIDOS] ().…
- Ruegos y preguntas: [COMPLETAR]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 9 del Real Decreto 901/2020
- Real Decreto 713/2010

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

### Formulario 0141 · Acta de reunión de la Comisión de seguimiento del Plan de Igualdad

- Año del modelo: 2022
- Revisión 17-11-2026: 5 párrafos repetibles señalados; 3 párrafos opcionales señalados; 9 campos de relleno marcados en blanco; 4 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

El art. 9 del Real Decreto 901/2020, de 13 de octubre, por el que se regulan los planes de igualdad y su registro y se modifica el Real Decreto 713/2010, de 28 de mayo, sobre registro y depósito de convenios y acuerdos colectivos de trabajo, regula el seguimento, evaluación y revisión del plan, estableciendo que deberá realizarse de forma periódica conforme se estipule en el calendario de actuaciones del plan de igualdad o en el reglamento que regule la composición y funciones de la comisión encargada del seguimiento del plan de igualdad, y que se realizará al menos una evaluación intermedia y otra final.

Orden del día: [COMPLETAR]

[OPCIONAL — incluir si procede]

Revisión detallada del grado de implantación de las medidas que incluye el Plan de Igualdad.

[OPCIONAL — incluir si procede]

Fijar medidas para la corrección de las posibles desviaciones observadas.

[OPCIONAL — incluir si procede]

Ruegos y preguntas.

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Integrantes de la Comisión que asisten:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] ().

Integrantes de la Comisión que no asisten:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] ().

Participantes de la reunión que no pertenecen a la Comisión:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- D./Dña. [NOMBRE Y APELLIDOS] ().

La Comisión de Seguimiento y Evaluación, según la convocatoria cursada por su presidente/a, se reúne en [COMPLETAR], a las [Nº] horas del día [FECHA].

Acuerdos tomados: [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Ruegos y preguntas: [COMPLETAR]

Documentación que se adjunta: [COMPLETAR]

Se adjunta a este Acta el INFORME DE IMPLANTACIÓN Y SEGUIMIENTO.

Concluye la reunión a las [Nº] horas.

En [LUGAR], a [FECHA].

Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
