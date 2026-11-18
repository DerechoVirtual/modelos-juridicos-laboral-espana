---
name: pedir-adaptacion-jornada-conciliacion-196
description: "Redacta el escrito «Pedir adaptación de jornada por conciliación» (formulario 196 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir adaptación de jornada por conciliación

> Formulario 0196 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA (3 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] DESCRIBIR
- [ ] Otros 10 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…persona trabajadora de esta empresa, con»; «…de»; «… así como el resto de normas aplicables,»; «…mi prestación de servicios se realiza en»; «…TERCERO.- En concreto solicito»; «…, y previendo una finalización»; «…cuanto a su organización, por cuanto que»; «…os que establezca la normativa laboral y»; «…. Por todo ello, Solicito»; «…udo. Atentamente, La persona trabajadora»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 34.8 ET
- art. 34.8 del Estatuto de los Trabajadores

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

### Formulario 0196 · Pedir adaptación de jornada por conciliación

- Año del modelo: 2020
- Revisión 17-11-2026: 16 campos de relleno marcados en blanco
- Avisos de la revisión: Adaptación del art. 34.8 ET: hasta que los hijos cumplan doce años, negociación de 15 días con presunción de concesión si no hay oposición motivada, y nulidad objetiva del despido o extinción por solicitarla o disfrutarla (arts. 53.4.b y 55.5.b, redacción LO 1/2025).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

LUGAR Y FECHA
EMPRESA
PERSONA TRABAJADORA
HECHOS
SOLICITO
Firmas

El art. 34.8 ET reconoce a las personas trabajadoras el derecho a solicitar adaptaciones de la duración y distribución de la jornada, de la ordenación del tiempo de trabajo y de la forma de prestación, incluida la prestación a distancia, para hacer efectivo el derecho a la conciliación de la vida familiar y laboral. La norma exige que tales adaptaciones sean razonables y proporcionadas en relación con las necesidades de la persona trabajadora y con las necesidades organizativas o productivas de la empresa.

Si no existe previsión convencional, la empresa, ante la solicitud de la persona trabajadora, debe abrir un proceso de negociación que ha de desarrollarse con la máxima celeridad y, en todo caso, dentro de un plazo máximo de quince días. Si en ese plazo no concurre oposición motivada expresa, la adaptación se presume concedida.

Finalizado el proceso, la empresa debe comunicar por escrito una de estas tres respuestas: aceptar la petición; formular una propuesta alternativa que haga posible las necesidades de conciliación; o denegar el ejercicio. Si propone una alternativa o deniega la solicitud, debe expresar las razones objetivas en que sustenta su decisión.

En [LUGAR], a [FECHA].

A la dirección de la empresa

D./Dña. [NOMBRE Y APELLIDOS], con DNI [DNI/NIE], persona trabajadora de esta empresa, con [COMPLETAR] de [COMPLETAR], en ejercicio del derecho concedido en el art. 34.8 del Estatuto de los Trabajadores, así como el resto de normas aplicables, [COMPLETAR] por medio del presente escrito solita adaptación de la jornada de trabajo para la conciliación de la vida laboral y familiar conforme a los siguientes:

HECHOS

PRIMERO.- Para hacer frente a mi situación personal actual, se requiere la reordenación de mi tiempo de trabajo, para poder conciliar mis obligaciones laborales y familiares, al tener que

SEGUNDO.- Actualmente, mi prestación de servicios se realiza en [COMPLETAR]

TERCERO.- En concreto solicito [COMPLETAR] consistente en [DESCRIBIR], comenzando el próximo día [FECHA], y previendo una finalización [COMPLETAR].

Adjunto como anexo a esta solicitud, documentos justificativos que acreditan la citada situación familiar y sus limitaciones para hacer efectivo mi derecho a conciliar mi vida laboral y familiar. Asimismo, pongo a disposición los documentos que a efectos probatorios fueran requeridos por la empresa, siempre teniendo en cuenta la observación por parte de la empresa de la normativa sobre protección de datos personales.

CUARTO.- La propuesta es razonable y proporcional entre mis necesidades de conciliar vida laboral y familiar y las de la empresa, que no se verá afectada especialmente en cuanto a su organización, por cuanto que [COMPLETAR].

Dada la necesidad y urgencia en la que me encuentro, ruego a la empresa que responda a esta solicitud en el plazo más breve posible y en los términos que establezca la normativa laboral y [COMPLETAR].

Por todo ello,

Solicito [COMPLETAR] con efectividad desde el día [FECHA].

Rogando acuse de recibo del presente documento, reciban un cordial saludo.

Atentamente,

La persona trabajadora [COMPLETAR]

Recibí,

La empresa

════════════════════════════════════════════════════════════════════════
