---
name: cambio-jornada-completa-parcial-reves-acuerdo-236
description: "Redacta el escrito «Cambio de jornada completa a parcial o al revés: acuerdo» (formulario 236 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Cambio de jornada completa a parcial o al revés: acuerdo

> Formulario 0236 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD (2 veces)
- [ ] NIF
- [ ] DNI/NIE
- [ ] FECHA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…sustancial de condiciones de trabajo. En»; «…, en su calidad de»; «… y fecha al inicio consignados. Firmado:»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Para pasar de contrato a tiempo completo a contrato a tiempo parcial / Para pasar de contrato a tiempo parcial a contrato a tiempo completo — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Para pasar de contrato a tiempo completo a contrato a tiempo parcial / Para pasar de contrato a tiempo parcial a contrato a tiempo completo — el texto de cada opción no venía en el formulario original

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

### Formulario 0236 · Cambio de jornada completa a parcial o al revés: acuerdo

- Año del modelo: 2019
- Revisión 17-11-2026: 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 15 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
ANTECEDENTES
CLÁUSULAS
Firmas

La conversión de un trabajo a tiempo completo en un trabajo parcial, y viceversa, tendrá siempre carácter voluntario para el trabajador y no se podrá imponer de forma unilateral o como consecuencia de una modificación sustancial de condiciones de trabajo.

En [COMPLETAR]

REUNIDOS

De una parte,

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, actuando en representación de [NOMBRE DEL REPRESENTADO/A], en su calidad de [COMPLETAR], con domicilio en [LOCALIDAD] y NIF [NIF], en adelante la Empresa.

Y de otra,

D./Dña. [NOMBRE Y APELLIDOS] mayor de edad, con domicilio en [LOCALIDAD], provisto/a de DNI [DNI/NIE], en adelante, el/la Trabajador/a.

Ambas partes se reconocen, el primero en la representación que ostenta y el segundo en su propio nombre y derecho, mutua y plena capacidad para otorgar el presente documento de ACUERDO DE MODIFICACIÓN INDIVIDUAL DEL CONTRATO DE TRABAJO, en base a las siguientes:

ANTECEDENTES

I.- Las partes tienen suscrito un contrato de trabajo, de fecha [FECHA], de carácter indefinido, contrato que al día de hoy está vigente.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Para pasar de contrato a tiempo completo a contrato a tiempo parcial / Para pasar de contrato a tiempo parcial a contrato a tiempo completo — el texto de cada opción no venía en el formulario original]

III.- El trabajador está percibiendo actualmente un salario fijo bruto anual de [IMPORTE] euros brutos anuales, incluidos todos los conceptos.

IV.- Las partes han convenido modificar el contrato referido conforme a las siguientes:

CLÁUSULAS

[ELEGIR UNA OPCIÓN Y REDACTARLA: Para pasar de contrato a tiempo completo a contrato a tiempo parcial / Para pasar de contrato a tiempo parcial a contrato a tiempo completo — el texto de cada opción no venía en el formulario original]

SEGUNDA.- Como consecuencia del cambio de jornada, el salario bruto anual del Trabajador será de [IMPORTE] euros brutos anuales, incluidos todos los conceptos.

TERCERA.- El presente documento se adjuntará al contrato de trabajo celebrado entre las partes en fecha [FECHA], que quedará modificado conforme a lo así pactado, manteniéndose el resto de condiciones laborales actuales del Trabajador.

Y para que conste, firman el presente documento, por duplicado, en el lugar y fecha al inicio consignados.

Firmado: [COMPLETAR]

Empresa	Trabajador/a
D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
