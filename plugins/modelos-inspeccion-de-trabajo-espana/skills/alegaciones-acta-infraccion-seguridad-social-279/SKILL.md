---
name: alegaciones-acta-infraccion-seguridad-social-279
description: "Redacta el escrito «Alegaciones al acta de infracción de Seguridad Social (trabajadores, beneficiarios y solicitantes)» (formulario 279 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alegaciones al acta de infracción de Seguridad Social (trabajadores, beneficiarios y solicitantes)

> Formulario 0279 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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
- Procedimiento de leves y graves de beneficiarios: lo inicia la entidad gestora, 15 días hábiles para alegar (art. 37 bis.3 RD 928/1998); sanciones de pérdida o extinción de prestaciones, no multas (art. 47.1 LISOS).

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
- [ ] IMPORTE (2 veces)
- [ ] DESCRIBIR
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…LEVE:»; «… notificaciones y comunicaciones. GRAVE:»; «…acceso al mercado de trabajo. MUY GRAVE:»; «…al y como sucedieron son los siguientes:»; «…nfracción no son ciertos, por cuanto que»; «…n califica genéricamente los hechos como»; «…consistente en que se tome declaración a»; «…s escritos que se acompañan como números»; «… procedentes. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- 24 / 25 / 26
- personas trabajadoras / clientes

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (4)

Inclúyelos solo si encajan en los hechos:

- (Si no se refleja el nombre de los trabajadores en el acta)…
- (Si el acta se limita a calificar los hechos de forma genérica)…
- Testifical, consistente en que se tome declaración a [COMPLETAR], en cuanto [ELEGIR: personas trabajadoras / c…
- Documental, consistente en los escritos que se acompañan como números [COMPLETAR], consistentes en [DESCRIBIR]…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 24 a 26 de la LISOS
- art. 3 de la Ley 3/2023
- art. 24 y 26 LISOS
- artículo 52.1.b) del Real Decreto Legislativo 5/2000
- artículo 17.1 del Real Decreto 928/1998
- Real Decreto-ley 2/2024

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

### Formulario 0279 · Alegaciones al acta de infracción de Seguridad Social (trabajadores, beneficiarios y solicitantes)

- Año del modelo: 2017
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 3 desplegables y casillas convertidos en elección en blanco; 5 bloques de alternativas señalados; 4 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Alegaciones: 15 días hábiles ante el órgano instructor (art. 17.1 RD 928/1998; art. 52.1.b LISOS). Si la sanción es solo pecuniaria, en el mismo plazo cabe pagar con reducción del 40 % renunciando a recursos (arts. 14.6 y 17.1). El expediente caduca a los 6 meses desde la fecha del acta hasta la notificación de la resolución (art. 20.3). · Procedimiento de leves y graves de beneficiarios: lo inicia la entidad gestora, 15 días hábiles para alegar (art. 37 bis.3 RD 928/1998); sanciones de pérdida o extinción de prestaciones, no multas (art. 47.1 LISOS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO COMPETENTE PARA SANCIONAR POR RAZÓN DE LA MATERIA
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de escrito de alegaciones, ante el órgano competente para dictar resolución, en el caso de acta de infracción leve, grave o muy grave, por las siguientes causas establecidas en el artículo 24 a 26 de la LISOS, con solicitud de sobreseimiento del expediente sancionador o, subsidiariamente, reducción de la sanción:

- Incumplir la obligación de facilitar datos para la afiliación o alta y de los deberes informativos

- No comparecer ante la entidad gestora de las prestaciones

- No comparecer ante los servicios públicos de empleo o las agencias de colocación

- No devolver el justificante de haber comparecido para cubrir las ofertas de empleo

- No cumplir las exigencias del acuerdo de actividad en los términos del art. 3 de la Ley 3/2023, de 28 de febrero, de Empleo

- No facilitar a los servicios públicos de empleo información para recibir notificaciones y comunicaciones

- Efectuar trabajos por cuenta propia o ajena durante la percepción de prestaciones, cuando exista incompatibilidad

- No comparecer a los reconocimientos médicos ordenados o no presentar ante las entidades gestoras los antecedentes, justificantes o datos requeridos

- No comunicar las bajas en las prestaciones en el momento en que se produzca incompatibilidad, suspensión o extinción del derecho.

- Rechazar una oferta de empleo adecuada

- Negarse a participar en acciones, programas o actividades señalados en el itinerario o plan personalizado para la mejora de la empleabilidad y el acceso al mercado de trabajo

- Obtener o prolongar fraudulentamente el disfrute de prestaciones

- Compatibilizar las prestaciones o el subsidio por desempleo, o la prestación por cese de actividad, con el trabajo por cuenta propia o ajena, salvo que sea a tiempo parcial

- Connivencia para la obtención indebida de prestaciones

- No aplicar o desviar la aplicación de las prestaciones por desempleo percibidas conforme a programas de fomento de empleo

Actualizado conforme a las modificaciones del art. 24 y 26 LISOS introducidas por el Real Decreto-ley 2/2024, de 21 de mayo, por el que se adoptan medidas urgentes para la simplificación y mejora del nivel asistencial de la protección por desempleo, y para completar la transposición de la Directiva (UE) 2019/1158 del Parlamento Europeo y del Consejo, de 20 de junio de 2019, relativa a la conciliación de la vida familiar y la vida profesional de los progenitores y los cuidadores, y por la que se deroga la Directiva 2010/18/UE del Consejo

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada el acta de infracción número [NÚMERO], con la que no estoy de acuerdo con el relato de hechos en los términos descritos, ni con su calificación jurídica, ni con la propuesta de sanción en la misma contenida, por lo que, dentro del plazo de quince días hábiles concedido al efecto, formulo el presente ESCRITO DE ALEGACIONES en base a los siguientes hechos y fundamentos de derecho:

HECHOS

PRIMERO.- Que con fecha [FECHA] se dictó acta de infracción número en la que se propone una multa de [NOTA DE REVISIÓN: Las sanciones a beneficiarios son de pérdida o extinción de prestaciones (art. 47.1 LISOS), no multas; adaptar el modelo. Fuente: RDLeg 5/2000 (LISOS), BOE-A-2000-15060, art. 47.1.] [IMPORTE] euros, ya que, de conformidad con el artículo [ELEGIR: 24 / 25 / 26] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

LEVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Incumplir la obligación de facilitar datos para la afiliación o alta y de los deberes informativos.

No comparecer ante la entidad gestora de las prestaciones.

No comparecer ante los servicios públicos de empleo o las agencias de colocación.

No devolver el justificante de haber comparecido para cubrir las ofertas de empleo.

No cumplir las exigencias del acuerdo de actividad en los términos del art. 3 de la Ley 3/2023, de 28 de febrero, de Empleo.

No facilitar a los servicios públicos de empleo información para recibir notificaciones y comunicaciones.

GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Efectuar trabajos por cuenta propia o ajena durante la percepción de prestaciones, cuando exista incompatibilidad.

No comparecer a los reconocimientos médicos ordenados o no presentar ante las entidades gestoras los antecedentes, justificantes o datos requeridos.

No comunicar las bajas en las prestaciones en el momento en que se produzca incompatibilidad, suspensión o extinción del derecho.

Rechazar una oferta de empleo adecuada.

Negarse a participar en acciones, programas o actividades señalados en el itinerario o plan personalizado para la mejora de la empleabilidad y el acceso al mercado de trabajo.

MUY GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Obtener o prolongar fraudulentamente el disfrute de prestaciones.

Compatibilizar las prestaciones o el subsidio por desempleo, o la prestación por cese de actividad, con el trabajo por cuenta propia o ajena, salvo que sea a tiempo parcial.

Connivencia para la obtención indebida de prestaciones.

No aplicar o desviar la aplicación de las prestaciones por desempleo percibidas conforme a programas de fomento de empleo.

SEGUNDO.- Que, en el acta de infracción arriba referenciada, se reflejan unos hechos que no responden a la realidad de lo acaecido, al no describirse pormenorizadamente el supuesto comportamiento infractor, n i destacar cuáles son los hechos relevantes a efectos de la tipificación y graduación de la sanción. En concreto, los hechos tal y como sucedieron son los siguientes: [COMPLETAR].

TERCERO.- Que la calificación realizada en el acta de los anteriores hechos no es conforme al ordenamiento jurídico, puesto que no se dan los elementos objetivos y subjetivos de la infracción presuntamente cometida, en base a las siguientes razones:

A) En relación a los elementos objetivos de la infracción, los hechos reflejados en el acta de infracción no son ciertos, por cuanto que [COMPLETAR].

[OPCIONAL — incluir si procede]

(Si no se refleja el nombre de los trabajadores en el acta)

Además, el acta de infracción nos causa una gran indefensión porque no refleja el nombre de los trabajadores afectados por la supuesta infracción que ha originado el acta, por lo que no podemos conocer con exactitud cuál ha sido el supuesto comportamiento infractor y, en consecuencia, proceder a desvirtuar tales afirmaciones.

[OPCIONAL — incluir si procede]

(Si el acta se limita a calificar los hechos de forma genérica)

Además, el acta de infracción califica genéricamente los hechos como [COMPLETAR], sin describir pormenorizadamente la conducta realizada por el empresario, y no se aportan los elementos de juicio necesarios, dado lo escaso del relato, para que el órgano competente sancionador pueda adoptar su decisión, ni tampoco para que el inculpado pueda defenderse de unos hechos que no se describen con el detalle necesario para poder ser calificados como constitutivos de esta infracción, tal y como reiteradamente viene exigiendo la jurisprudencia de nuestro Tribunal Supremo.

B) En cuanto al elemento subjetivo, los hechos acaecidos no son susceptibles de incardinarse en la infracción administrativa tal y como se hizo en el acta de infracción, sino que en atención a lo sucedido y a las circunstancias de hechos concurrentes no existe culpabilidad del empresario.

CUARTO.- Que la propuesta de sanción realizada en el acta de infracción consistente en el pago de una multa en cuantía de [IMPORTE] euros, vulnera el principio de proporcionalidad (adaptación de la sanción a la gravedad de los hechos reprochables a los interesados, a partir del carácter intencional de la infracción, la reincidencia, la naturaleza de los daños causados, etc.) y demás principios que informan el ejercicio de la potestad sancionadora en materia de infracciones en el orden social, atendiendo al relato de hechos más arriba reseñado.

Que para la demostración de las afirmaciones anteriormente manifestadas en este escrito de alegaciones, y sin perjuicio de las demás actuaciones que de oficio sean practicadas por el órgano instructor competente, se propone la práctica de los siguientes MEDIOS DE PRUEBA:

[OPCIONAL — incluir si procede]

Testifical, consistente en que se tome declaración a [COMPLETAR], en cuanto [ELEGIR: personas trabajadoras / clientes] y testigos presenciales de los hechos reflejados en el acta de infracción, por tener un conocimiento directo de los mismos en razón de su presencia física en el momento en que tuvo lugar la infracción presuntamente cometida.

[OPCIONAL — incluir si procede]

Documental, consistente en los escritos que se acompañan como números [COMPLETAR], consistentes en [DESCRIBIR], todos ellos necesarios para el conocimiento más preciso de los hechos reflejados en el acta de infracción, así como de las posibles responsabilidades.

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.- El presente escrito de alegaciones se interpone en virtud de lo establecido en el artículo 52.1.b) del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, en relación con lo dispuesto en el artículo 17.1 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social.

II.- A quien me dirijo es el órgano competente para su tramitación, ya que el escrito de alegaciones y los medios de prueba de que intenten valerse serán presentados ante el órgano instructor del expediente, de acuerdo con el citado artículo 17.1 del Real Decreto 928/1998, de 14 de mayo.

III.- Notificada el acta de infracción el día [FECHA], se formula el presente escrito de alegaciones dentro del indicado plazo de quince días, siendo de aplicación el artículo 37 bis.3 del citado Real Decreto 928/1998 [NOTA DE REVISIÓN: El plazo de 15 días hábiles para alegar está en el art. 37 bis.3; el 37 bis.4 regula la resolución. Fuente: RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), art. 37 bis.3.], de 14 de mayo.

IV.-

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Incumplir la obligación de facilitar datos para la afiliación o alta y de los deberes informativos)
— (No comparecer ante la entidad gestora de las prestaciones)
— (No comparecer ante los servicios públicos de empleo o las agencias de colocación)
— (No devolver el justificante de haber comparecido para cubrir las ofertas de empleo)
— (No cumplir las exigencias del compromiso de actividad)
— (No facilitar a los servicios públicos de empleo información para recibir notificaciones y comunicaciones)
— (No estar inscrito como demandante de empleo)
— (Efectuar trabajos por cuenta propia o ajena durante la percepción de prestaciones, cuando exista incompatibilidad)
— (No comparecer a los reconocimientos médicos ordenados o no presentar ante las entidades gestoras los antecedentes, justificantes o datos requeridos)
— (No comunicar las bajas en las prestaciones)
— (Rechazar una oferta de empleo adecuada)
— (Negarse a participar en trabajos de colaboración social, programas de empleo o acciones de promoción, formación, motivación, información, orientación, inserción o reconversión profesional)
— (Obtener o prolongar fraudulentamente el disfrute de prestaciones)
— (Compatibilizar las prestaciones o el subsidio por desempleo, o la prestación por cese de actividad, con el trabajo por cuenta propia o ajena, salvo que sea a tiempo parcial)
— (Connivencia para la obtención indebida de prestaciones)
— (No aplicar o desviar la aplicación de las prestaciones por desempleo percibidas conforme a programas de fomento de empleo)

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por presentado este escrito de alegaciones con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que se deje sin efecto el acta de infracción y, en consecuencia, acuerde el sobreseimiento del expediente sancionador o, subsidiariamente y para el caso de no estimar la petición de archivo del expediente, disponga la reducción de la sanción inicialmente propuesta a la cuantía inferior de su grado mínimo, sin perjuicio de la interposición ulterior de los recursos procedentes.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
