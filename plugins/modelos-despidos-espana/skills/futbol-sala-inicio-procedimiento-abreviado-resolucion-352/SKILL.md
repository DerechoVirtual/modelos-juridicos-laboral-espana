---
name: futbol-sala-inicio-procedimiento-abreviado-resolucion-352
description: "Redacta el escrito «Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada» (formulario 352 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada

> Formulario 0352 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] FECHA
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…uscribió contrato de trabajo con el Club»; «…dor de fútbol sala para la/s temporada/s»; «…ptos que a continuación se relacionan: -»; «…-»; «…on el Club. Ello es justicia que pido en»; «…, a de»; «…, a de [COMPLETAR] Fdo.:»

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

### Formulario 0352 · Fútbol sala: inicio del procedimiento abreviado de resolución contractual anticipada

- Año del modelo: 2017
- Revisión 17-11-2026: 8 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Parte
DICE:
Firmas

A LA COMISIÓN MIXTA DEL CONVENIO PROCEDIMIENTO ABREVIADO DE RESOLUCIÓN CONTRACTUAL ANTICIPADA

Don [NOMBRE Y APELLIDOS], mayor de edad, con documento nacional de identidad número, y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], ante la Comisión Mixta comparece y, como mejor procede en Derecho,

DICE:

Primero. Con fecha [FECHA], el compareciente suscribió contrato de trabajo con el Club [COMPLETAR], como jugador de fútbol sala para la/s temporada/s [COMPLETAR] (Documento n.° 1).

Que en dicho contrato de trabajo se pactó el siguiente régimen de abono del salario fijo del compareciente.

- -Temporada /:

- -Temporada /:

Segundo. Que actualmente el Club denunciado adeuda al que suscribe, desde las fechas que se establecen, las cantidades por los conceptos que a continuación se relacionan:

- [COMPLETAR]

- [COMPLETAR]

La suma total de las cantidades adeudadas asciende a los referidos, los cuales se vienen a reclamar ante esa Comisión Mixta por medio de la presente denuncia.

Se adjunta al presente escrito la siguiente documentación justificativa de las obligaciones de pago incumplidas por el Club.

Tercero. Que esta parte, al amparo de lo establecido en el Convenio Colectivo AJFS-LNFS, se acoge libre y voluntariamente al procedimiento Abreviado de extinción contractual anticipada y formula la presente denuncia contra el citado Club o Sociedad Anónima Deportiva demandada, instando ante la Comisión Mixta la declaración de la terminación de la relación de trabajo por impago y el abono de las compensaciones previstas en dicho Acuerdo.

Cuarto. Que el compareciente, al acogerse al Procedimiento Abreviado de extinción contractual anticipada se somete a lo dispuesto en el mismo y abreviado declara:

a) Su voluntad inequívoca de someterse a la resolución que emita la Comisión Mixta respecto de la extinción contractual anticipada de su relación laboral con el Club que sea su empleador, aceptando las indemnizaciones y términos de las mismas que la Comisión Mixta establezca, en su caso, como consecuencia de la estimación de la terminación anticipada de la relación laboral renunciando a reclamar cantidades compensatorias por los mismos conceptos y con la misma naturaleza.

Suplico a La Comisión Mixta LNFS-AJFS, tenga por presentado este escrito, con los documentos que le acompañan, se sirva admitirlos y, previo los trámites reglamentarios oportunos, declare la resolución anticipada de la relación contractual que me vincula con el Club.

Ello es justicia que pido en [COMPLETAR], a de [COMPLETAR]

Fdo.: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
