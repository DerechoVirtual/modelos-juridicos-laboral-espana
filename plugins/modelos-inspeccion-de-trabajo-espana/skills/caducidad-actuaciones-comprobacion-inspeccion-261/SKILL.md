---
name: caducidad-actuaciones-comprobacion-inspeccion-261
description: "Redacta el escrito «Caducidad de las actuaciones de comprobación de la Inspección: alegaciones» (formulario 261 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Caducidad de las actuaciones de comprobación de la Inspección: alegaciones

> Formulario 0261 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Alegaciones: 15 días hábiles ante el órgano instructor (art. 17.1 RD 928/1998; art. 52.1.b LISOS). Si la sanción es solo pecuniaria, en el mismo plazo cabe pagar con reducción del 40 % renunciando a recursos (arts. 14.6 y 17.1). El expediente caduca a los 6 meses desde la fecha del acta hasta la notificación de la resolución (art. 20.3).
- Plazo de actuaciones comprobatorias: 9 meses ampliables por otros 9 y 5 meses de interrupción máxima (art. 21.4 Ley 23/2015); el efecto es que no se interrumpe la prescripción y decae la posibilidad de extender acta por esas actuaciones, pero pueden iniciarse otras si no ha prescrito (art. 8.2 RD 928/1998).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] ÓRGANO AL QUE SE DIRIGE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] FECHA (3 veces)
- [ ] NÚMERO
- [ ] IMPORTE
- [ ] DESCRIBIR
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, ya que, de conformidad con el artículo»; «…onstitutivos de la siguiente infracción:»; «…consistente en que se tome declaración a»; «…s escritos que se acompañan como números»; «… sancionador. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- personas trabajadoras / clientes

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- Testifical, consistente en que se tome declaración a [COMPLETAR], en cuanto [ELEGIR: personas trabajadoras / c…
- Documental, consistente en los escritos que se acompañan como números [COMPLETAR], consistentes en [DESCRIBIR]…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 21.4 de la Ley 23/2015
- artículo 21.4 de la Ley 23/2015
- artículo 52.1.b) del Real Decreto Legislativo 5/2000
- artículo 17.1 del Real Decreto 928/1998

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

### Formulario 0261 · Caducidad de las actuaciones de comprobación de la Inspección: alegaciones

- Año del modelo: 2017
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 2 desplegables y casillas convertidos en elección en blanco; 2 párrafos opcionales señalados; 16 campos de relleno marcados en blanco
- Avisos de la revisión: Alegaciones: 15 días hábiles ante el órgano instructor (art. 17.1 RD 928/1998; art. 52.1.b LISOS). Si la sanción es solo pecuniaria, en el mismo plazo cabe pagar con reducción del 40 % renunciando a recursos (arts. 14.6 y 17.1). El expediente caduca a los 6 meses desde la fecha del acta hasta la notificación de la resolución (art. 20.3). · Plazo de actuaciones comprobatorias: 9 meses ampliables por otros 9 y 5 meses de interrupción máxima (art. 21.4 Ley 23/2015); el efecto es que no se interrumpe la prescripción y decae la posibilidad de extender acta por esas actuaciones, pero pueden iniciarse otras si no ha prescrito (art. 8.2 RD 928/1998).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO COMPETENTE PARA SANCIONAR POR RAZÓN DE LA MATERIA, ARTS. 48 Y 52.1 b) LISOS
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de escrito de alegaciones por caducidad de actuaciones comprobatorias de la Inspección de Trabajo y Seguridad Social, al haber superado el plazo máximo legalmente previsto para su realización, ante el órgano competente por razón de la materia, de conformidad con lo establecido en los artículos 21.4 de la Ley 23/2015, de 21 de julio, Ordenadora del Sistema de Inspección de Trabajo y Seguridad Social, y 17 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que, el día [FECHA] me ha sido notificada el acta de infracción número [NÚMERO], con la que no estoy de acuerdo con el relato de hechos en los términos descritos, ni con su calificación jurídica, ni con la propuesta de sanción en la misma contenida, por lo que, dentro del plazo de quince días hábiles concedido al efecto, formulo el presente ESCRITO DE ALEGACIONES en base a los siguientes hechos y fundamentos de derecho:

HECHOS

PRIMERO.- Que, con fecha [FECHA] se dictó acta de infracción número en la que se propone una multa de [IMPORTE] euros, ya que, de conformidad con el artículo [COMPLETAR] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción: [COMPLETAR].

SEGUNDO.- Que, en el acta de infracción arriba referenciada es improcedente, por cuanto que se ha dictado una vez que ha superado el plazo máximo de duración de nueve meses previsto para la realización de las actuaciones comprobatorias [NOTA DE REVISIÓN: Art. 21.4 Ley 23/2015: 9 meses, ampliables por otros 9 (especial complejidad, obstrucción u ocultación, cooperación internacional); interrupción máxima 5 meses salvo causa del inspeccionado o pendencia judicial; el cómputo empieza en la primera visita o en la comparecencia con toda la documentación, y no computa el plazo de subsanación de requerimientos. No confundir con la caducidad del procedimiento sancionador (6 meses desde la fecha del acta hasta la notificación de la resolución, art. 20.3 RD 928/1998). Fuente: Ley 23/2015, BOE-A-2015-8168, art. 21.4; RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), arts. 8.2 y 20.3.], sin que exista dilación alguna imputable a este sujeto inspeccionado y sancionado, vulnerando lo previsto en el artículo 21.4 de la Ley 23/2015, de 21 de julio, Ordenadora del Sistema de Inspección de Trabajo y Seguridad Social.

En todo caso, ha transcurrido con creces el plazo de cinco meses establecido para interrumpir las actuaciones comprobatorias, sin que esta interrupción haya sido causada por este sujeto inspeccionado o por personas dependientes, sino por la propia Administración actuante, ni estemos ante actividades de inspección que revistan especial dificultad y complejidad o requieran cooperación administrativa internacional, ni haya existido obstrucción u ocultación de las actividades, ni se haya constatado la imposibilidad de proseguir la actuación inspectora por la pendencia de un pronunciamiento judicial que pudiera condicionar su resultado, por lo que estamos ante una caducidad de las actuaciones comprobatorias inspectoras, al haberse infringido el antedicho artículo.

TERCERO.- Que, para la demostración de las afirmaciones anteriormente manifestadas en este escrito de alegaciones, y sin perjuicio de las demás actuaciones que de oficio sean practicadas por el órgano instructor competente, se propone la práctica de los siguientes MEDIOS DE PRUEBA:

[OPCIONAL — incluir si procede]

Testifical, consistente en que se tome declaración a [COMPLETAR], en cuanto [ELEGIR: personas trabajadoras / clientes] y testigos presenciales de los hechos reflejados en el acta de infracción, por tener un conocimiento directo de los mismos en razón de su presencia física en el momento en que tuvo lugar la infracción presuntamente cometida.

[OPCIONAL — incluir si procede]

Documental, consistente en los escritos que se acompañan como números [COMPLETAR], consistentes en [DESCRIBIR], todos ellos necesarios para el conocimiento más preciso de los hechos reflejados en el acta de infracción, así como de las posibles responsabilidades.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.- El presente escrito de alegaciones se interpone en virtud de lo establecido en el artículo 52.1.b) del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, en relación con lo dispuesto en el artículo 17.1 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social.

II.- A quien me dirijo es el órgano competente para su tramitación, ya que el escrito de alegaciones y los medios de prueba de que intenten valerse serán presentados ante el órgano instructor del expediente, de acuerdo con el citado artículo 17.1 del Real Decreto 928/1998, de 14 de mayo.

III.- Notificada el acta de infracción el día [FECHA], se formula el presente escrito de alegaciones dentro del indicado plazo de quince días.

IV.- Es de aplicación el artículo 21.4 de la Ley 23/2015, de 21 de julio, Ordenadora del Sistema de Inspección de Trabajo y Seguridad Social.

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por presentado este escrito de alegaciones con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que se deje sin efecto el acta de infracción y, en consecuencia, acuerde el sobreseimiento del expediente sancionador.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
