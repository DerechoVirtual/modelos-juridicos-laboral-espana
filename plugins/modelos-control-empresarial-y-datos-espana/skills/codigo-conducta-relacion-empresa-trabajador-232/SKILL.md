---
name: codigo-conducta-relacion-empresa-trabajador-232
description: "Redacta el escrito «Código de conducta en la relación empresa-trabajador» (formulario 232 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Código de conducta en la relación empresa-trabajador

> Formulario 0232 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

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

El formulario no tiene campos marcados: revisa el texto por si hay datos implícitos.

## Párrafos opcionales (23)

Inclúyelos solo si encajan en los hechos:

- Legislación aplicable…
- Acuerdos colectivos y contratos individuales…
- Comportamiento ético…
- Confianza y participación…
- Organización del trabajo…
- Movilidad funcional…
- Cambio de condiciones…
- Productividad y calidad…
- Directrices e instrucciones empresariales…
- Control económico y de gestión…
- Respeto a la dignidad…
- Reclutamiento interno y externo…
- Evaluación personal…
- Salarios…
- Suspensión y extinción de la relación laboral…
- Régimen disciplinario…
- Comunicación y participación…
- Formación y desarrollo…
- Seguridad y salud laboral…
- Confidencialidad…
- No concurrencia…
- Ventajas y obsequios…
- Instalaciones y medios…

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

### Formulario 0232 · Código de conducta en la relación empresa-trabajador

- Año del modelo: 2019
- Revisión 17-11-2026: 23 párrafos opcionales señalados

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MARCO GENERAL
DIRECCIÓN Y CONTROL DE LA ACTIVIDAD LABORAL
CRITERIOS APLICABLES A LA TOMA DE DECISIONES
ÁMBITOS ESPECIALES DE COLABORACIÓN
RELACIONES DEL TRABAJADOR CON TERCEROS
Firmas

Información a los trabajadores sobre el código de conducta de la empresa

1. MARCO GENERAL

[OPCIONAL — incluir si procede]

Legislación aplicable

La ley es la expresión colectiva de la virtud de la justicia. En una sociedad democrática el primer principio ético reside en el respeto a la letra y el espíritu de la ley.

La ley laboral se refiere tanto a derechos y deberes laborales básicos (igualdad, dignidad, intimidad, protección, ocupación efectiva, productividad, lealtad y buena fe, representación y negociación, etc.) como a las normas mínimas o de orden público de la relación laboral.

[OPCIONAL — incluir si procede]

Acuerdos colectivos y contratos individuales

Las condiciones concretas de trabajo se negocian de forma colectiva e individual que se formalizan en Convenios o Acuerdos colectivos y en Contratos individuales de trabajo. Ambas formas son necesarias y complementarias. Los acuerdos deben cumplirse en sus propios términos y en lo que resulte de su interpretación con arreglo a los principios de lealtad y buena fe. Deben respetarse asimismo las reglas establecidas para la denuncia de los acuerdos y para el cambio de condiciones.

[OPCIONAL — incluir si procede]

Comportamiento ético

A partir del respeto a las leyes y a los acuerdos es exigible a empresa y trabajadores un comportamiento ético en sus relaciones recíprocas. Esta exigencia debe hacerse efectiva no solo como principio de aceptación general sino como obligación de cumplimiento concreto cuya conculcación debe sancionarse efectivamente.

[OPCIONAL — incluir si procede]

Confianza y participación

La exigencia de modelo de conducta parte de una consideración y de una confianza recíproca que debe ser impulsada y mantenida como un valor necesario y que se apoya en una verdadera participación y responsabilización de la persona en el proyecto organizativo dirigido por la empresa.

2. DIRECCIÓN Y CONTROL DE LA ACTIVIDAD LABORAL

[OPCIONAL — incluir si procede]

Organización del trabajo

La organización de la actividad laboral (estructura, diseño del trabajo) es facultad de la dirección de la empresa, que, dentro del respeto a los necesarios criterios de eficacia y productividad, lo aplicará de manera tal que favorezca el desarrollo profesional y el trabajo en equipo.

[OPCIONAL — incluir si procede]

Movilidad funcional

La movilidad funcional, entendida como el cambio de contenidos de la función y prestaciones laborales básicas, que favorece la realización de distintas funciones y las posibilidades de promoción profesional, supone una mejora de la eficacia organizativa y de la empleabilidad laboral. Se desarrollará mediante la formación interna y una actitud general favorable.

[OPCIONAL — incluir si procede]

Cambio de condiciones

En entorno cambiante y sujeto a movimientos rápidos e imprevisibles la organización debe mantener una capacidad de adaptación importante como garantía de eficacia y como ventaja competitiva. El cambio (de lugar de trabajo, de tiempo de trabajo, de métodos de trabajo, de sistema de compensaciones) puede preverse, al menos en parte, en las normas aplicables a la relación laboral, pero en ocasiones surge repentinamente. La actitud favorable al cambio requiere una información adecuada y el mantenimiento de las garantías económicas y profesionales básicas de las personas.

[OPCIONAL — incluir si procede]

Productividad y calidad

El trabajador tiene la obligación de contribuir a la productividad y a la calidad en la empresa poniendo en la realización de su trabajo la debida diligencia, colaborando con el resto de la organización y de las personas con quien esté relacionado y aportando las ideas o sugerencias que considere adecuadas.

La empresa facilitará los medios necesarios para conseguir los objetivos de productividad y la calidad, tales como la mejora organizativa, la inversión tecnológica, la formación, etc. Asimismo la empresa velará por el cumplimiento de los objetivos y adoptará las medidas de corrección necesarias.

[OPCIONAL — incluir si procede]

Directrices e instrucciones empresariales

En el desarrollo de su función de dirección la empresa por medio de las personas designadas para ello emitirá directrices generales e instrucciones concretas relativas a los objetivos de la empresa, a los sistemas y procedimientos aplicables y a la forma de realización del trabajo. El trabajador está obligado al cumplimiento de las órdenes empresariales sin perjuicio de su denuncia en caso de que estime su ilicitud por ser contrarios a normas de obligado cumplimiento o por su manifiesta irregularidad.

[OPCIONAL — incluir si procede]

Control económico y de gestión

El trabajador observará todos los controles y auditorías relativos a activos y pasivos, ingresos y gastos, sistemas y procedimientos, establecidos por la empresa.

[OPCIONAL — incluir si procede]

Respeto a la dignidad

En todo caso, cuando sea necesario establecer un control o vigilancia especial para verificar el cumplimiento de las obligaciones laborales se guardará en su adopción y aplicación la consideración debida a la dignidad del trabajador.

3. CRITERIOS APLICABLES A LA TOMA DE DECISIONES

[OPCIONAL — incluir si procede]

Reclutamiento interno y externo

El personal de la empresa tendrá prioridad en la ocupación de vacantes o de puestos de nueva creación. Solo se recurrirá al reclutamiento externo en caso de no existir en el interior personal disponible e idóneo. En todo caso, se respetarán las prioridades de obligado cumplimiento de origen normativo (por ejemplo, las relativas a la reserva de puesto de los excedentes o a la prioridad de permanencia de los representantes legales de los trabajadores).

La empresa dará a conocer públicamente la existencia de vacante y las condiciones o criterios establecidos para el acceso a la misma con el fin de abrir el campo de oportunidades al mayor número de aspirantes.

En todo caso, los puestos de confianza de la empresa o que comporten mando se proveerán directamente por la empresa.

[OPCIONAL — incluir si procede]

Evaluación personal

La entrevista anual entre el responsable de la unidad y el colaborador es la base del plan personal de mejora y de carrera, porque en la misma se debe constatar la marcha del trabajo, medir lo alcanzado y establecer las medidas adecuadas para el futuro. La responsabilidad de realizar la evaluación corresponde al responsable y al colaborador, sin perjuicio de la utilización de ayudas externas y de los medios técnicos y procedimientos de control establecidos.

La entrevista de evaluación anual complementa, no sustituye al diálogo permanente entre el mando y el colaborador.

[OPCIONAL — incluir si procede]

Salarios

La empresa define la estrategia y el sistema salarial aplicando los criterios que siguen.

El nivel salarial debe ser al menos igual al del sector de actividad o profesional comparable. Para establecerlo se fijarán las referencias-clave de acuerdo con los baremos y estudios externos más adecuados. Las diferencias internas deben reflejar con equidad las distintas competencias profesionales de acuerdo con la organización y el nivel de formación, complejidad y responsabilidad ocupado. Asimismo, la parte variable del salario debe adaptarse a los objetivos y resultados alcanzados, tanto individuales como colectivos.

[OPCIONAL — incluir si procede]

Suspensión y extinción de la relación laboral

Para la empresa la estabilidad en el empleo es un valor que debe ser respetado. Sin embargo, estabilidad no significa la renuncia a la utilización de las modalidades legales de contratación de duración determinada o temporal, aplicándolas de acuerdo con su espíritu y finalidad. No significa, tampoco, la no adopción de decisiones individuales de separación en caso de incumplimientos graves. La estabilidad significa no recurrir directamente al recurso de reducción de costes mediante la suspensión o extinción contractual sin antes haber analizado el conjunto de medidas posibles en una perspectiva a medio y largo plazo.

En caso de regulación de empleo la empresa ofrecerá las medidas compensatorias o sustitutivas posibles en el marco de la situación general y aplicará criterios objetivos en la designación de las personas afectadas. Todo ello con estricto respeto a las normas vigentes e intentando alcanzar el acuerdo con la representación laboral.

[OPCIONAL — incluir si procede]

Régimen disciplinario

La dirección de la empresa, con estricto respeto a la normativa aplicable, aplicará el régimen disciplinario con criterios objetivos y de equidad y orientando su actuación a la defensa y promoción de los valores sociales y económicos de la empresa y de sus partícipes.

4. ÁMBITOS ESPECIALES DE COLABORACIÓN

[OPCIONAL — incluir si procede]

Comunicación y participación

La empresa debe mantener una comunicación permanente tanto individual como colectiva con sus trabajadores con la finalidad de informar sobre la evaluación de su trabajo y de sus perspectivas personales y de dar a conocer todos aquellos aspectos relativos a la empresa que deban ser conocidos para que su trabajo adquiera significado dentro del conjunto.

Asimismo el trabajador debe comunicar a la empresa por medio de su responsable directo sus opiniones respecto al trabajo y a su situación en la empresa y debe formular todas las consultas y quejas que considere oportunas. La dirección de la empresa responderá directamente a todas las peticiones planteadas en un plazo razonable.

Todo ello sin perjuicio de las competencias de la representación legal de los trabajadores que se respetarán íntegramente.

[OPCIONAL — incluir si procede]

Formación y desarrollo

La empresa reconoce el derecho de sus trabajadores a recibir formación profesional que facilite la puesta al día de su cualificación y la realización de otras funciones y tareas en caso de reorganización. El trabajador se compromete a realizar el esfuerzo adecuado para el buen aprovechamiento de los programas. En todo caso la formación requiere actitudes y compromisos recíprocos y una participación activa.

La empresa asimismo facilitará las acciones de desarrollo personal y profesional que los trabajadores deseen emprender y tendentes a la diversificación y mejora de las cualificaciones y de las posibilidades futuras.

[OPCIONAL — incluir si procede]

Seguridad y salud laboral

Con independencia del cumplimiento estricto de la normativa aplicable a esta materia, la empresa como tal y los trabajadores se esforzarán por elaborar las políticas y aplicar los medios de prevención más adecuados para conseguir un nivel óptimo de seguridad y salud laboral.

5. RELACIONES DEL TRABAJADOR CON TERCEROS

[OPCIONAL — incluir si procede]

Confidencialidad

El deber de lealtad aplicable a todo el comportamiento laboral tiene una especial aplicación en cuanto se refiere a la necesaria confidencialidad o reserva sobre los datos e informaciones conocidos con motivo del trabajo y cuya divulgación a terceros pueda causar un daño material o moral a la empresa. Este deber se exige de todos los trabajadores de la empresa de acuerdo con las circunstancias que concurren en cada uno.

[OPCIONAL — incluir si procede]

No concurrencia

Los trabajadores deben abstenerse de realizar por sí o por persona interpuesta, de forma temporal o por tiempo indefinido, por cuenta propia o ajena, cualquier gestión o trabajo para terceros que entre en competencia con la actividad de la empresa. Asimismo se abstendrán, en los términos que formalmente se pacten en cada caso, de realizar actividades concurrentes una vez finalizada la relación laboral en la empresa.

[OPCIONAL — incluir si procede]

Ventajas y obsequios

En las relaciones con autoridades, proveedores, clientes, o cualquier otra persona con la que se contacte en nombre de la empresa, no se realizarán ni recibirán directa ni indirectamente pagos, obsequios o ventajas con valor económico de cualquier tipo de naturaleza irregular.

[OPCIONAL — incluir si procede]

Instalaciones y medios

Las instalaciones y medios de la empresa sean materiales, organizativos o humanos, son para la adecuada realización del trabajo, sin que puedan utilizarse con otros fines, salvo las comunicaciones urgentes y necesarias por razones particulares o la autorización expresa en casos singulares.

Los activos materiales e inmateriales de la empresa no se utilizarán con ningún fin ilegal, ni a favor de grupos políticos u otras opciones de carácter partidista.

════════════════════════════════════════════════════════════════════════
