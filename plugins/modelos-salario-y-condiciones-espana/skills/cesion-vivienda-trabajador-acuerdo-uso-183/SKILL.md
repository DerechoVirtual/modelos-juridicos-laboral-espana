---
name: cesion-vivienda-trabajador-acuerdo-uso-183
description: "Redacta el escrito «Cesión de vivienda al trabajador: acuerdo de uso» (formulario 183 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cesión de vivienda al trabajador: acuerdo de uso

> Formulario 0183 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

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
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NIF
- [ ] LOCALIDAD (3 veces)
- [ ] NÚMERO
- [ ] CALLE
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, en su condición de»; «…de la Empresa»; «…cios profesionales para la empresa desde»; «…como»; «…, incluido en el grupo profesional»; «…bajo sea el centro de trabajo ubicado en»; «… del uso de la vivienda serán a cargo de»

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

### Formulario 0183 · Cesión de vivienda al trabajador: acuerdo de uso

- Año del modelo: 2020
- Revisión 17-11-2026: 18 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
ESTIPULACIONES
Firmas

Acuerdo de cesión de uso de vivienda a la persona trabajadora por parte de la empresa como parte de su retribución en especie

En [LUGAR], a [FECHA].

REUNIDOS

De una parte,

D./Dña. [NOMBRE Y APELLIDOS], en su condición de [COMPLETAR] de la Empresa [COMPLETAR], con NIF nº [NIF], y domicilio en [LOCALIDAD], en adelante la Empresa.

Y de otra,

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con D.N.I. nº [NÚMERO] y domicilio en [LOCALIDAD], en su propio nombre y derecho, en adelante la persona trabajadora.

EXPONEN

I.- Que la persona trabajadora viene prestando sus servicios profesionales para la empresa desde [COMPLETAR] como [COMPLETAR], incluido en el grupo profesional [COMPLETAR].

II.- Que el lugar de prestación de los servicios es el centro de trabajo sito en [LOCALIDAD].

III.- Que la empresa es titular de una vivienda sita en la calle [CALLE].

IV.- Que es intención de la empresa ceder a la persona trabajadora, como contraprestación del puesto de trabajo que ocupa en la Compañía, el uso de dicha vivienda durante el tiempo de vigencia de la relación laboral, en base a las siguientes

ESTIPULACIONES

PRIMERA.- La empresa cede a la persona trabajadora el uso de la vivienda citada en el Exponendo III de este acuerdo, para su uso y el de su familia, de forma gratuita mientras esté vigente la relación laboral y el lugar de prestación del trabajo sea el centro de trabajo ubicado en [COMPLETAR].

SEGUNDA.- En caso de que, por cualquier causa, el centro de trabajo de la persona trabajadora cambie a otra provincia, cesará la cesión de uso que. En todo caso la cesión finalizará en el momento en que se extinga el contrato de trabajo.

En cualquiera de los casos la persona trabajadora tendrá que abandonar la vivienda en el plazo de un mes desde que se lo comunique la empresa.

TERCERA.- La persona trabajadora se compromete a conservar la vivienda en buen estado y a devolverla en el mismo estado en el que se le ha hecho entrega.

CUARTA.- Los gastos inherentes a la propiedad, incluidas cualquier tasa o impuesto, cuotas de la comunidad de propietarios y seguros de la casa, serán a cargo de la empresa. Los gastos originados como consecuencia de los suministros de electricidad, agua, gas, teléfono y cualesquiera otras derivados del uso de la vivienda serán a cargo de [COMPLETAR].

Y en prueba de conformidad de cuento exponen las partes firman el presente documento que se incorpora como anexo a su contrato de trabajo.

La Empresa

La persona trabajadora

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
