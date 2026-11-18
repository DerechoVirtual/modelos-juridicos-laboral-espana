---
name: distribucion-irregular-jornada-acuerdo-representacion-234
description: "Redacta el escrito «Distribución irregular de la jornada: acuerdo con la representación» (formulario 234 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Distribución irregular de la jornada: acuerdo con la representación

> Formulario 0234 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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
- [ ] Nº (7 veces)
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de doce meses desde que se produzcan. En»; «…, en su calidad de»; «…de la Empresa»; «… por ello ACUERDAN I. Que durante el año»

## Elecciones que hay que hacer

- miembro/a del Comité de Empresa de / Delegado/a de personal de

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- D./Dña. [NOMBRE Y APELLIDOS]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 34.2 del ET

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

### Formulario 0234 · Distribución irregular de la jornada: acuerdo con la representación

- Año del modelo: 2019
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 16 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
ACUERDAN
Firmas

Acuerdo entre los representantes legales de los trabajadores y la empresa sobre distribución irregular de la jornada

En virtud de lo establecido en el art. 34.2 del ET, mediante convenio colectivo o, en su defecto, por acuerdo entre la empresa y los representantes de los trabajadores, se podrá establecer la distribución irregular de la jornada a lo largo del año. En defecto de pacto, la empresa podrá distribuir de manera irregular a lo largo del año el diez por ciento de la jornada de trabajo.

Dicha distribución deberá respetar en todo caso los periodos mínimos de descanso diario y semanal previstos en la ley y el trabajador deberá conocer con un preaviso mínimo de cinco días el día y la hora de la prestación de trabajo resultante de aquella.

La compensación de las diferencias, por exceso o por defecto, entre la jornada realizada y la duración máxima de la jornada ordinaria de trabajo legal o pactada será exigible según lo acordado en convenio colectivo o, a falta de previsión al respecto, por acuerdo entre la empresa y los representantes de los trabajadores. En defecto de pacto, las diferencias derivadas de la distribución irregular de la jornada deberán quedar compensadas en el plazo de doce meses desde que se produzcan.

En [COMPLETAR]

REUNIDOS

De una parte,

D./Dña. [NOMBRE Y APELLIDOS], en su calidad de [COMPLETAR] de la Empresa [COMPLETAR].

Y, de otra,

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

D./Dña. [NOMBRE Y APELLIDOS]

[NOMBRE Y APELLIDOS], en su condición de [ELEGIR: miembro/a del Comité de Empresa de / Delegado/a de personal de].

EXPONEN

Que el convenio colectivo de aplicación, establece una jornada máxima anual de [Nº] horas de trabajo efectivo.

Que el citado convenio colectivo no regula la distribución irregular de la jornada de trabajo, siendo el marco aplicable a la misma el establecido en el Estatuto de los trabajadores.

Que debido a las características de la actividad a la que se dedica la empresa y su organización del trabajo, ambas partes están interesadas en pactar una distribución irregular de la jornada de todas las personas trabajadoras de la plantilla que se adapte a las necesidades productivas y organizativas, y por ello

ACUERDAN

I. Que durante el año [COMPLETAR] la empresa podrá distribuir de forma irregular a lo largo del año el % de la jornada, esto es [Nº] horas.

II. La jornada diaria no podrá ser inferior a [Nº] horas ni superar las [Nº] horas. En cómputo semanal no podrá ser inferior a [Nº] horas ni superar [Nº] horas.

III. En cualquier caso, esta distribución irregular respetará los períodos mínimos de descanso diario (12 horas) y semanal (día y medio).

IV. La distribución irregular no podrá realizarse los sábados, domingos y festivos.

V. Con carácter general se comunicará a la representación legal de los trabajadores y a las personas trabajadoras afectadas con un preaviso mínimo de [Nº] días.

VI. La aplicación de la jornada irregular no implicará variación alguna en la forma de retribución ordinaria y cotizaciones de la persona trabajadora, abonándose, por tanto, los salarios, de igual manera que en el período de jornada regular.

VII. La compensación de las diferencias, por exceso o por defecto, entre la jornada realizada y la duración máxima de la jornada ordinaria de trabajo se realizará en el plazo de doce meses desde que se produzcan.

Y en prueba de conformidad ambas partes firman el presenta acuerdo en el lugar y fecha indicados en el encabezamiento.

Y en prueba de conformidad, firman el presente documento, por duplicado, en el lugar y fecha al inicio consignados.

Firmado: D./Dña. [NOMBRE Y APELLIDOS]

Firmado: D./Dña. [NOMBRE Y APELLIDOS]

Empresa	Comité de Empresa/Delegado/a de personal

════════════════════════════════════════════════════════════════════════
