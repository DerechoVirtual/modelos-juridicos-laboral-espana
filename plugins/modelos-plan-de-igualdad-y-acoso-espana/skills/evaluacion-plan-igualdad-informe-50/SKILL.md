---
name: evaluacion-plan-igualdad-informe-50
description: "Redacta el escrito «Evaluación del Plan de Igualdad: informe» (formulario 50 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Evaluación del Plan de Igualdad: informe

> Formulario 0050 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

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

- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ece el art. 9 RD 901/2020. Razón social:»; «…Fecha del informe:»; «…Periodo de análisis:»; «…Adecuación de los recursos asignados:»; «…cución: Soluciones adoptadas en su caso:»

## Elecciones que hay que hacer

- INTERMEDIA / FINAL
- Bajo / Medio / Alto

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 9 RD 901/2020

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

### Formulario 0050 · Evaluación del Plan de Igualdad: informe

- Año del modelo: —
- Revisión 17-11-2026: 18 desplegables y casillas convertidos en elección en blanco; 5 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

EVALUACIÓN [ELEGIR: INTERMEDIA / FINAL]

Información de resultados para cada área de actuación
Información sobre el proceso de implantación
Información sobre impacto
Conclusiones y propuestas

La comisión de seguimiento es la encargada de elaborar los informes correspondientes a las evaluaciones intermedias y final (o

cualesquiera otras que se establezcan) a partir de la información y los datos recopilados a lo largo del periodo correspondiente, tal como establece el art. 9 RD 901/2020.

Razón social: [COMPLETAR]

Fecha del informe: [COMPLETAR]

Periodo de análisis: [COMPLETAR]

Información de resultados para cada área de actuación

Grado de cumplimiento de objetivos definidos en el Plan de Igualdad: [ELEGIR: Bajo / Medio / Alto]

Nivel de realización de las medidas previstas en el Plan de Igualdad: [ELEGIR: Bajo / Medio / Alto]

Nivel de obtención de resultados esperados: [ELEGIR: Bajo / Medio / Alto]

Grado de cumplimiento de objetivos de cada medida según indicadores marcados en el Plan de Igualdad: [ELEGIR: Bajo / Medio / Alto]

Grado de medidas de nuevas necesidades detectadas: [ELEGIR: Bajo / Medio / Alto]

Nivel de corrección de las desigualdades detectadas en el diagnóstico: [ELEGIR: Bajo / Medio / Alto]

Situación del nivel de compromiso de la empresa con la igualdad: [ELEGIR: Bajo / Medio / Alto]

Información sobre la implementación de medidas a partir de los datos de las fichas de seguimiento de medidas:

Resumen de datos relativos al nivel de ejecución, cumplimiento de planificación, consecución de objetivos:

Conclusiones obtenidas de la explotación de datos e información de los cuestionarios cumplimentados por la comisión de seguimiento, la dirección y la plantilla:

Valoración general del periodo de referencia:

Información sobre el proceso de implantación

Nivel de desarrollo de las medidas: [ELEGIR: Bajo / Medio / Alto]

Grado de implicación de la plantilla en el proceso: [ELEGIR: Bajo / Medio / Alto]

El presupuesto previsto ha sido: [ELEGIR: Bajo / Medio / Alto]

El cumplimiento del calendario previsto ha sido: [ELEGIR: Bajo / Medio / Alto]

Adecuación de los recursos asignados: [COMPLETAR]

Dificultades, obstáculos o resistencias encontradas en la ejecución:

Soluciones adoptadas en su caso: [COMPLETAR]

Información sobre impacto

¿Se han producido cambios en la cultura de la empresa?: [ELEGIR: Bajo / Medio / Alto]

¿Se han reducido los desequilibrios de presencia de las mujeres?: [ELEGIR: Bajo / Medio / Alto]

¿Se han reducido los desequilibrios de presencia de los hombres?: [ELEGIR: Bajo / Medio / Alto]

¿Ha habido cambios en las actitudes y opiniones del equipo directivo?: [ELEGIR: Bajo / Medio / Alto]

¿Ha habido cambios en las actitudes y opiniones de la plantilla?: [ELEGIR: Bajo / Medio / Alto]

¿Se han detectado cambios en relación con la imagen externa de la empresa?: [ELEGIR: Bajo / Medio / Alto]

Señalar en qué han consistido los cambios tanto en relación con las personas como en la gestión y clima empresarial:

Conclusiones y propuestas

Incluir una valoración general del periodo de referencia sobre el desarrollo del plan de igualdad:

Definir propuestas de mejora o corrección de desviaciones detectadas tanto de aplicación inmediata como a futuro cuando se produzca la actualización del plan de igualdad:

════════════════════════════════════════════════════════════════════════
