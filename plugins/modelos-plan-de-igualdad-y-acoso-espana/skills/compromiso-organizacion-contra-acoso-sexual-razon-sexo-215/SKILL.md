---
name: compromiso-organizacion-contra-acoso-sexual-razon-sexo-215
description: "Redacta el escrito «Compromiso de la organización contra el acoso sexual y por razón de sexo» (formulario 215 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Compromiso de la organización contra el acoso sexual y por razón de sexo

> Formulario 0215 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] LUGAR
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… digital. De acuerdo con ese compromiso,»; «…ción de la organización y, por lo tanto,»; «…mpresas podrá extinguirse. Por lo tanto,»; «… consecución efectiva de este compromiso»; «…s personas que los sufren. Por su parte,»

## Párrafos opcionales (10)

Inclúyelos solo si encajan en los hechos:

- Diseño de un protocolo para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de…
- Difusión y distribución entre todas las personas trabajadoras del protocolo para la gestión de la prevención y…
- Realización de acciones formativas en materia de prevención del acoso sexual y del acoso por razón de sexo ent…
- Realización de campañas formativas, informativas y de sensibilización en materia de prevención del acoso sexua…
- Diseño y distribución de folletos informativos en materia de prevención del acoso sexual y del acoso por razón…
- Designación de una persona o equipo de personas, con formación específica en igualdad entre mujeres y hombres,…
- Establecimiento de un servicio de asesoramiento, apoyo y asistencia a las personas que puedan sufrir estos com…
- Inclusión de las medidas para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón …
- Realización de estudios de evaluación de riesgos psicosociales.…
- Evaluación y seguimiento, con carácter periódico, del desarrollo, funcionamiento y efectividad del protocolo p…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 48 Ley Orgánica 3/2007

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

### Formulario 0215 · Compromiso de la organización contra el acoso sexual y por razón de sexo

- Año del modelo: 2019
- Revisión 17-11-2026: 10 párrafos opcionales señalados; 8 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

La empresa debe adoptar una política activa frente el acoso sexual o por razón de género en su propia organización. Para ello es importante formalizar su compromiso de prevención y lucha contra el mismo.

 manifiesta su tolerancia cero ante la concurrencia en toda su organización de conductas contrarias a la libertad sexual y la integridad moral, especialmente en los casos de acoso sexual y/o acoso por razón de sexo, incluido el producido en el ámbito digital.

De acuerdo con ese compromiso, [COMPLETAR] quiere subrayar su compromiso con la prevención y actuación frente a estas conductas en cualquiera de sus manifestaciones, informando de la aplicación del "Protocolo para la prevención y actuación frente al acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el ámbito laboral" a todo el personal que presta servicios en su organización, sea personal propio o procedente de otras empresas, incluidas las personas que, no teniendo una relación laboral, prestan servicios o colaboran con la organización, tales como personas en formación, las que realizan prácticas no laborales o aquéllas que realizan voluntariado.

Cuando la presunta persona agresora quedara fuera del poder de dirección de la organización y, por lo tanto, [COMPLETAR] no pueda aplicar el procedimiento en su totalidad, se dirigirá a la empresa competente al objeto de que adopte las medidas oportunas y, en su caso, sancione a la persona responsable, advirtiéndole que, de no hacerlo, la relación mercantil que une a ambas empresas podrá extinguirse.

Por lo tanto, [COMPLETAR] se compromete a:

- No permitir ni tolerar bajo ningún concepto comportamientos, actitudes o situaciones de acoso sexual y acoso por razón de sexo.
- No ignorar las quejas, reclamaciones y denuncias de los casos de acoso sexual y acoso por razón de sexo que se puedan producir en la organización.
- Recibir y tramitar de forma rigurosa y rápida, así como con las debidas garantías de seguridad jurídica, confidencialidad, imparcialidad y derecho de defensa de las personas implicadas, todas las quejas, reclamaciones y denuncias que pudieran producirse.
- Garantizar que no se producirá ningún tipo de represalia ni contra las personas que formulen quejas, reclamaciones o denuncias, ni contra aquellas que participen en su proceso de resolución.
- Sancionar a las personas que acosen en función de las circunstancias y condicionamientos de su comportamiento o actitud.

Para la consecución efectiva de este compromiso [COMPLETAR] exige de todas y cada una de las personas que integran su organización, y en especial de aquellas que ocupan puestos directivos y de mandos intermedios, que asuman las siguientes responsabilidades:

- Tratar a todas las personas con las que se mantengan relaciones por motivos de trabajo (proveedores/as, clientela, personal colaborador externo, etc.) con respeto a su dignidad y a sus derechos fundamentales.
- Evitar comportamientos, actitudes o acciones que son o puedan ser ofensivas, humillantes, degradantes, molestas, intimidatorias u hostiles.
- Actuar adecuadamente frente a esos comportamientos, actitudes o acciones: no ignorándolos, no tolerándolos, manifestando su desacuerdo, impidiendo que se repitan o se agraven, comunicándolos a las personas designadas al efecto, así como prestando apoyo a las personas que los sufren.

Por su parte, [COMPLETAR] se compromete a establecer las siguientes medidas para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el trabajo:

[OPCIONAL — incluir si procede]

Diseño de un protocolo para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el trabajo.

[OPCIONAL — incluir si procede]

Difusión y distribución entre todas las personas trabajadoras del protocolo para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el trabajo.

[OPCIONAL — incluir si procede]

Realización de acciones formativas en materia de prevención del acoso sexual y del acoso por razón de sexo entre el personal directivo, mandos intermedios y personas designadas para la recepción, tramitación y resolución de las quejas, reclamaciones y denuncias.

[OPCIONAL — incluir si procede]

Realización de campañas formativas, informativas y de sensibilización en materia de prevención del acoso sexual y del acoso por razón de sexo a toda la plantilla de la entidad, así como al personal de nuevo ingreso.

[OPCIONAL — incluir si procede]

Diseño y distribución de folletos informativos en materia de prevención del acoso sexual y del acoso por razón de sexo, dando a conocer las vías de resolución de estas situaciones, tanto en el ámbito de la entidad, como fuera de la misma.

[OPCIONAL — incluir si procede]

Designación de una persona o equipo de personas, con formación específica en igualdad entre mujeres y hombres, prevención del acoso sexual y del acoso por razón de sexo y habilidades sociales para la recepción, tramitación y resolución de las quejas, reclamaciones y denuncias en esta materia.

[OPCIONAL — incluir si procede]

Establecimiento de un servicio de asesoramiento, apoyo y asistencia a las personas que puedan sufrir estos comportamientos, compuestos por personas con la formación y aptitudes necesarias para el desempeño de esa labor.

[OPCIONAL — incluir si procede]

Inclusión de las medidas para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el trabajo, en el plan de igualdad de la entidad.

[OPCIONAL — incluir si procede]

Realización de estudios de evaluación de riesgos psicosociales.

[OPCIONAL — incluir si procede]

Evaluación y seguimiento, con carácter periódico, del desarrollo, funcionamiento y efectividad del protocolo para la gestión de la prevención y erradicación del acoso sexual, el acoso por razón de sexo y otras conductas contrarias a la libertad sexual y la integridad moral en el trabajo.

En el desarrollo e implantación de las diferentes actuaciones y medidas recogidas en este compromiso de la entidad se contará con la participación y colaboración de la representación legal del personal de la organización, cumpliendo así con lo dispuesto en el art. 48 Ley Orgánica 3/2007.

En [LUGAR], a [FECHA].

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
