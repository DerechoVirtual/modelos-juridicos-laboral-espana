---
name: transaccion-sobre-despido-acuerdo-241
description: "Redacta el escrito «Transacción sobre el despido: acuerdo» (formulario 241 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Transacción sobre el despido: acuerdo

> Formulario 0241 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] NIF
- [ ] LOCALIDAD (2 veces)
- [ ] NÚMERO
- [ ] IMPORTE (2 veces)
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, en su condición de»; «…de la Empresa»; «…estando sus servicios profesionales como»; «…para la empresa»; «…, con una antigüedad reconocida del»; «…e Mediación, Arbitraje y Conciliación de»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

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

### Formulario 0241 · Transacción sobre el despido: acuerdo

- Año del modelo: 2019
- Revisión 17-11-2026: 1 bloques de alternativas señalados; 19 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
EXPONEN
CLÁUSULAS
Firmas

Pacto entre empresario y persona trabajadora, posterior a un despido, mediante el cual se renuncia a acudir a los tribunales a cambio de una compensación económica

En [LUGAR], a [FECHA].

REUNIDOS

De una parte, D./Dña. [NOMBRE Y APELLIDOS], en su condición de [COMPLETAR] de la Empresa [COMPLETAR], con NIF nº [NIF], y domicilio en [LOCALIDAD], en adelante la Empresa.

Y de otra, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con D.N.I. nº [NÚMERO] y domicilio en [LOCALIDAD], en su propio nombre y derecho, en adelante la persona trabajadora.

Ambas partes, que se reconocen mutuamente la suficiente capacidad y legitimación para suscribir el presente documento y comprometer a las partes a las que representan,

EXPONEN

I.- Que D./Dña. [NOMBRE Y APELLIDOS] ha venido prestando sus servicios profesionales como [COMPLETAR] para la empresa [COMPLETAR], con una antigüedad reconocida del [COMPLETAR], percibiendo una retribución bruta anual por todos los conceptos de [IMPORTE] euros.

II.- Que la Empresa ha decidido despedir a la persona trabajadora por causas disciplinarias, con efectos desde el día [FECHA], en los términos y por las razones contenidas en la carta de despido notificada con esa misma fecha.

III.- Que la persona trabajadora expresa su disconformidad con el contenido de la carta de despido referida por entender que son inciertos los hechos que en ella se le imputan, anunciando su decisión de formular la oportuna reclamación judicial en defensa de sus intereses.

IV.- Que, en aras de no acudir a la vía judicial y llegar a un acuerdo, la Empresa realiza una propuesta de solución del conflicto judicial anunciado, y ambas partes firman el presente acuerdo en base a las siguientes

CLÁUSULAS

Primera.- Ofrecimiento empresarial

La Empresa reconoce la improcedencia del despido efectuado y ofrece a la persona trabajadora una indemnización por importe de [IMPORTE] euros netos.

Segunda.- Aceptación de la Oferta

La persona trabajadora acepta el ofrecimiento realizado y se muestra conforme con el importe de indemnización ofrecido por su despido improcedente.

Esta cantidad se ofrecerá por la Empresa y será aceptada por la persona trabajadora en el acto de conciliación celebrado ante el Servicio de Mediación, Arbitraje y Conciliación de [COMPLETAR] y se abonará:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Mediante transferencia bancaria en el plazo de 48 horas a la cuenta corriente en la que el Trabajador venía percibiendo su salario

Mediante la entrega de un cheque nominativo.

Tercera.- Liquidación de salarios y finiquito

En esta misma fecha la Empresa pone a disposición de la persona trabajadora la liquidación de salarios, vacaciones y parte proporcional de pagas extraordinarias devengadas y no cobradas al día de la fecha.

La persona trabajadora acepta dicha cantidad, con cuyo percibo efectivo y una vez celebrado el acto de conciliación se considera saldado y finiquitado por todos los conceptos que pudieran derivarse de la relación laboral mantenida, renunciando, en consecuencia a interponer todo tipo de reclamación contra la empresa por cualquier concepto y ante cualquier orden jurisdiccional y comprometiéndose a desistir de cualquier demanda planteada contra la empresa.

Y en prueba de conformidad con lo que antecede, se firma el presente documento por duplicado ejemplar en el lugar y fecha arriba indicados.

La empresa

La persona trabajadora

D./Dña. [NOMBRE Y APELLIDOS]	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
