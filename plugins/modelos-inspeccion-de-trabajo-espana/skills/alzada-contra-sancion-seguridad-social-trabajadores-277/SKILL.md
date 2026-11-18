---
name: alzada-contra-sancion-seguridad-social-trabajadores-277
description: "Redacta el escrito «Alzada contra sanción de Seguridad Social a trabajadores y beneficiarios de prestaciones» (formulario 277 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alzada contra sanción de Seguridad Social a trabajadores y beneficiarios de prestaciones

> Formulario 0277 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Modelo mal planteado: en leves y graves de beneficiarios la resolución de la entidad gestora agota la vía administrativa y se impugna ante el orden social (art. 37 bis.4 RD 928/1998); las sanciones no son multas sino pérdida o extinción de prestaciones (art. 47.1 LISOS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] ÓRGANO AL QUE SE DIRIGE
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] FECHA (2 veces)
- [ ] ÓRGANO O PERSONA
- [ ] Nº DE EXPEDIENTE
- [ ] IMPORTE (3 veces)
- [ ] NÚMERO
- [ ] Otros 5 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…al y como sucedieron son los siguientes:»; «…nfracción no son ciertos, por cuanto que»; «…n califica genéricamente los hechos como»; «…d a dictarse la resolución sancionadora:»; «… procedentes. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- 24 / 25 / 26

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Infracción leve / Infracción grave / Infracción muy grave — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la resolución sancionadora es nula por haber sido dictada por órgano incompetente / Si la resolución sancionadora es contraria al principio de tipicidad / Si la resolución sancionadora vulnera el derecho a la tutela judicial efectiva / Si se ha vulnerado el derecho a la presunción de inocencia / Si se ha vulnerado algún derecho del art. 24 de CE / Si la resolució
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- (Si no se refleja el nombre de los trabajadores en el acta)…
- (Si el acta se limita a calificar los hechos de forma genérica)…
- IV.- La sanción impuesta vulnera el principio de proporcionalidad establecido en el artículo 39 del Real Decre…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 54 del Real Decreto Legislativo 5/2000
- artículos 24, 25 y 26 de la LISOS
- art. 3 de la Ley 3/2023
- art. 24 y 26 LISOS
- artículos 23 del Real Decreto 928/1998
- art. 24 de CE
- artículo 39 del Real Decreto Legislativo 5/2000
- Ley 39/2015
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

### Formulario 0277 · Alzada contra sanción de Seguridad Social a trabajadores y beneficiarios de prestaciones

- Año del modelo: 2017
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; 2 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 1 bloques de alternativas señalados; 3 párrafos opcionales señalados; 18 campos de relleno marcados en blanco
- Avisos de la revisión: Modelo mal planteado: en leves y graves de beneficiarios la resolución de la entidad gestora agota la vía administrativa y se impugna ante el orden social (art. 37 bis.4 RD 928/1998); las sanciones no son multas sino pérdida o extinción de prestaciones (art. 47.1 LISOS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO SUPERIOR JERÁRQUICO DEL QUE DICTÓ LA RESOLUCIÓN
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de recurso de alzada ante el órgano superior jerárquico del que dictó la resolución, contra resolución sancionadora por infracción leve, grave o muy grave de trabajadores o asimilados, beneficiarios y solicitantes de prestaciones, conforme establecen los artículos 54 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, 23 y 37 bis.4 del Real Decreto 928/1998 [NOTA DE REVISIÓN: El art. 37 bis.4 dice lo contrario de lo que se pretende: en infracciones leves y graves de solicitantes o beneficiarios, la resolución de la entidad gestora pone fin a la vía administrativa y se impugna ante el orden social; no cabe alzada. La alzada del art. 23 encaja, en principio, solo en las muy graves, que siguen el procedimiento ordinario iniciado por acta (art. 52.2 LISOS a contrario). Fuente: RD 928/1998, BOE-A-1998-12816 (red. RD 688/2021, BOE-A-2021-13382), arts. 23 y 37 bis.4.], de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 121 y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas, por las siguientes causas establecidas en los artículos 24, 25 y 26 de la LISOS:

- Incumplir la obligación de facilitar datos para la afiliación o alta y de los deberes informativos

- No comparecer ante la entidad gestora de las prestaciones

- No comparecer ante los servicios públicos de empleo o las agencias de colocación

- No devolver el justificante de haber comparecido para cubrir las ofertas de empleo

- No cumplir las exigencias del acuerdo de actividad en los términos del art. 3 de la Ley 3/2023, de 28 de febrero, de Empleo

- No facilitar a los servicios públicos de empleo información para recibir notificaciones y comunicaciones

- Efectuar trabajos por cuenta propia o ajena durante la percepción de prestaciones, cuando exista incompatibilidad

- No comparecer a los reconocimientos médicos ordenados o no presentar ante las entidades gestoras los antecedentes, justificantes o datos requeridos

- No comunicar las bajas en las prestaciones en el momento en que se produzca incompatibilidad, suspensión o extinción del derecho

- Rechazar una oferta de empleo adecuada

- Negarse a participar en acciones, programas o actividades señalados en el itinerario o plan personalizado para la mejora de la empleabilidad y el acceso al mercado de trabajo

- Obtener o prolongar fraudulentamente el disfrute de prestaciones

- Compatibilizar las prestaciones o el subsidio por desempleo, o la prestación por cese de actividad, con el trabajo por cuenta propia o ajena, salvo que sea a tiempo parcial

- Connivencia para la obtención indebida de prestaciones

- No aplicar o desviar la aplicación de las prestaciones por desempleo percibidas conforme a programas de fomento de empleo

Actualizado conforme a las modificaciones del art. 24 y 26 LISOS introducidas por el Real Decreto-ley 2/2024, de 21 de mayo, por el que se adoptan medidas urgentes para la simplificación y mejora del nivel asistencial de la protección por desempleo, y para completar la transposición de la Directiva (UE) 2019/1158 del Parlamento Europeo y del Consejo, de 20 de junio de 2019, relativa a la conciliación de la vida familiar y la vida profesional de los progenitores y los cuidadores, y por la que se deroga la Directiva 2010/18/UE del Consejo

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada la resolución sancionadora dictada por [ÓRGANO O PERSONA] en el expediente número [Nº DE EXPEDIENTE], y en la que se acuerda imponer a la empresa una multa de [NOTA DE REVISIÓN: A trabajadores, solicitantes y beneficiarios no se les imponen multas: pérdida de la prestación (1 o 3 meses), extinción o pérdida de 6 meses y exclusión, según gravedad (art. 47.1 LISOS, red. RDL 2/2024). Adaptar «empresa» y «multa» en todo el modelo. Fuente: RDLeg 5/2000 (LISOS), BOE-A-2000-15060, art. 47.1.] [IMPORTE] euros.

Que, contra dicha resolución, por considerarla no ajustada a Derecho, interpone RECURSO DE ALZADA en el plazo de un mes concedido al efecto, conforme establecen los artículos 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas, en base a los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que con fecha [FECHA] se dictó resolución sancionadora que tiene su origen en el acta de infracción número [NÚMERO], en la que se impone una multa de [IMPORTE] euros, ya que, de conformidad con el artículo [ELEGIR: 24 / 25 / 26] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Infracción leve / Infracción grave / Infracción muy grave — el texto de cada opción no venía en el formulario original]

SEGUNDO.- Que en el acta de infracción más arriba referenciada y en el informe complementario posterior que sirven de fundamento a la resolución sancionadora, se reflejan unos hechos que no responden a la realidad de lo acaecido, al no describirse pormenorizadamente el supuesto comportamiento infractor, ni destacar cuáles son los hechos relevantes a efectos de la tipificación y graduación de la sanción. En concreto, los hechos tal y como sucedieron son los siguientes: [COMPLETAR].

TERCERO.- Que la calificación realizada en el expediente sancionador de los anteriores hechos no es conforme al ordenamiento jurídico puesto que no se dan los elementos objetivos y subjetivos de la infracción presuntamente cometida, en base a las siguientes razones:

A) En relación a los elementos objetivos de la infracción, los hechos reflejados en el acta de infracción no son ciertos, por cuanto que [COMPLETAR].

[OPCIONAL — incluir si procede]

(Si no se refleja el nombre de los trabajadores en el acta)

Además, el acta de infracción nos causa una gran indefensión porque no refleja el nombre de las personas trabajadoras afectados por la supuesta infracción que ha originado el acta, por lo que no podemos conocer con exactitud cuál ha sido el supuesto comportamiento infractor y, en consecuencia, proceder a desvirtuar tales afirmaciones.

[OPCIONAL — incluir si procede]

(Si el acta se limita a calificar los hechos de forma genérica)

Además, el acta de infracción califica genéricamente los hechos como [COMPLETAR], sin describir pormenorizadamente la conducta realizada por el empresario, y no se aportan los elementos de juicio necesarios, dado lo escaso del relato, para que el órgano competente sancionador pueda adoptar su decisión, ni tampoco para que el inculpado pueda defenderse de unos hechos que no se describen con el detalle necesario para poder ser calificados como constitutivos de esta infracción, tal y como reiteradamente viene exigiendo la jurisprudencia de nuestro Tribunal Supremo.

B) En cuanto al elemento subjetivo, los hechos acaecidos no son susceptibles de incardinarse en la infracción administrativa tal y como se hizo en el acta de infracción, sino que en atención a lo sucedido y a las circunstancias de hechos concurrentes no existe culpabilidad del empresario.

CUARTO.- Que la sanción impuesta, consistente en el pago de una multa en cuantía de [IMPORTE] euros, vulnera el principio de proporcionalidad y demás principios que informan el ejercicio de la potestad sancionadora en materia de infracciones en el orden social, atendiendo al relato de hechos más arriba reseñado.

Que, para la demostración de las afirmaciones anteriormente manifestadas, se propone la práctica de los siguientes MEDIOS DE PRUEBA, que incomprensiblemente los órganos instructor y sancionador no admitieron con anterioridad a dictarse la resolución sancionadora: [COMPLETAR].

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.- Procede la interposición del presente recurso de alzada conforme establecen los artículos 54 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 121 y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas.

II.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la resolución sancionadora es nula por haber sido dictada por órgano incompetente / Si la resolución sancionadora es contraria al principio de tipicidad / Si la resolución sancionadora vulnera el derecho a la tutela judicial efectiva / Si se ha vulnerado el derecho a la presunción de inocencia / Si se ha vulnerado algún derecho del art. 24 de CE / Si la resolución sancionadora ha infringido el art. 14 del Reglamento sobre procedimientos para la imposición de sanciones / Si se han infringido todos los trámites esenciales destinados a la comprobación efectiva y adecuada de los hechos — el texto de cada opción no venía en el formulario original]

III.–

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (Si la sanción impuesta se basa en la infracción de incumplir la obligación de facilitar datos para la afiliación o alta y de los deberes informativos)
— (Si la sanción impuesta se basa en la infracción de no comparecer ante la entidad gestora de las prestaciones)
— (Si la sanción impuesta se basa en la infracción de no comparecer ante los servicios públicos de empleo o las agencias de colocación)
— (Si la sanción impuesta se basa en la infracción de no devolver el justificante de haber comparecido para cubrir las ofertas de empleo)
— (Si la sanción impuesta se basa en la infracción de no cumplir las exigencias del compromiso de actividad)
— (Si la sanción impuesta se basa en la infracción de no facilitar a los servicios públicos de empleo información para recibir notificaciones y comunicaciones)
— (Si la sanción impuesta se basa en la infracción de no estar inscrito como demandante de empleo)
— (Si la sanción impuesta se basa en la infracción de efectuar trabajos por cuenta propia o ajena durante la percepción de prestaciones, cuando exista incompatibilidad)
— (Si la sanción impuesta se basa en la infracción de no comparecer a los reconocimientos médicos ordenados o no presentar ante las entidades gestoras los antecedentes, justificantes o datos requeridos)
— (Si la sanción impuesta se basa en la infracción de no comunicar las bajas en las prestaciones)
— (Si la sanción impuesta se basa en la infracción de rechazar una oferta de empleo adecuada)
— (Si la sanción impuesta se basa en la infracción de negarse a participar en trabajos de colaboración social, programas de empleo o acciones de promoción, formación, motivación, información, orientación, inserción o reconversión profesional)
— (Si la sanción impuesta se basa en la infracción de obtener o prolongar fraudulentamente el disfrute de prestaciones)
— (Si la sanción impuesta se basa en la infracción de compatibilizar las prestaciones o el subsidio por desempleo, o la prestación por cese de actividad, con el trabajo por cuenta propia o ajena, salvo que sea a tiempo parcial)
— (Si la sanción impuesta se basa en la infracción de connivencia para la obtención indebida de prestaciones)
— (Si la sanción impuesta se basa en la infracción de no aplicar o desviar la aplicación de las prestaciones por desempleo percibidas conforme a programas de fomento de empleo)

[OPCIONAL — incluir si procede]

IV.- La sanción impuesta vulnera el principio de proporcionalidad establecido en el artículo 39 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, puesto que no se adapta a la gravedad de la infracción, así como a las circunstancias de hecho concurrentes que no han sido tenidas en cuenta a la hora de graduar la multa infligida. Al no considerarse relevantes las circunstancias de graduación, la sanción debe imponerse en la cuantía inferior del grado mínimo, máxime cuando el acta de infracción no contiene una descripción detallada de tales circunstancias, incurriéndose en arbitrariedad y discrecionalidad impropia de un expediente administrativo sancionador.

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por interpuesto Recurso de Alzada con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que declare la invalidez de la resolución sancionadora impugnada y del acta de infracción, con el consiguiente archivo del expediente sancionador o, subsidiariamente y para el caso de no estimar la petición de archivo del expediente, disponga la reducción de la sanción inicialmente propuesta a la cuantía inferior de su grado mínimo, sin perjuicio de la interposición ulterior de los recursos procedentes.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
