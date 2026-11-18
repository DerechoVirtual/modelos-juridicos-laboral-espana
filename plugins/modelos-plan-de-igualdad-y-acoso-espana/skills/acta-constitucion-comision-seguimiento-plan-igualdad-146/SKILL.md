---
name: acta-constitucion-comision-seguimiento-plan-igualdad-146
description: "Redacta el escrito «Acta de constitución de la Comisión de seguimiento del plan de igualdad o plan LGTBI» (formulario 146 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Acta de constitución de la Comisión de seguimiento del plan de igualdad o plan LGTBI

> Formulario 0146 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- La «evaluación intermedia y otra final» es del art. 9.6 RD 901/2020 para el plan de igualdad; el art. 9 RD 1026/2024 remite la evaluación de las medidas LGTBI a convenio o acuerdo.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (8 veces)
- [ ] DNI/NIE (2 veces)
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…. Composición:»; «…en su calidad de»; «…. En representación de la plantilla:»; «…en su calidad de»; «…—»; «…de»; «…de»; «…de [COMPLETAR]. En»; «…de [COMPLETAR]. En [COMPLETAR]. Firmado:»

## Elecciones que hay que hacer

- empresa / organización
- de las personas trabajadoras / del personal funcionario y laboral
- Igualdad de efectiva entre mujeres y hombres / medidas para la igualdad y no discriminación de las personas LGTBI

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Seleccionar en caso de Plan de Igualdad efectiva entre mujeres y hombres / Seleccionar en caso de Plan de medidas para la igualdad y no discriminación de las personas LGTBI — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (5)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE].…
- D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE].…
- D./Dña. [NOMBRE Y APELLIDOS] en su calidad de [COMPLETAR].…
- D./Dña. [NOMBRE Y APELLIDOS] en su calidad de [COMPLETAR].…
- — [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 8.2.j) del RD 901/2020
- artículo 9 del RD 1026/2024

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

### Formulario 0146 · Acta de constitución de la Comisión de seguimiento del plan de igualdad o plan LGTBI

- Año del modelo: 2022
- Revisión 17-11-2026: 6 desplegables y casillas convertidos en elección en blanco; 4 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 párrafos opcionales señalados; 16 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: La «evaluación intermedia y otra final» es del art. 9.6 RD 901/2020 para el plan de igualdad; el art. 9 RD 1026/2024 remite la evaluación de las medidas LGTBI a convenio o acuerdo.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
ACUERDAN
Firmas

Según el artículo 8.2.j) del RD 901/2020 los Planes de Igualdad deberán contemplar la constitución de una comisión u órgano paritario encargado del seguimiento, evaluación y revisión periódica de los planes de igualdad. Esta comisión puede coincidir con la comisión negociadora del Plan o puede ser un órgano diferente.

Asimismo, también en el artículo 9 del RD 1026/2024 dentro de los Planes de las medidas para la igualdad y no discriminación de las personas LGTBI en las empresas se contempla su seguimiento, evaluación y revisión de las medidas planificadas.

REUNIDOS

De una parte, en representación de la [ELEGIR: empresa / organización]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE].

De otra parte, en representación [ELEGIR: de las personas trabajadoras / del personal funcionario y laboral]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE].

EXPONEN

[ELEGIR UNA OPCIÓN Y REDACTARLA: Seleccionar en caso de Plan de Igualdad efectiva entre mujeres y hombres / Seleccionar en caso de Plan de medidas para la igualdad y no discriminación de las personas LGTBI — el texto de cada opción no venía en el formulario original]

Todas las partes se reconocen mutuamente con la capacidad suficiente para obligarse en el presente acto y,

ACUERDAN

PRIMERO: Constituir la Comisión de evaluación y seguimiento del Plan que, con carácter general se ocupará de velar por el cumplimento de los compromisos adoptados en el Plan así como de revisar periódicamente el grado de implantación de las medidas acordadas.

La composición será paritaria entre la [ELEGIR: empresa / organización] y la representación legal [ELEGIR: de las personas trabajadoras / del personal funcionario y laboral].

Composición: [COMPLETAR]

En representación de la [ELEGIR: empresa / organización]:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] en su calidad de [COMPLETAR].

En representación de la plantilla: [COMPLETAR]

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS] en su calidad de [COMPLETAR].

SEGUNDO: Las partes negociadoras acuerdan que la Comisión tendrá las siguientes competencias:

— Revisión de las medidas del plan en cualquier momento con el fin de añadir, reorientar, mejorar, corregir, intensificar, atenuar o, incluso, dejar de aplicar alguna medida que contenga en función de los efectos que vayan apreciándose en relación con la consecución de sus objetivos.
— Revisión del Plan cuando concurran las siguientes circunstancias:
a) Cuando se ponga de manifiesto su falta de adecuación a los requisitos legales y reglamentarios o su insuficiencia como resultado de la actuación de la Inspección de Trabajo y Seguridad Social.
b) En los supuestos de fusión, absorción, transmisión o modificación del estatus jurídico de la empresa.
c) Ante cualquier incidencia que modifique de manera sustancial la plantilla de la empresa, sus métodos de trabajo, organización o sistemas retributivos, incluidas las inaplicaciones de convenio y las modificaciones sustanciales de condiciones de trabajo o las situaciones analizadas en el diagnóstico de situación que haya servido de base para su elaboración.
d) Cuando una resolución judicial condene a la organización por discriminación directa o indirecta por razón de sexo, de orientación e identidad sexual, de expresión de género o características sexuales de las personas LGTBI y sus familias, o cuando determine la falta de adecuación del plan a los requisitos legales o reglamentarios.
e) Cuando por circunstancias debidamente motivadas resulte necesario.
— Realización de al menos una evaluación intermedia y otra final.

[OPCIONAL — incluir si procede]

— [COMPLETAR].

TERCERO: Regirse por el Reglamento de funcionamiento de la Comisión de seguimiento y evaluación del Plan de [ELEGIR: Igualdad de efectiva entre mujeres y hombres / medidas para la igualdad y no discriminación de las personas LGTBI] de [COMPLETAR].

Queda aprobado por consenso la constitución de la Comisión de seguimiento y evaluación del Plan de [ELEGIR: Igualdad de efectiva entre mujeres y hombres / medidas para la igualdad y no discriminación de las personas LGTBI] de [COMPLETAR].

En [COMPLETAR].

Firmado: [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

Por parte de la organización	Por parte de la organización	Por parte de las personas trabajadoras	Por parte de las personas trabajadoras

════════════════════════════════════════════════════════════════════════
