---
name: pedir-acumulacion-procesos-ante-mismo-distinto-tribunal-372
description: "Redacta el escrito «Pedir acumulación de procesos ante el mismo o distinto tribunal» (formulario 372 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir acumulación de procesos ante el mismo o distinto tribunal

> Formulario 0372 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- No existen «Tribunales de lo Social»: plazas de las Secciones de lo Social (art. 29 LRJS y LO 1/2025, DA 1.ª); la acumulación es obligatoria salvo perjuicio desproporcionado (art. 28.1, RDL 6/2023).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Nº DE PROCEDIMIENTO
- [ ] SEDE
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (3 veces)
- [ ] COLEGIO
- [ ] ACTO O RESOLUCIÓN
- [ ] FECHA (3 veces)
- [ ] NÚMERO (4 veces)
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…, en reclamación de»

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Procesos ante el mismo tribunal / Procesos ante distintos tribunales — el texto de cada opción no venía en el formulario original
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 28.1 LRJS
- art. 28.2 LRJS
- art. 29 LRJS
- art. 30.1 LRJS
- art. 30.2 LRJS

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

### Formulario 0372 · Pedir acumulación de procesos ante el mismo o distinto tribunal

- Año del modelo: 2016
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 16 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº DE PROCEDIMIENTO)
- Avisos de la revisión: No existen «Tribunales de lo Social»: plazas de las Secciones de lo Social (art. 29 LRJS y LO 1/2025, DA 1.ª); la acumulación es obligatoria salvo perjuicio desproporcionado (art. 28.1, RDL 6/2023).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Si en el mismo tribunal se tramitaran varias demandas contra un mismo demandado, aunque los actores sean distintos, y se ejercitasen en ellas acciones idénticas o susceptibles de haber sido acumuladas en una misma demanda, se acordará obligatoriamente la acumulación de los procesos, salvo cuando el tribunal aprecie, de forma motivada, que la acumulación podría ocasionar perjuicios desproporcionados a la tutela judicial efectiva del resto de intervinientes (art. 28.1 LRJS).

Cuando en materia de prestaciones de Seguridad Social o sobre recargo de prestaciones, se impugnare un mismo acto administrativo, o actos de reproducción, confirmación o ejecución de otro anterior, o actos entre los que exista conexión directa, se acordará la acumulación de los procesos aunque no coincidan todas las partes ni la posición procesal que ocupen. Dicha regla se aplicará a la impugnación de un mismo acto administrativo en las restantes materias competencia del orden social (art. 28.2 LRJS).

Si las demandas pendieran en distintos procesos ante dos o más Tribunales de lo Social de una misma circunscripción [NOTA DE REVISIÓN (comprobar): No existen «Tribunales de lo Social». El art. 29 LRJS habla de Juzgados de lo Social, hoy plazas de las Secciones de lo Social (LO 1/2025 DA 1.ª). Propuesta: «ante distintas plazas de las Secciones de lo Social de una misma circunscripción». Fuente: art. 29 LRJS (red. RDL 6/2023); LO 1/2025 DA 1.ª; LRJS (Ley 36/2011), BOE-A-2011-15936.], también se acordará obligatoriamente la acumulación de todas ellas, de oficio o a petición de parte. A tal efecto, las partes deberán comunicar esta circunstancia ante el tribunal que conociese de la demanda que hubiera tenido entrada antes en el Registro (art. 29 LRJS).

Se acordará también, de oficio o a instancia de parte, la acumulación de procesos que estuvieren pendientes en el mismo tribunal cuando entre los objetos de los procesos cuya acumulación se pretende exista tal conexión que, de seguirse por separado, pudieran dictarse sentencias con pronunciamientos o fundamentos contradictorios, incompatibles o mutuamente excluyentes (art. 30.1 LRJS).

Asimismo, se acumularán los procesos que tengan su origen en un mismo accidente de trabajo o enfermedad profesional, aunque no coincidan todas las partes o su posición procesal, salvo que hayan debido tramitarse mediante procedimientos administrativos separados, en cuyo caso solamente podrán acumularse las impugnaciones referidas a un mismo procedimiento (art. 30.2 LRJS).

Actualizado conforme a la nueva redacción de los artículos 28 y 29 dada por los apartados siete y ocho del artículo 104 del R.D.-ley 6/2023, de 19 de diciembre, por el que se aprueban medidas urgentes para la ejecución del Plan de Recuperación, Transformación y Resiliencia en materia de servicio público de justicia, función pública, régimen local y mecenazgo.

Procedimiento núm. [Nº DE PROCEDIMIENTO]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

D./Dña. [NOMBRE Y APELLIDOS], Letrado/a del Ilustre Colegio de Abogados de [COLEGIO], en nombre y representación de D./Dña. [NOMBRE Y APELLIDOS], cuyos demás datos ya constan en autos núm. promovidos por mi mandante contra [ACTO O RESOLUCIÓN], en reclamación de [COMPLETAR], ante esa Sección de lo Social del Tribunal de Instancia comparece y, como mejor proceda en Derecho, DICE:

Que en fecha [FECHA], se ha notificado a esta parte citación para los actos de conciliación y juicio, a celebrar el día [FECHA] a las [Nº] horas.

[ELEGIR UNA OPCIÓN Y REDACTARLA: Procesos ante el mismo tribunal / Procesos ante distintos tribunales — el texto de cada opción no venía en el formulario original]

es por lo que interesa a esta parte la acumulación de ambas actuaciones referenciadas, a fin de que en su día se dicte una única sentencia que resuelva los pedimentos de las dos demandas.

Que, conforme a lo establecido preceptivamente, la presente solicitud se formula ante el Juez que conoce de la demanda que ha tenido entrada anteriormente en el Registro.

En su virtud,

SUPLICO A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA que, habiendo por presentado este escrito con su copia en tiempo y forma legal, acuerde tener formulada la anterior petición, y previos los trámites legales oportunos, acuerde la acumulación

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

del proceso núm [NÚMERO] al núm [NÚMERO], seguidos ambos ante el Tribunal al que me dirijo,

al proceso núm [NÚMERO] seguido ante la Sección de lo Social del Tribunal de Instancia plaza núm [NÚMERO] de los de [LOCALIDAD] al presente proceso; y, en consecuencia, se dirija oficio, al citado órgano judicial, al objeto de que se remitan las actuaciones en el plazo más breve posible,

fije fecha para los actos de conciliación y juicio y, en su día, recaiga sentencia unificada sobre todas las cuestiones planteadas.

Es de Justicia que se solicita en [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
