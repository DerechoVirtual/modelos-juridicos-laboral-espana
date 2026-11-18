---
name: despido-causas-objetivas-carta-344
description: "Redacta el escrito «Despido por causas objetivas: carta» (formulario 344 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido por causas objetivas: carta

> Formulario 0344 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…sea representante de los trabajadores. A»; «…Muy Sr. mío/Sra. mía:»; «…de la liquidación de haberes y finiquito»

## Elecciones que hay que hacer

- sociales / de la entidad
- esta misma fecha / la fecha de extinción

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se respeta el plazo de preaviso / Si no se respeta el plazo de preaviso / — y además elegir: Por ineptitud sobrevenida / Por falta de adaptación de la persona trabajadora a las modificaciones técnicas operadas en su puesto de trabajo / Por causas económicas, técnicas, organizativas o de producción / — y además elegir: Si la empresa abona en ese momento la indemin
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si se respeta el plazo de preaviso / Si no se respeta el plazo de preaviso — el texto de cada opción no venía en el formulario original

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- En caso de que se trate de un representante legal de los trabajadores:…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 52 del Estatuto de los Trabajadores
- artículo 53.1.c) del Estatuto de los Trabajadores

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

### Formulario 0344 · Despido por causas objetivas: carta

- Año del modelo: 2017
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 párrafos opcionales señalados; 4 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Emisor
Receptor
Firmas

Carta de despido objetivo o extinción de contrato dirigida por el empresario a la persona trabajadora por la causa objetiva contemplada en el artículo 52 del Estatuto de los Trabajadores, esto es, por ineptitud de la persona trabajadora sobrevenida, por falta de adaptación a las modificaciones técnicas operadas en el puesto de trabajo, o por causas económicas, técnicas, organizativas o de producción.

Este modelo incluye opciones a seleccionar tanto si se ha respetado el plazo de preaviso como si no ha sido así, e incorpora también la opción de que la persona trabajadora cuyo contrato se extingue sea representante de los trabajadores.

A [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS]

Muy Sr. mío/Sra. mía: [COMPLETAR]

La Dirección de esta empresa ha tomado la decisión de extinguir el contrato de trabajo que nos une, con efectos desde:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se respeta el plazo de preaviso / Si no se respeta el plazo de preaviso / — y además elegir: Por ineptitud sobrevenida / Por falta de adaptación de la persona trabajadora a las modificaciones técnicas operadas en su puesto de trabajo / Por causas económicas, técnicas, organizativas o de producción / — y además elegir: Si la empresa abona en ese momento la indeminización / Si la empresa no puede abonar la indemnización en ese momento por causas económicas — el texto de cada opción no venía en el formulario original]

Asimismo se adjunta propuesta detallada de la liquidación de haberes y finiquito [COMPLETAR], cuya cuantía se pondrá a su disposición en los locales [ELEGIR: sociales / de la entidad] en [ELEGIR: esta misma fecha / la fecha de extinción], advirtiéndole que puede Ud. solicitar la presencia de un representante legal de los trabajadores al firmar su recibo, en el cual, haga o no uso de su derecho, se hará constar uno u otro extremo expresamente, conforme establece el artículo 49.2 del Estatuto de los trabajadores de aquella misma norma.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si se respeta el plazo de preaviso / Si no se respeta el plazo de preaviso — el texto de cada opción no venía en el formulario original]

[OPCIONAL — incluir si procede]

En caso de que se trate de un representante legal de los trabajadores:

De conformidad con lo establecido en el citado artículo 52.c) del Estatuto de los trabajadores, hemos tenido en cuenta la prioridad dada por su condición de representante de los trabajadores para tomar tal decisión, pero no existe homogeneidad de puestos de trabajo funcionalmente equivalentes al suyo entre los que hacer la comparación para aplicarla.

Del presente escrito se ha dado copia a los representantes legales de los trabajadores a los fines informativos establecidos en el mismo artículo 53.1.c) del Estatuto de los Trabajadores.

Rogándole firme la recepción de esta comunicación, le saluda atentamente,

La empresa

Recibí

	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
