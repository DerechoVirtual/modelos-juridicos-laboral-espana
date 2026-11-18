---
name: impugnar-sancion-seguridad-social-empresario-demanda-345
description: "Redacta el escrito «Impugnar la sanción de Seguridad Social a un empresario: demanda» (formulario 345 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impugnar la sanción de Seguridad Social a un empresario: demanda

> Formulario 0345 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Art. 22.2 LISOS: una infracción por cada trabajador (art. 22.2) con multa de 3.750 a 12.000 € e incrementos del 20 al 50 % (art. 40.1.e). Comprobar el orden competente: actas de infracción vinculadas a actas de liquidación y actos sobre afiliación/alta van al contencioso (art. 3.f LRJS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (2 veces)
- [ ] FECHA (6 veces)
- [ ] ACTO O RESOLUCIÓN (2 veces)
- [ ] IMPORTE
- [ ] ÓRGANO
- [ ] LUGAR
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…y representación de la entidad mercantil»; «…tamente de la resolución que resuelve el»; «…esentar la documentación acreditativa de»; «… de Trabajo y Seguridad Social propuso y»; «…JS), BOE-A-2011-15936, arts. 2.s y 3.f.]»; «…, por considerar que»; «…guientes motivos que aquí se reproducen:»; «…en»

## Elecciones que hay que hacer

- mínimo / medio / máximo

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- arts. 151 y 152 LRJS
- artículo 22.2 del Real Decreto Legislativo 5/2000
- artículo 69.2 de la Ley 36/2011
- artículos 2 s), 6 y 10 de la Ley 36/2011

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

### Formulario 0345 · Impugnar la sanción de Seguridad Social a un empresario: demanda

- Año del modelo: 2013
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 1 desplegables y casillas convertidos en elección en blanco; 26 campos de relleno marcados en blanco
- Avisos de la revisión: Art. 22.2 LISOS: una infracción por cada trabajador (art. 22.2) con multa de 3.750 a 12.000 € e incrementos del 20 al 50 % (art. 40.1.e). Comprobar el orden competente: actas de infracción vinculadas a actas de liquidación y actos sobre afiliación/alta van al contencioso (art. 3.f LRJS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
Firmas

La Ley reguladora de la jurisdicción social faculta la impugnación de los actos de las Administraciones públicas, sujetos a Derecho administrativo y que pongan fin a la vía administrativa, dictadas en el ejercicio de sus potestades y funciones en materia de Seguridad Social.

En cuanto a su tramitación (y, en este caso concreto, agotada la vía administrativa tras un recurso de alzada), el artículo 69 de la citada LRJS expresa que el interesado podrá formalizar la demanda en el plazo de dos meses ante el Tribunal competente. A la demanda se acompañará copia de la resolución denegatoria o documento acreditativo de la interposición o resolución del recurso administrativo, según proceda, uniendo copia de todo ello para la entidad demandada.

El procedimiento se regirá por los principios y reglas del proceso ordinario laboral pero con las especialidades contenidas en los arts. 151 y 152 LRJS, que regulan la modalidad procesal denominada “procedimiento de impugnación de actos administrativos en materia laboral y de seguridad social no prestacionales”. En lo no expresamente previsto en dichos preceptos serán de aplicación supletoria las normas reguladoras de la jurisdicción contencioso-administrativa, en cuanto sean compatibles con los principios del proceso social.

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto/a de DNI número [DNI/NIE], actuando en nombre y representación de la entidad mercantil [COMPLETAR], conforme a la escritura de poder a mi favor otorgada ante el/la Notario/a de esta localidad, D./Dña. [NOMBRE Y APELLIDOS], cuya copia acompaña, con domicilio social en [LOCALIDAD], ante el Tribunal comparece y, DICE:

Que, por medio del presente escrito, viene a interponer DEMANDA DE IMPUGNACIÓN DE ACTO ADMINISTRATIVO EN MATERIA DE SEGURIDAD SOCIAL, en tiempo y forma y de conformidad con lo establecido en el artículo 151 de la Ley reguladora de la Jurisdicción Social, concretamente de la resolución que resuelve el [COMPLETAR] que confirma la sanción grave en materia de Seguridad Social de fecha [FECHA] contra [ACTO O RESOLUCIÓN] con domicilio en [LOCALIDAD].

Se basa la presente demanda en los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que, en fecha [FECHA] la empresa fue requerida por la Inspección de Trabajo y Seguridad Social para presentar la documentación acreditativa de [COMPLETAR].

SEGUNDO.- Presentada la documentación solicitada, la Inspección de Trabajo y Seguridad Social propuso y [COMPLETAR] dictó resolución imponiendo a la empresa una sanción de [IMPORTE] euros por infracción grave en materia de Seguridad Social, del artículo 22.2 del Real Decreto Legislativo 5/2000, de 4 de agosto, al considerar que [NOTA DE REVISIÓN: Art. 22.2: una infracción por cada trabajador afectado; multa de 3.750-7.500 / 7.501-9.600 / 9.601-12.000 € por infracción, con incrementos del 20 % al 50 % si hay de 2 a 5 o más trabajadores (art. 40.1.e). Si el acta de infracción va vinculada a un acta de liquidación, o se impugnan actos de afiliación/alta, el orden competente es el contencioso (art. 3.f LRJS). Fuente: RDLeg 5/2000 (LISOS), BOE-A-2000-15060, arts. 22.2 y 40.1.e; Ley 36/2011 (LRJS), BOE-A-2011-15936, arts. 2.s y 3.f.] [COMPLETAR].

La resolución indicada de fecha [FECHA], cuya copia se acompaña, imponía la sanción en su grado [ELEGIR: mínimo / medio / máximo], por considerar que [COMPLETAR].

TERCERO.- La empresa interpuso recurso de alzada contra la citada resolución ante [ÓRGANO], por no estar conforme la misma en base a los siguientes motivos que aquí se reproducen: [COMPLETAR].

CUARTO.- En fecha [FECHA] le fue notificada a la empresa que represento la resolución que ahora se impugna, desestimatoria del recurso interpuesto, limitándose a reproducir y confirmar los hechos y la sanción de la resolución inicial recurrida.

Resolución que agota la vía administrativa y que asimismo se acompaña.

QUINTO.- Se interpone la presente demanda dentro del plazo establecido en el artículo 69.2 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social, por no estar conforme con la sanción impuesta.

Lo expuesto se basa en los siguientes:

FUNDAMENTOS DE DERECHO

I.- Corresponde el conocimiento del presente asunto al Tribunal al que me dirijo por razón de la materia y el territorio en razón de lo dispuesto en los artículos 2 s), 6 y 10 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social.

II.- Se ha seguido el procedimiento y los plazos establecidos en los artículos 69 y 151 de la indicada Ley procesal.

III.- En cuanto al fondo del asunto, son de aplicación los artículo 22.2 del Real Decreto Legislativo 5/2000, de 4 de agosto.

Por lo expuesto,

SUPLICA AL TRIBUNAL DE INSTANCIA que, teniendo por presentado este escrito, con los documentos y copias que se acompañan, se sirva admitirlo y, en su virtud y en la representación que ostento, tenga por formulada demanda de IMPUGNACIÓN DE ACTO ADMINISTRATIVO EN MATERIA DE SEGURIDAD SOCIAL, concretamente de la resolución que le impone sanción grave en esa materia de fecha [FECHA], contra [ACTO O RESOLUCIÓN] y, previos los trámites legales oportunos, señale día y hora para el acto de conciliación y, en su caso, juicio, y dicte en su día sentencia por la que, estimando íntegramente las pretensiones expuestas en el cuerpo de este escrito, declare la nulidad y deje sin efecto la mencionada sanción, con las consecuencias derivadas de tal declaración, por no ser ciertos ni haber sido probados los hechos imputados a la empresa.

Todo ello por ser de Justicia que pide en [LUGAR], a [FECHA].

Fdo.: D./Dña. [NOMBRE Y APELLIDOS]

OTROSÍ DICE: Que, en este acto y en la representación que ostenta, designa el domicilio del/de la Letrado/a D./Dña [NOMBRE Y APELLIDOS] en [COMPLETAR], a efectos de notificaciones y demás diligencias.

Por lo que,

SUPLICA AL TRIBUNAL que tenga por hecha tal manifestación a los efectos oportunos, por ser de Justicia que en el mismo lugar y fecha pide.

════════════════════════════════════════════════════════════════════════
