---
name: evaluacion-comision-seguimiento-cuestionario-51
description: "Redacta el escrito «Evaluación para la comisión de seguimiento: cuestionario» (formulario 51 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Evaluación para la comisión de seguimiento: cuestionario

> Formulario 0051 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Señalar cuáles:»; «…Señalar cuáles:»; «…Señalar cuáles:»

## Elecciones que hay que hacer

- Hombre / Mujer / LGTBI
- Sí / No
- 0% / 10% / 20% / 30% / 40% / 50% / 60% / 70% / 80% / 90% / 100%

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 9 del RD 901/2020
- art. 9 del RD 1026/2024

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

### Formulario 0051 · Evaluación para la comisión de seguimiento: cuestionario

- Año del modelo: 2023
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 12 desplegables y casillas convertidos en elección en blanco; 3 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

La fase de evaluación cierra el proceso de elaboración e implantación de un plan en la empresa. Permite conocer el grado de cumplimiento de los objetivos definidos y de las medidas del plan ejecutadas.

Según el art. 9 del RD 901/2020 la evaluación de las medidas previstas en el plan de igualdad deberá realizarse de forma periódica conforme se estipule en el calendario de actuaciones del plan de igualdad o en el reglamento que regule la composición y funciones de la comisión encargada del seguimiento del plan de igualdad.

Asimismo, también a través de los convenios colectivos y los acuerdos de empresa podrán establecerse plazos adecuados para evaluar el cumplimiento de las medidas planificadas acordadas, así como los supuestos en los que dichas evaluaciones se deberán llevar a cabo dentro del Plan de medidas para la igualdad y no discriminación de las personas LGTBI como estipula el art. 9 del RD 1026/2024 [NOTA DE REVISIÓN: El art. 9.2 del RD 1026/2024 deja a los convenios o acuerdos fijar plazos y supuestos de evaluación de las medidas LGTBI; la «evaluación intermedia y otra final» procede del art. 9.6 del RD 901/2020 (planes de igualdad). Fuente: RD 1026/2024, art. 9, BOE-A-2024-20402; RD 901/2020, art. 9.6, BOE-A-2020-12214.].No obstante, se realizará al menos una evaluación intermedia y otra final, así como cuando sea acordado por la comisión de seguimiento.

DATOS

Sexo: [ELEGIR: Hombre / Mujer / LGTBI]
¿Formas parte de la RLT? [ELEGIR: Sí / No]

CUESTIONARIO

1. ¿Qué grado de cumplimiento general de los objetivos de la igualdad y no discriminación se ha conseguido?: [ELEGIR: 0% / 10% / 20% / 30% / 40% / 50% / 60% / 70% / 80% / 90% / 100%]

2. ¿El cumplimiento de los objetivos y las acciones propuestas han obtenido los resultados esperados hacia la mejora de la igualdad y no discriminación en la empresa?: [ELEGIR: Sí / No]

3. ¿Se han percibido cambios de actitudes en relación a la igualdad y no discriminación entre las personas de la empresa y su cultura?: [ELEGIR: Sí / No]

4. ¿Qué dificultades se han encontrado en relación al proceso de implementación del Plan?

5. En el caso de que haya habido dificultades: ¿Cómo han sido subsanadas esas dificultades?

6. ¿Se han percibido resistencias en la aplicación del Plan?: [ELEGIR: Sí / No]

Señalar cuáles: [COMPLETAR]

7. ¿Se han incorporado nuevas acciones que inicialmente no estaban previstas en el Plan?: [ELEGIR: Sí / No]

Señalar cuáles: [COMPLETAR]

8. ¿Algunas de las acciones u objetivos previstos han tenido que ser modificados?: [ELEGIR: Sí / No]

Señalar cuáles y qué modificación se ha efectuado

9. ¿Algunas de las acciones u objetivos previstos han tenido que ser desestimados y anulados?: [ELEGIR: Sí / No]

Señalar cuáles: [COMPLETAR]

10. ¿Ha habido participación y apoyo del personal hacia el Plan? Del 1 al 10

11. ¿Ha habido participación y apoyo de la dirección hacia el Plan? Del 1 al 10

12. ¿Los recursos económicos asignados han sido suficientes?: [ELEGIR: Sí / No]

13. ¿El tiempo de cumplimiento de objetivos se ha respetado?: [ELEGIR: Sí / No]

14. ¿La Comisión se ha comprometido adecuadamente con el cumplimiento de los objetivos del Plan?: [ELEGIR: Sí / No]

15. Señalar las barreras que se han encontrado el Plan y propuesta de mejora

════════════════════════════════════════════════════════════════════════
