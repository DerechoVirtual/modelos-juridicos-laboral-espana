---
name: anunciar-recurso-suplicacion-367
description: "Redacta el escrito «Anunciar recurso de suplicación» (formulario 367 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Anunciar recurso de suplicación

> Formulario 0367 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Anuncio en cinco días (art. 194); depósito de 300 € y consignación o aval (arts. 229 y 230); exentos trabajadores, beneficiarios, sindicatos y justicia gratuita (art. 229.4); la entidad gestora acredita el abono de la prestación (art. 230.2.c).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NÚMERO
- [ ] SEDE
- [ ] Nº
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] COLEGIO
- [ ] Nº DE COLEGIADO/A
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD
- [ ] TELÉFONO
- [ ] Nº DE PROCEDIMIENTO
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] DESCRIBIR
- [ ] FECHA (3 veces)
- [ ] LUGAR

## Elecciones que hay que hacer

- demandante / demandado

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 190.1 LRJS
- art. 191.1 LRJS
- art. 194 LRJS
- art. 229 LRJS
- art. 230 LRJS

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

### Formulario 0367 · Anunciar recurso de suplicación

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 15 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Avisos de la revisión: Anuncio en cinco días (art. 194); depósito de 300 € y consignación o aval (arts. 229 y 230); exentos trabajadores, beneficiarios, sindicatos y justicia gratuita (art. 229.4); la entidad gestora acredita el abono de la prestación (art. 230.2.c).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Las Salas de lo Social de los Tribunales Superiores de Justicia conocerán de los recursos de suplicación que se interpongan contra las resoluciones dictadas por los Tribunales de Instancia de su circunscripción, así como contra los autos y sentencias que puedan dictar los Jueces de lo Mercantil que se encuentren en su circunscripción y que afecten al derecho laboral (art. 190.1 LRJS). Son recurribles en suplicación las sentencias que dicten los Tribunales de Instancia en los procesos que ante ellos se tramiten, cualquiera que sea la naturaleza del asunto, salvo cuando la Ley reguladora de la jurisdicción social disponga lo contrario (art. 191.1 LRJS).

El recurso objeto del formulario se debe anunciar dentro de los cinco días siguientes a la notificación de la sentencia, bastando para ello la mera manifestación de la parte o de su abogado, graduado social colegiado o de su representante, al hacerle la notificación de aquella, de su propósito de entablarlo. También puede anunciarse por comparecencia o por escrito de las partes o de su abogado o graduado social colegiado, o representante ante el Tribunal que dictó la resolución impugnada, dentro del indicado plazo (art. 194 LRJS).

Todo el que, sin tener la condición de persona trabajadora, causahabiente suyo o beneficiario del régimen público de la Seguridad Social, anuncie recurso de suplicación, consignará como depósito trescientos euros (art. 229 LRJS).

Cuando la sentencia impugnada hubiere condenado al pago de cantidad, será indispensable que el recurrente que no gozare del derecho de asistencia jurídica gratuita acredite, al anunciar el recurso de suplicación, haber consignado en la oportuna entidad de crédito y en la cuenta de depósitos y consignaciones abierta a nombre del órgano jurisdiccional, la cantidad objeto de la condena, pudiendo sustituirse la consignación en metálico por el aseguramiento mediante aval solidario de duración indefinida y pagadero a primer requerimiento emitido por entidad de crédito (art. 230 LRJS).

Procedimiento n.º [NÚMERO]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], Colegiado nº [Nº DE COLEGIADO/A], en nombre y representación de [NOMBRE DEL REPRESENTADO/A], según tengo acreditado en los autos de referencia, con domicilio en [LOCALIDAD], teléfono [TELÉFONO], correo electrónico [ELEGIR: demandante / demandado] en el procedimiento núm. [Nº DE PROCEDIMIENTO] que se sigue contra [ACTO O RESOLUCIÓN] sobre [DESCRIBIR], ante ese Tribunal de Instancia comparezco y como mejor proceda en Derecho, DIGO:

Que, el día [FECHA], se ha dictado sentencia en el número de procedimiento referenciado, a través de la cual se desestima la demanda interpuesta contra [ACTO O RESOLUCIÓN], habiendo sido notificada a esta parte el día [FECHA].

Que, por medio de este escrito y en el plazo legalmente conferido, vengo a anunciar el pertinente recurso de suplicación, toda vez que con el respeto que ese Tribunal me merece, considero que la sentencia perjudica y lesiona el derecho de esta parte.

Todo ello a tenor de lo establecido en los artículos 194 y siguientes de la Ley Reguladora de la Jurisdicción Social.

Por todo lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito con los documentos que se acompañan, tenga por anunciado en tiempo y forma recurso de suplicación contra la sentencia dictada en las actuaciones de referencia, y siguiéndose los trámites oportunos le haga entrega de los autos al/a la Letrado/a designado/a para su interposición dentro del plazo legalmente establecido.

OTROSI DIGO que, cumpliendo con lo preceptuado en los artículos 229 y 230 de la Ley reguladora de la jurisdicción social, se acompaña con el presente escrito el resguardo de haber efectuado la preceptiva consignación de la cantidad objeto de la condena impuesta en la sentencia, así como el correspondiente depósito.

SUPLICO AL TRIBUNAL, tenga por hecha la anterior manifestación a los efectos oportunos.

Es de Justicia que pido en [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
