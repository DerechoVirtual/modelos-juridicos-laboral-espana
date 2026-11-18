---
name: falso-autonomo-papeleta-conciliacion-previa-smac-181
description: "Redacta el escrito «Falso autónomo: papeleta de conciliación previa en el SMAC» (formulario 181 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Falso autónomo: papeleta de conciliación previa en el SMAC

> Formulario 0181 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Papeleta: a los quince días hábiles sin celebrarse se reanuda la caducidad; a los treinta días hábiles se tiene por terminado y cumplido el trámite (art. 65.1 y 65.2 LRJS, LO 1/2025). El MASC de la LO 1/2025 no se aplica en lo laboral (art. 3.2).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] NÚMERO
- [ ] TELÉFONO
- [ ] CORREO ELECTRÓNICO
- [ ] NIF
- [ ] FECHA (4 veces)
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 6 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…E MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE»; «…E MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE»; «…con domicilio a estos efectos en»; «…IA DE RELACIÓN LABORAL contra la empresa»; «…con NIF número [NIF] domiciliada en»; «…e la empresa demandada a la actividad de»

## Elecciones que hay que hacer

- DNI / NIE / Pasaporte

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 63 LRJS
- artículo 83 ET
- art. 65.1 LRJS
- Ley Orgánica 1/2025

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

### Formulario 0181 · Falso autónomo: papeleta de conciliación previa en el SMAC

- Año del modelo: 2020
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 bloques de alternativas señalados; 17 campos de relleno marcados en blanco
- Avisos de la revisión: Papeleta: a los quince días hábiles sin celebrarse se reanuda la caducidad; a los treinta días hábiles se tiene por terminado y cumplido el trámite (art. 65.1 y 65.2 LRJS, LO 1/2025). El MASC de la LO 1/2025 no se aplica en lo laboral (art. 3.2).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE [COMPLETAR]
HECHOS
Firmas

Las reclamaciones judiciales al empresario requieren, de conformidad con el art. 63 LRJS, el intento de conciliación previa o, en su caso, de mediación ante el servicio administrativo correspondiente o ante el órgano que asuma estas funciones, que podrá constituirse mediante los acuerdos interprofesionales o los convenios colectivos a los que se refiere el artículo 83 ET, así como mediante los acuerdos de interés profesional a los que se refiere la Ley del Estatuto del Trabajo Autónomo.

La presentación de la solicitud de conciliación o de mediación interrumpirá la prescripción o suspenderá la caducidad de acciones desde la fecha de dicha presentación, reiniciándose o reanudándose respectivamente el cómputo de los plazos al día siguiente de intentada la conciliación o mediación o transcurridos quince días hábiles desde su presentación sin que se haya celebrado. (art. 65.1 LRJS)

La papeleta de conciliación ante el Servicio de Mediación, Arbitraje y Conciliación (SMAC) se podrá presentar telemáticamente a través de las oficinas virtuales o sedes electrónicas de las correspondientes Comunidades Autónomas. Cuando se presenta de esta forma se cumplimenta en línea el impreso de solicitud al que se puede anexa cualquier documentación complementaria, entre la que se recomienda adjuntar la papeleta de conciliación redactada con detalle.

Actualizado según las modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN DE [COMPLETAR]

D./Dña. [NOMBRE Y APELLIDOS] con domicilio a estos efectos en [COMPLETAR] provisto de [ELEGIR: DNI / NIE / Pasaporte] número [NÚMERO], teléfono [TELÉFONO], correo electrónico [CORREO ELECTRÓNICO], ante este Organismo comparezco y, como mejor proceda en Derecho, DIGO:

Que por medio del presente escrito formulo PAPELETA DE CONCILIACIÓN en RECLAMACIÓN DE RECONOCIMIENTO DE EXISTENCIA DE RELACIÓN LABORAL contra la empresa [COMPLETAR] con NIF número [NIF] domiciliada en [COMPLETAR] en la persona de su representante legal.

La presente papeleta tiene su base en los siguientes:

HECHOS

PRIMERO.- Que he venido prestando servicios en la aludida empresa desde el día [FECHA] con un salario bruto de [LOCALIDAD], dedicándose la empresa demandada a la actividad de [COMPLETAR].

Durante todos estos años he venido desempeñando siguientes funciones:

SEGUNDO.- Que desempeño todas las funciones dentro del círculo rector y organicista de la empleadora, recibiendo instrucciones sobre cómo debo desempeñar mi trabajo y realizando informes sobre el desarrollo de este con carácter periódico y siempre que mis superiores me los solicitan.

TERCERO.- Que dicha relación, en la cual se dan las notas de dependencia y ajenidad, ha sido fraudulentamente estructurada como si de una por cuenta propia se tratara, habiéndome obligado la empresa a darme de alta en el Régimen Especial de Trabajadores Autónomos.

CUARTO.- Que, tras reiteradas solicitudes por mi parte para que se regularizara mi situación,

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

la empresa me remitió una propuesta de contrato de trabajo en fecha [FECHA] sin que hasta la fecha se me haya dado de alta en el Régimen General de la Seguridad Social, lo que motiva la interposición de esta papeleta.

la empresa no ha accedido a darme de alta en el Régimen General de la Seguridad Social.

En su virtud,

SUPLICO AL SERVICIO DE MEDIACIÓN, ARBITRAJE Y CONCILIACIÓN que, teniendo por presentado este escrito junto con sus copias, se sirva admitirlos, por realizadas las manifestaciones en él contenidas y, en méritos del mismo, se tenga por formulada PAPELETA DE CONCILIACIÓN en RECLAMACIÓN DE RECONOCIMIENTO DE EXISTENCIA DE RELACIÓN LABORAL, por la que se proceda a señalar día y hora, previa citación de las partes, para la celebración del oportuno acto de conciliación en el que la empresa se avenga a reconocer la existencia de dicha relación desde el día [FECHA] con los efectos legales inherentes a dicho reconocimiento.

Por ser de Justicia que pido en [LUGAR], a [FECHA].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
