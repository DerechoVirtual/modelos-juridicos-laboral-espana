---
name: reglamento-comision-seguimiento-evaluacion-136
description: "Redacta el escrito «Reglamento de la Comisión de seguimiento y evaluación» (formulario 136 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reglamento de la Comisión de seguimiento y evaluación

> Formulario 0136 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…eto y evaluación del plan de igualdad de»; «…D./Dña. [NOMBRE Y APELLIDOS],»; «…ación y revisión del Plan de Igualdad de»; «…e implementación del Plan de Igualdad en»

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS], [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 9.5 del RD 901/2020

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

### Formulario 0136 · Reglamento de la Comisión de seguimiento y evaluación

- Año del modelo: 2022
- Revisión 17-11-2026: 1 párrafos repetibles señalados; 10 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Conforme al art. 9.5 del RD 901/2020, en el plan de igualdad deberá incluirse una comisión u órgano concreto de seguimiento, con la composición y atribuciones que se decidan en aquél, en el que deberán participar de forma paritaria la representación de la empresa y de las personas trabajadoras y, en la medida de lo posible, tendrá una composición equilibrada entre mujeres y hombres.

Artículo 1.- Constitución

La Comisión de seguimiento y evaluación se ocupará de velar por el cumplimento de los compromisos adoptados en el Plan de Igualdad, así como de revisar periódicamente el grado de implantación de las medidas acordadas.

Artículo 2.- Composición

La Comisión de seguimiento y evaluación del plan de igualdad estará conformada por un grupo paritario entre la representación de la empresa y de las personas trabajadoras, y que, en la medida de lo posible, tendrá una composición equilibrada entre mujeres y hombres.

Integrarán la Comisión de seguimineto y evaluación del plan de igualdad de [COMPLETAR]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], [COMPLETAR].

Articulo. 3.- Declaración de intenciones y obligaciones

El presente protocolo tiene como finalidad regular la forma de trabajar de la Comisión para seguimiento, evaluación y revisión del Plan de Igualdad de [COMPLETAR], en el tiempo que dure el proceso de diseño y durante la vigencia del mismo.

La función principal de esta Comisión será la de facilitar y garantizar la elaboración e implementación del Plan de Igualdad en [COMPLETAR], basado en un diagnóstico previo de la situación de la empresa y a partir del cual se propondrán medidas encaminadas a conseguir la igualdad real en todos los ámbitos en que fuera necesario.

Artículo 4.- Funciones

Las funciones de la Comisión de seguimiento serán:

• Establecimiento de un plan de trabajo para la ejecución del plan de igualdad.
• Facilitar los datos necesarios desagregados por sexo para efectuar un seguimiento correcto de los objetivos, medidas e indicadores del plan:
- Proceso de selección y contratación
- Clasificación profesional
- Formación
- Promoción profesional
- Condiciones de trabajo, incluida la auditoría salarial entre mujeres y hombres
- Ejercicio corresponsable de los derechos de la vida personal, familiar y laboral
- Infrarrepresentación femenina
- Retribuciones
- Prevención del acoso sexual y por razón de sexo
- Uso no discriminatorio del lenguaje, la comunicación y la publicidad
- Prevención de la violencia de género
- Comunicación
• La Comisión será la encargada de velar por que se lleven a cabo las medidas acordadas en el Plan, los plazos y recursos para llevarlas a efecto, los responsables de hacerlo, así como los plazos para su evaluación.
• La Comisión será la encargada de la evaluación, el seguimiento y el control de la aplicación de las medidas contempladas en dicho plan.
• La Comisión será la encargada de gestionar las dudas o cuestiones que surjan de la plantilla con el fin de facilitar la comunicación en lo que al Plan de Igualdad se refiere.

Artículo 5.- Procedimiento para solventar discrepancias

Las posibles discrepancias que pudieran surgir en la aplicación, seguimiento, evaluación o revisión, se resolverán en reuniones extraordinarias u ordinarias de la comisión dejando reflejadas las discrepancias en su debida acta.

En el caso en que las discrepancias no se resolvieran después de 3 reuniones, se propondrá la opción de establecer un mediador externo a la organización y representantes o acudir a un organismo conciliador.

Si tras la propuesta de mediación no se aceptase, o la mediación no llegase a un acuerdo, se podrá recurrir a la vía judicial en el órgano competente para ello.

Artículo 6.- Reuniones

Tras la implantación del Plan para su seguimiento, evaluación y revisión, la Comisión se reunirá con una periodicidad SEMESTRAL para su seguimiento y consecución.

Las horas de reunión no se asemejan como horas sindicales.

Artículo 7.- Actas

De cada reunión se levantará un acta, firmada por todas las personas que integran la Comisión, y en la que se hará constar el resumen de los temas tratados, acuerdos y desacuerdos.

Artículo 8.- Confidencialidad

Todas las personas componentes de la Comisión se comprometen a tratar con confidencialidad la información, datos, documentos, y/o cualquier otra información de la que se hiciera uso en el seno de la misma o les fuera entregada.

En [LUGAR], a [FECHA].

Por parte de la empresa

Por parte de la empresa

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

Por parte de los trabajadores

Por parte de los trabajadores

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
