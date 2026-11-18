---
name: registro-contratos-puesta-disposicion-cpd-386
description: "Redacta el escrito «Registro de contratos de puesta a disposición (CPD)» (formulario 386 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Registro de contratos de puesta a disposición (CPD)

> Formulario 0386 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- NO VERIFICADO: la Orden TES/1324/2024, de 20 de noviembre, que se cita como norma de actualización, no se ha localizado en el BOE por su título; comprobar su referencia.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº (2 veces)
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…Trabajo Temporal Celebrados en el mes de»; «…de»; «…nta cotización S. Social (11 posiciones)»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto 417/2015

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

### Formulario 0386 · Registro de contratos de puesta a disposición (CPD)

- Año del modelo: 2015
- Revisión 17-11-2026: 6 campos de relleno marcados en blanco
- Avisos de la revisión: NO VERIFICADO: la Orden TES/1324/2024, de 20 de noviembre, que se cita como norma de actualización, no se ha localizado en el BOE por su título; comprobar su referencia.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Relación de contratos de puesta a disposición que las ETT están obligadas a remitir mensualmente por medios electrónicos al Registro de Empresas de Trabajo Temporal de la autoridad laboral competente..

Se cumplimentará una relación por cada centro de trabajo de la empresa de trabajo temporal. Esta relación se cumplimentará y enviará aun cuando la empresa no haya formalizado contratos de puesta a disposición en el período, indicando dicha circunstancia y anotando el valor cero en las columnas de tipos de contratos.

Formulario actualizado según la Orden TES/1324/2024, de 20 de noviembre, por la que se desarrolla el Real Decreto 417/2015, de 29 de mayo, por el que se aprueba el Reglamento de las Empresas de Trabajo Temporal

Celebrados en el mes de [COMPLETAR] de [COMPLETAR]

Identificación de la empresa de trabajo temporal
Nombre o razón social	Nº [Nº] de autorización

NIF

(9 posiciones)

Código cuenta cotización S. Social

(11 posiciones) [COMPLETAR]

Nº orden del centro

(máximo 3 posiciones)

	Nº [Nº] de personas trabajadoras puestas a disposición

Dirección del centro de trabajo
Identificación de la/s empresa/s usuaria/s
Nombre o razón social de la empresa usuaria	Actividad económica de la empresa usuaria

NIF

(9 posiciones)

Código cuenta cotización Seg. Social

(11 posiciones)

Número de contratos de puesta a disposición (CPD)

(indique en cada caso si el contrato de trabajo es Fijo Discontinuo) Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinuo)

	Descripción literal actividad	Código CNAE-2025			Total (Suma de los tipos de CPD: 1+2+3+4 +5)

Tipo 1

Circunstancias de la producción

(incremento ocasional e imprevisible de la actividad y oscilaciones que generan un desajuste temporal entre el empleo estable disponible y el que se requiere)

Tipo 2

Circunstancias de la producción

(situaciones ocasionales, previsibles y que tengan una duración reducida y delimitada)

Tipo 3

Sustitución de una persona trabajadora con derecho a reserva de puesto de trabajo, o para completar la jornada reducida de otra o para la cobertura durante un proceso de selección

Tipo 4

Para la obtención de práctica profesional

Tipo 5

De formación en alternancia

N.º CPD	FD Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinuo)	N.º CPD	FD Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinuo)	N.º CPD	FD Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinuo)	N.º CPD	FD Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinuo)	N.º CPD	FD Para marcar la casilla FD debe haber cumplimentado previamente el dato numérico de cada tipo de CPD e indicar en cada caso cuántos de ellos corresponden a personas trabajadoras con contrato fijo discontinu)o

TOTAL CONTRATOS DE PUESTA A DISPOSICIÓN

En [LUGAR], a [FECHA].

Firma y sello de la empresa

════════════════════════════════════════════════════════════════════════
