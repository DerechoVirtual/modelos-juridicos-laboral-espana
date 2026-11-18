---
name: sancion-ofensas-verbales-fisicas-carta-313
description: "Redacta el escrito «Sanción por ofensas verbales o físicas: carta» (formulario 313 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sanción por ofensas verbales o físicas: carta

> Formulario 0313 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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

- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…sional, o a persona ajena a la empresa A»; «…. Muy Sr./a mío/a:»; «… establecido en el Convenio colectivo de»; «…de»; «…ada en el art. del Convenio colectivo de»; «…, con la sanción de»

## Elecciones que hay que hacer

- las palabras por Ud. utilizadas / los acometimientos, ataques físicos y palabras por Ud. utilizados
- leve / grave / muy grave

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si las ofensas son verbales / Si las ofensas son físicas / — y además elegir: Si el ofendido es el empleador / Si el ofendido es empleado de superior grupo profesional o directivo / Si el ofendido es empleado de igual o similar grupo profesional / Si el ofendido es empleado de inferior grupo profesional / Si el ofendido es persona ajena a la empresa, cliente o prove
- ELEGIR UNA OPCIÓN Y REDACTARLA: Infracción grave o muy grave si el trabajador es representante legal o sindical / Infracción muy grave de persona trabajadora no afiliada a un sindicato / Infracción muy grave de persona trabajadora afiliada a un sindicato — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- (Si se trata de una suspensión de empleo y sueldo)…
- (Si en Infracción grave o muy grave la persona trabajadora renuncia a la presencia o asistencia de un represen…
- (Si en la persona trabajadora no quiere firmar la recepción de la carta de sanción)…
- D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 20 del Estatuto de los Trabajadores
- Real Decreto Legislativo 2/2015

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

### Formulario 0313 · Sanción por ofensas verbales o físicas: carta

- Año del modelo: 2017
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 1 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 3 párrafos opcionales señalados; 11 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
Firmas

Modelo de carta por la que se comunica la imposición de sanción disciplinaria a trabajador, por la comisión de una falta leve, grave o muy grave por ofensas verbales o físicas en el trabajo por los siguientes motivos que puede seleccionar individualmente:

- Ofensas verbales al empresario o a familiar o pariente del empresario, a empleado de superior, igual o similar o inferior grupo profesional, o a persona ajena a la empresa

- Ofensas físicas al empresario o a familiar o pariente del empresario, a empleado de superior, igual o similar o inferior grupo profesional, o a persona ajena a la empresa

A [COMPLETAR].

Muy Sr./a mío/a: [COMPLETAR]

El régimen sancionador, como especificación de una parte del poder de dirección de la empresa a que se refiere el artículo 20 del Estatuto de los Trabajadores, Real Decreto Legislativo 2/2015, de 23 de octubre, persigue el mantenimiento de la disciplina laboral, en tanto aspecto universalmente considerado como fundamental para la normal convivencia, ordenación técnica y organización de toda empresa, así como para la garantía y defensa de los derechos e intereses legítimos tanto de ésta como de los propios trabajadores.

Esta empresa, en fecha [FECHA], ha entrado en conocimiento de la comisión por Ud. de una conducta, que más abajo se describirá detalladamente, que le obliga a tomar una medida disciplinaria conforme al régimen disciplinario establecido en el Convenio colectivo de [COMPLETAR] aplicable en la empresa.

En efecto, ha quedado acreditado que Ud. ha realizado la siguiente conducta y en las siguientes fechas, constituyendo la misma un incumplimiento contractual culpable:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si las ofensas son verbales / Si las ofensas son físicas / — y además elegir: Si el ofendido es el empleador / Si el ofendido es empleado de superior grupo profesional o directivo / Si el ofendido es empleado de igual o similar grupo profesional / Si el ofendido es empleado de inferior grupo profesional / Si el ofendido es persona ajena a la empresa, cliente o proveedor / Si el ofendido es familiar o pariente del empresario — el texto de cada opción no venía en el formulario original]

En el presente caso, dada la gravedad de [ELEGIR: las palabras por Ud. utilizadas / los acometimientos, ataques físicos y palabras por Ud. utilizados], de los insultos e imprecaciones que vertió, así como la falta de provocación bastante por parte de la persona ofendida para desencadenar su reacción y las demás circunstancias ya descritas, esta empresa se ve en la necesidad de calificar la falta laboral por Ud. cometida como de [ELEGIR: leve / grave / muy grave].

La indicada conducta es constitutiva de un incumplimiento por su parte de las obligaciones laborales derivadas de su contrato de trabajo y sancionable conforme a los arts. del Convenio colectivo de aplicación.

Vistos, por tanto, la indicada conducta acreditada y sus circunstancias, sus fechas de conocimiento por esta empresa y de comisión y los preceptos mencionados, esta empresa ha tomado la decisión de sancionarle a Ud., por la comisión de una falta [ELEGIR: leve / grave / muy grave] de [COMPLETAR], tipificada en el art. del Convenio colectivo de [COMPLETAR], con la sanción de [COMPLETAR] prevista en el art. del citado convenio.

[OPCIONAL — incluir si procede]

(Si se trata de una suspensión de empleo y sueldo)

Dicha sanción tendrá efectos a partir del día [FECHA] incluido.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Infracción grave o muy grave si el trabajador es representante legal o sindical / Infracción muy grave de persona trabajadora no afiliada a un sindicato / Infracción muy grave de persona trabajadora afiliada a un sindicato — el texto de cada opción no venía en el formulario original]

Rogándole que, a los exclusivos efectos de constancia de la recepción por Ud. de esta comunicación, firme un duplicado de la misma, le saluda atentamente.

Empresa

Recibí

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

(Si en Infracción grave o muy grave la persona trabajadora renuncia a la presencia o asistencia de un representante legal de los trabajadores)

Renuncio a la asistencia y/o presencia.

D./Dña. [NOMBRE Y APELLIDOS]

[OPCIONAL — incluir si procede]

(Si en la persona trabajadora no quiere firmar la recepción de la carta de sanción)

La persona trabajadora no quiere firmar la recepción de la carta de sanción, por lo que, a ruego de la empresa, firman, en calidad de testigos de ello,

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
