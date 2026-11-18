---
name: plan-formativo-207
description: "Redacta el escrito «Plan formativo» (formulario 207 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Plan formativo

> Formulario 0207 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… Formación estará vigente durante el año»; «…rsos de formación de los trabajadores de»; «…n que los trabajadores y trabajadoras de»; «…ados y empleadas. Para los trabajadores:»; «…blemas. PROGRAMAS FORMATIVOS PARA EL AÑO»; «…DURACIÓN MODALIDAD DESTINATARIOS A CARGO»; «…gualdad de oportunidades. Por otro lado,»; «… de las acciones formativas se realizará»; «…editar la asistencia igual o superior al»

## Elecciones que hay que hacer

- empresa / organización

## Párrafos opcionales (8)

Inclúyelos solo si encajan en los hechos:

- ACCIÓN FORMATIVA DURACIÓN MODALIDAD DESTINATARIOS A CARGO [COMPLETAR]…
- La realización de cursos sea en horario laboral o, en caso de no poder serlo, consensuar formas de compensació…
- Todos los cursos presenciales se impartan en las propias instalaciones de la empresa.…
- Los cursos tengan enfoque desde una perspectiva de género o un módulo específico en materia de igualdad de opo…
- Ofertar todos los cursos a las personas trabajadoras que se encuentren en situación de excedencia por motivos …
- Programar acciones formativas específicamente dirigidas a trabajadoras para facilitar su promoción a puestos d…
- Realizar formaciones específicas en materia de igualdad, acoso sexual y acoso por razón de sexo.…
- Quienes no hayan completado el citado porcentaje podrán solicitar la certificación de las horas realizadas.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 4.2.b) del ET

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

### Formulario 0207 · Plan formativo

- Año del modelo: 2019
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 7 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

El art. 4.2.b) del ET recoge el derecho de los trabajadores a la promoción y formación profesional en el trabajo, incluida la dirigida a su adaptación a las modificaciones operadas en el puesto de trabajo, así como al desarrollo de planes y acciones formativas tendentes a favorecer su mayor empleabilidad. Las empresas deben desarrollar planes de formación para garantizar este derecho a sus empleados.

Este Plan de Formación estará vigente durante el año [COMPLETAR] y constituye el referente para organizar y contratar la realización de cursos de formación de los trabajadores de [COMPLETAR].

Este documento recoge las necesidades del personal identificadas por la [ELEGIR: empresa / organización], y pretende que la formación desarrollada mejore el crecimiento de la misma y la capacitación de sus personas trabajadoras.

OBJETIVO DEL PLAN DE FORMACIÓN

El objetivo de este plan es proponer acciones formativas que permitan que los trabajadores y trabajadoras de [COMPLETAR] adquieran conocimientos que les son necesarios para el desarrollo de su trabajo o para la mejora de éste.

BENEFICIOS DE LA FORMACIÓN

Para la [ELEGIR: empresa / organización]:

- Mejora de la productividad a través del aprendizaje de nuevos procesos de trabajo, que a su vez aumenta la eficacia y la eficiencia.
- Aumento del nivel de competitividad y rentabilidad de la empresa.
- Mejora de la cualificación de los empleados y empleadas.
- Aumento de la calidad de los productos o servicios.
- Mejora de los procesos de gestión de calidad.
- Incremento del compromiso de todos los empleados y empleadas.

Para los trabajadores: [COMPLETAR]

- Adquisición de nuevos conocimientos, destrezas y habilidades.
- Aumento de la satisfacción y motivación.
- Mejora de la capacidad de la persona trabajadora para asumir nuevas responsabilidades, tomar decisiones y resolver problemas.

PROGRAMAS FORMATIVOS PARA EL AÑO [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]
ACCIÓN FORMATIVA	DURACIÓN	MODALIDAD 	DESTINATARIOS	A CARGO [COMPLETAR]

INSTRUCCIONES GENERALES

Para que cada persona trabajadora realice la formación que realmente necesita y que le ayude a mejorar, se intentará que la formación que reciba sea lo más individualizada y flexible posible.

Además, la empresa procurará que:

[OPCIONAL — incluir si procede]

La realización de cursos sea en horario laboral o, en caso de no poder serlo, consensuar formas de compensación del tiempo empleado fuera del horario laboral.

[OPCIONAL — incluir si procede]

Todos los cursos presenciales se impartan en las propias instalaciones de la empresa.

[OPCIONAL — incluir si procede]

Los cursos tengan enfoque desde una perspectiva de género o un módulo específico en materia de igualdad de oportunidades.

Por otro lado, [COMPLETAR] se compromete a:

[OPCIONAL — incluir si procede]

Ofertar todos los cursos a las personas trabajadoras que se encuentren en situación de excedencia por motivos familiares o con el contrato suspendido por razones vinculadas a la conciliación de la vida laboral y familiar.

[OPCIONAL — incluir si procede]

Programar acciones formativas específicamente dirigidas a trabajadoras para facilitar su promoción a puestos de responsabilidad y a categorías profesionales u ocupaciones en las que estén subrepresentadas.

[OPCIONAL — incluir si procede]

Realizar formaciones específicas en materia de igualdad, acoso sexual y acoso por razón de sexo.

Todos los cursos de formación se difundirán en todos los canales de comunicación de la empresa para asegurar que la información llegue a toda la plantilla.

La inscripción en cualquiera de las acciones formativas se realizará [COMPLETAR].

OBLIGACIONES DEL ALUMNADO

Al finalizar la formación, se realizará una prueba de evaluación para comprobar el grado de asimilación de los contenidos del curso.

Todos los participantes deberán rellenar de forma anónima un cuestionario que les será facilitado al finalizar cada curso que obligatoriamente deberán cumplimentar como compromiso adquirido con la formación recibida. Y en cualquier momento tendrán la posibilidad de hacer llegar sus sugerencias, valoraciones u opiniones al área de Formación.

ASISTENCIA Y CERTIFICADOS

Para obtener el certificado de aprovechamiento, los alumnos deberán acreditar la asistencia igual o superior al [COMPLETAR] de las horas lectivas de la acción formativa.

Una vez finalizado el curso se les entregará el correspondiente certificado.

[OPCIONAL — incluir si procede]

Quienes no hayan completado el citado porcentaje podrán solicitar la certificación de las horas realizadas.

════════════════════════════════════════════════════════════════════════
