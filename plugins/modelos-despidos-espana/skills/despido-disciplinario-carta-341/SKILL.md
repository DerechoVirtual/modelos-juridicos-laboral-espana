---
name: despido-disciplinario-carta-341
description: "Redacta el escrito «Despido disciplinario: carta» (formulario 341 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido disciplinario: carta

> Formulario 0341 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Audiencia previa: el art. 55.1 ET no la exige con carácter general; la doctrina del TS (STS 1250/2024) que se invoca no se ha podido verificar con las fuentes del BOE.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA (4 veces)
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…personas que trabajan en la empresa. De:»; «…Para:»; «…onstituyen una falta grave y culpable de»; «…ores y el art. del Convenio Colectivo de»; «…cal de la sección sindical del sindicato»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- (En caso de que la persona trabajadora estuviese afiliado a un sindicato y al empresario le constase)…
- (En caso de que haya existido expediente contradictorio)…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 54.2 del Estatuto de los Trabajadores
- artículo 54 del Estatuto de los Trabajadores
- artículo 49.2 del Estatuto de los Trabajadores
- artículo 55.1 del Estatuto de los Trabajadores

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

### Formulario 0341 · Despido disciplinario: carta

- Año del modelo: 2017
- Revisión 17-11-2026: 2 bloques de alternativas señalados; 2 párrafos opcionales señalados; 8 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Audiencia previa: el art. 55.1 ET no la exige con carácter general; la doctrina del TS (STS 1250/2024) que se invoca no se ha podido verificar con las fuentes del BOE.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Carta de despido disciplinario dirigida por el empresario a la persona trabajadora por las causas contempladas en el artículo 54.2 del Estatuto de los Trabajadores:

- Faltas repetidas e injustificadas de asistencia o puntualidad al trabajo.

- Indisciplina o desobediencia en el trabajo.

- Ofensas verbales o físicas al empresario o a las personas que trabajan en la empresa o a los familiares que convivan con ellos.

- Transgresión de la buena fe contractual y abuso de confianza en el desempeño del trabajo.

- Disminución continuada y voluntaria en el rendimiento de trabajo normal o pactado.

- Embriaguez habitual o toxicomanía que repercuten negativamente en el trabajo.

- Acoso por razón de origen racial o étnico, religión o convicciones, discapacidad, edad u orientación sexual y el acoso sexual o por razón de sexo al empresario o a las personas que trabajan en la empresa.

De: [COMPLETAR]

Para: [COMPLETAR]

En [LUGAR], a [FECHA].

Con esta misma fecha, y

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

tras haber recibido su escrito de alegaciones en contestación a la comunicación de la empresa en el trámite de audiencia previa a su despido, que en nada desvirtúan los hechos imputados,

transcurrido el plazo concedido para presentar alegaciones en el trámite de audiencia previa a su despido sin que haya contestado al mismo,

la Dirección de esta empresa, una vez finalizado el trámite de audiencia previa iniciado mediante comunicación de fecha [FECHA] ha adoptado la decisión de proceder a su despido, en base al artículo 54 del Estatuto de los Trabajadores, por haber incurrido Ud. en

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Faltas repetidas e injustificadas de asistencia o puntualidad al trabajo)
— (Indisciplina o desobediencia en el trabajo)
— (Ofensas verbales o físicas al empresario o a las personas que trabajan en la empresa o a los familiares que convivan con ellos)
— (Transgresión de la buena fe contractual, así como el abuso de confianza en el desempeño del trabajo)
— (Disminución continuada y voluntaria en el rendimiento de trabajo normal o pactado)
— (La embriaguez habitual o toxicomanía si repercuten negativamente en el trabajo)
— (Acoso por razón de origen racial o étnico, religión o convicciones, discapacidad, edad u orientación sexual y el acoso sexual o por razón de sexo al empresario o a las personas que trabajan en la empresa)

Los hechos relatados constituyen una falta grave y culpable de [COMPLETAR] tipificada, como ya se ha dicho, en el art. 54.2. del Estatuto de los Trabajadores y el art. del Convenio Colectivo de [COMPLETAR], sancionable con el despido conforme al art. de la citada norma convencional, por lo que por medio de la presente procedemos a notificarle su despido disciplinario, que tendrá efectos a partir del día [FECHA], en que pondremos a su disposición en las oficinas de esta empresa la cantidad correspondiente en concepto de liquidación de haberes y finiquito hasta ese día, quedando extinguido el contrato que nos une, y a partir de la cual se abstendrá de acudir a la misma.

Conforme establece el artículo 49.2 del Estatuto de los Trabajadores, le adjuntamos propuesta detallada de la citada liquidación y finiquito y le advertimos que puede Ud. solicitar la presencia de un representante legal de los trabajadores al firmar el presente documento, en el cual, haga o no uso de su derecho, se hará constar uno u otro extremo expresamente.

[OPCIONAL — incluir si procede]

(En caso de que la persona trabajadora estuviese afiliado a un sindicato y al empresario le constase)

Asimismo y conforme establece el artículo 55.1 del Estatuto de los Trabajadores, le comunicamos que, en fecha [FECHA], la empresa procedió a dar audiencia al Delegado Sindical de la sección sindical del sindicato [COMPLETAR] a fin de que alegara lo que considerase oportuno, dada su condición de afiliado al mismo. Le adjuntamos copia de dicho trámite a efectos de su acreditación.

[OPCIONAL — incluir si procede]

(En caso de que haya existido expediente contradictorio)

Asimismo y conforme establece el artículo 55.1 del Estatuto de los Trabajadores, dada su condición de representante legal de los trabajadores, hacemos constar que la empresa procedió a abrir y tramitar expediente contradictorio, en el que fueron oídos Ud. mismo y los demás representantes de los trabajadores.

Le saluda atentamente,

La empresa

Recibí

	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
