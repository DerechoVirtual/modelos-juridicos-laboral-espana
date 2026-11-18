---
name: cuestionario-igualdad-direccion-205
description: "Redacta el escrito «Cuestionario de igualdad para la dirección» (formulario 205 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cuestionario de igualdad para la dirección

> Formulario 0205 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] Nº

## Elecciones que hay que hacer

- Hombre / Mujer
- Menos de 45 años / 45 años y más
- Sí / No
- Menos de 2 años / Entre 2 y 5 años / Más de 5 años

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si más del 60% de la plantilla son mujeres / Si más del 60% de la plantilla son hombres — el texto de cada opción no venía en el formulario original

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

### Formulario 0205 · Cuestionario de igualdad para la dirección

- Año del modelo: 2019
- Revisión 17-11-2026: 10 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Este cuestionario es una plantilla editable que permite su personalización para adaptarse a las características y necesidades de su empresa.

Elimine aquellas cuestiones que no sean oportunas para su empresa (datos susceptibles de identificación de la persona que cumplimenta el cuestionario, preguntas dirigidas a empresas feminizadas o masculinizadas) y modifique los apartados de datos personales y profesionales en función de las características de su organización.

DATOS PERSONALES
Sexo: [ELEGIR: Hombre / Mujer]

Edad: [ELEGIR: Menos de 45 años / 45 años y más]

Responsabilidades de cuidados
Hijos/as: [ELEGIR: Sí / No]

Otras personas dependientes: [ELEGIR: Sí / No]

DATOS PROFESIONALES
Antigüedad: [ELEGIR: Menos de 2 años / Entre 2 y 5 años / Más de 5 años]
¿Formas parte de la Representación Legal de las Trabajadoras y Trabajadores?: [ELEGIR: Sí / No]
N.º [Nº]

En qué grado se cumplen estas afirmaciones: 1 (bajo) 4(alto)

Ns/Nc (No sabes/No contestas)

	1	2	3	4	Ns/Nc
1	La igualdad se reconoce como principio básico de la organización.
2	La igualdad es compatible con la filosofía y cultura de la organización en la actualidad.
3	La Dirección de la organización tiene sensibilidad real y compromiso hacia la igualdad de trato y oportunidades entre mujeres y hombres.
4	Se valoran las repercusiones que las decisiones estratégicas tienen en las trabajadoras y trabajadores.
5	Se toman decisiones diferentes en función de si la persona afectada por la decisión es hombre o mujer.
6	Se busca la forma de reequilibrar situaciones donde uno de los sexos está subrepresentado.
7	Se toman las decisiones en espacios que garantizan la presencia de todas las personas implicadas, ya sean hombres o mujeres.
8	Se ha informado a la totalidad de la organización de lo que supone el inicio e implantación del plan.
9	La Dirección está dispuesta a impulsar el plan incluso aunque suponga cambios sustanciales en la forma de trabajo.
10	Se dispone de información suficiente para informar al personal de lo que va a suponer el plan de igualdad en su departamento.
11	Hay protocolos de actuación para casos de acoso sexual y/o por razón de sexo.
12	Sabrías qué hacer en caso de acoso en el departamento del que eres responsable.
13	Tu departamento ofrece las mismas oportunidades a hombres y a mujeres.
14	Si hay desequilibrio en el departamento que diriges lo consideras una situación a corregir.
15	La igualdad está en consonancia con los objetivos de tu departamento.
16	Consideras necesario un plan de igualdad en la organización.
17	Consideras que el plan de igualdad aportará valor a tu departamento.
18	Menciona, por favor, los tres aspectos fundamentales en los que crees que habría que trabajar en materia de igualdad de mujeres y hombres en la organización, de acuerdo a estos ítems.
Necesidades y deficiencias que se deben cubrir para favorecer la igualdad:	Medidas que podría adoptar tu organización para favorecer la igualdad y que respondan a esas necesidades y deficiencias:

1.

2.

3.

1.

2.

3.

Observaciones: escribe a continuación cualquier observación que te haya surgido en relación al cuestionario para que sirva de aclaración y/o ampliación a tus respuestas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si más del 60% de la plantilla son mujeres / Si más del 60% de la plantilla son hombres — el texto de cada opción no venía en el formulario original]

════════════════════════════════════════════════════════════════════════
