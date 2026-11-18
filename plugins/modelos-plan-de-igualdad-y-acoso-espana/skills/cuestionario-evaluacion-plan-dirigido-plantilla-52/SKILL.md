---
name: cuestionario-evaluacion-plan-dirigido-plantilla-52
description: "Redacta el escrito «Cuestionario de evaluación del plan dirigido a la plantilla» (formulario 52 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cuestionario de evaluación del plan dirigido a la plantilla

> Formulario 0052 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…rdado por la comisión de seguimiento. En»; «…CUESTIONARIO:»

## Elecciones que hay que hacer

- Hombre / Mujer
- Menos de 45 años / 45 años y más
- Sí / No
- Menos de 2 años / Entre 2 y 5 años / Más de 5 años

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 9 del RD 901/2020

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

### Formulario 0052 · Cuestionario de evaluación del plan dirigido a la plantilla

- Año del modelo: 2023
- Revisión 17-11-2026: 23 desplegables y casillas convertidos en elección en blanco; 1 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

La fase de evaluación cierra el proceso de elaboración e implantación de un plan de igualdad en la empresa. Permite conocer el grado de cumplimiento de los objetivos definidos y de las medidas del plan ejecutadas.

Según el art. 9 del RD 901/2020 la evaluación de las medidas previstas en el plan de igualdad deberá realizarse de forma periódica conforme se estipule en el calendario de actuaciones del plan de igualdad o en el reglamento que regule la composición y funciones de la comisión encargada del seguimiento del plan de igualdad.

No obstante, se realizará al menos una evaluación intermedia y otra final, así como cuando sea acordado por la comisión de seguimiento.

En [COMPLETAR] estamos en proceso de evaluación de nuestro Plan de Igualdad.

A continuación, en este cuestionario de carácter ANÓNIMO y estrictamente CONFIDENCIAL, encontrarás una serie de preguntas diseñadas para conocer tu percepción acerca de diferentes aspectos relacionados con la implantación del Plan de Igualdad.

Por tratarse de un cuestionario de opiniones, recordamos que no existen respuestas correctas o incorrectas y lo que realmente nos interesa es tu espontaneidad y sinceridad.

Gracias de antemano por tu colaboración.

DATOS PERSONALES

Sexo [ELEGIR: Hombre / Mujer]
Edad [ELEGIR: Menos de 45 años / 45 años y más]
Responsabilidades de cuidados
Hijos/as [ELEGIR: Sí / No]
Otras personas dependientes [ELEGIR: Sí / No]

DATOS PROFESIONALES

Grupo profesional
Puesto
Mando intermedio
Técnico
Administrativo u/y otros
Antigüedad: [ELEGIR: Menos de 2 años / Entre 2 y 5 años / Más de 5 años]
¿Tienes personal a cargo?: [ELEGIR: Sí / No]
¿Formas parte de la Representación Legal de Trabajadores y Trabajadoras? [ELEGIR: Sí / No]

CUESTIONARIO: [COMPLETAR]

1. ¿Consideras que ha mejorado la situación de igualdad de la empresa con el Plan de Igualdad implementado?: [ELEGIR: Sí / No]

2. ¿Crees que ha servido para:

• ajustar condiciones laborales de las mujeres (salarios, contratos...)?: [ELEGIR: Sí / No]

• mejorar las políticas de conciliación en la empresa?: [ELEGIR: Sí / No]

• mejorar las políticas de corresponsabilidad en la empresa?: [ELEGIR: Sí / No]

• aumentar la presencia y participación de mujeres en la toma de decisiones?: [ELEGIR: Sí / No]

• cambiar la mentalidad de uso del tiempo y presencia en el trabajo?: [ELEGIR: Sí / No]

• tomar conciencia de las barreras, discriminaciones y estereotipos de género?: [ELEGIR: Sí / No]

• equilibrar la plantilla en relación con el número de mujeres y hombres?: [ELEGIR: Sí / No]

• extender el uso del lenguaje y comunicación no sexista?: [ELEGIR: Sí / No]

• tener las mismas oportunidades hombres y mujeres?: [ELEGIR: Sí / No]

• otras? Indicar cuáles

3. ¿Las acciones que se han desarrollado han servido para sensibilizarte y tener más presente las situaciones de desigualdad de género?: [ELEGIR: Sí / No]

4. ¿Consideras que has sido suficientemente informado/a sobre el proceso?: [ELEGIR: Sí / No]

5. Si tuvieras alguna duda o consulta sobre temas de igualdad ¿sabrías dónde dirigirte para resolverla?: [ELEGIR: Sí / No]

6. ¿Has recibido formación sobre igualdad?: [ELEGIR: Sí / No]

7. ¿Crees que se ha implicado a toda la empresa en el plan de igualdad?: [ELEGIR: Sí / No]

8. ¿Consideras que se han alcanzado los objetivos del plan de igualdad propuestos inicialmente?: [ELEGIR: Sí / No]

9. Tu valoración global: del 1 al 10 en cuanto a satisfacción con el Plan de Igualdad

10. ¿Qué destacarías como más positivo del proceso de implantación del Plan de Igualdad?

11. ¿Qué destacarías como más negativo del proceso de implantación del Plan de Igualdad?

12. ¿Qué acciones consideras que han sido más efectivas?

════════════════════════════════════════════════════════════════════════
