---
name: contrato-patron-embarcaciones-recreo-378
description: "Redacta el escrito «Contrato de patrón de embarcaciones de recreo» (formulario 378 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato de patrón de embarcaciones de recreo

> Formulario 0378 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] LOCALIDAD (2 veces)
- [ ] NIF (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] FECHA (2 veces)
- [ ] Nº (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] Otros 14 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nales. REUNIDOS De una parte, la entidad»; «…A es titular de la embarcación de recreo»; «…de»; «… que opera desde el amarre del puerto de»; «…rtud de título expedido por el Organismo»; «…ias de su titulación para la embarcación»; «…ones propias de patrón de la embarcación»; «…. La duración del presente contrato será»; «…y estableciéndose un período de prueba»; «… por los siguientes conceptos salariales»; «…ración de las vacaciones anuales será de»; «…l período comprendido entre los meses de»; …

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- Como gratificaciones extraordinarias se pactan las siguientes:…
- El PATRÓN se obliga a contratar al personal de tripulación necesario por cuenta de la EMPRESA, a contratar los…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto 875/2014

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

### Formulario 0378 · Contrato de patrón de embarcaciones de recreo

- Año del modelo: 2016
- Revisión 17-11-2026: 2 párrafos opcionales señalados; 28 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
MANIFIESTAN
EXPONEN
ESTIPULACIONES
Firmas

Modelo para la contratación entre una empresa con embarcaciones y un patrón profesional de embarcaciones de recreo estableciendo el cumplimiento de los requisitos establecidos en el Real Decreto 875/2014 de 10 de octubre, por el que se regula las titulaciones náuticas para el gobierno de las embarcaciones de recreo.

Este documento ofrece un marco contractual detallado para la contratación de un patrón de embarcaciones de recreo, delineando las responsabilidades laborales y condiciones de trabajo asociadas. El contrato especifica elementos clave como la identificación de las partes, descripción exhaustiva de las funciones del patrón, así como las condiciones de empleo tales como la duración, salario, y beneficios adicionales.

REUNIDOS

De una parte, la entidad [COMPLETAR], con domicilio en [LOCALIDAD] y titular del NIF [NIF], representada en este acto por D./Dña. [NOMBRE Y APELLIDOS], Director General con apoderamiento de fecha [FECHA], en condición de EMPRESA,

Y de otra, D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con domicilio en [LOCALIDAD] y titular del NIF [NIF], en adelante el PATRÓN,

MANIFIESTAN

Que reconociéndose mutuamente las partes la capacidad legal necesaria a los efectos de este CONTRATO DE TRABAJO DE PATRÓN DE EMBARCACIONES DE RECREO, siendo responsables de la veracidad de sus manifestaciones, y de forma libre, espontánea y de mutuo acuerdo

EXPONEN

Que la EMPRESA es titular de la embarcación de recreo [COMPLETAR] de [COMPLETAR] metros de eslora, con pabellón y bandera española, que opera desde el amarre del puerto de [COMPLETAR] y cuya actividad es

Que el PATRÓN ostenta el título de patrón de yate con las facultades reconocidas en el Real Decreto 875/2014, de 10 de octubre, por el que se regulan las titulaciones náuticas para el gobierno de las embarcaciones de recreo, en virtud de título expedido por el Organismo [COMPLETAR], reuniendo los documentos y requisitos necesarios para el ejercicio profesional de esta función.

Que es deseo de ambas partes suscribir un contrato mediante el cual el PATRÓN se vincule laboralmente a la EMPRESA, a partir de la fecha que se indica, para el desempeño de las funciones propias de su titulación para la embarcación [COMPLETAR], pactando que el indicado contrato se regulará con arreglo a las siguientes.

ESTIPULACIONES

El objeto del contrato será la prestación por parte del PATRÓN por cuenta de la EMPRESA de las funciones propias de patrón de la embarcación [COMPLETAR], desarrollando todas aquellas labores directa e indirectamente relacionadas con el ejercicio de dicho cargo.

La duración del presente contrato será [COMPLETAR], iniciándose la relación el día [FECHA] y estableciéndose un período de prueba [COMPLETAR]

La jornada de trabajo será a tiempo completo, con una duración de [Nº] horas semanales, y con la siguiente distribución del tiempo de trabajo adaptada a las necesidades de la actividad

El PATRÓN percibirá una retribución total de [IMPORTE] euros brutos anuales, que se distribuirán por los siguientes conceptos salariales [COMPLETAR]

[OPCIONAL — incluir si procede]

Como gratificaciones extraordinarias se pactan las siguientes:

- Por día de pernocta en el barco por hallarse fuera de puerto o si los clientes se quedan a dormir, la cantidad de [IMPORTE] euros.
- Por excursiones contratadas directamente por el PATRÓN, se le abonará una gratificación adicional del 20% de su importe neto.
- ()

La duración de las vacaciones anuales será de [COMPLETAR], las cuales deberán disfrutarse en temporada baja, en el período comprendido entre los meses de [COMPLETAR] y de [COMPLETAR], o en los períodos de parada de la embarcación en puerto

La EMPRESA cumplirá las obligaciones fiscales y de Seguridad Social, y gestionará los trámites y documentos necesarios ante las autoridades administrativas y marítimas para inscribir al PATRÓN en el rol del barco.

[OPCIONAL — incluir si procede]

El PATRÓN se obliga a contratar al personal de tripulación necesario por cuenta de la EMPRESA, a contratar los suministros necesarios y a realizar las operaciones necesarias de mantenimiento y reparación de la embarcación para que se encuentre en perfecto estado de uso y conservación.

El contrato se suspenderá en el caso de que la embarcación deba estar en parada forzosa o dique seco por un tiempo superior a [Nº] meses.

El contrato se extinguirá en el caso de pérdida de vigencia, temporal o definitiva, del título del PATRÓN, o por la concurrencia de cualquier causa impeditiva para el ejercicio de la titulación, así como por las demás causas previstas legalmente.

En lo no previsto en este contrato se estará a lo previsto en la normativa laboral de aplicación.

El contenido del presente contrato se comunicará al Servicio Público de Empleo de [COMPLETAR] en el plazo de los diez días siguientes a su concertación.

En prueba de conformidad, una vez leído el contrato, ambas partes firman el presente documento a un solo efecto, en el lugar y fecha indicados en el encabezamiento.

LA EMPRESA

EL PATRÓN

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
