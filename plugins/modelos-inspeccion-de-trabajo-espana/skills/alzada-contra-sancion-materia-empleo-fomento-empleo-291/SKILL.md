---
name: alzada-contra-sancion-materia-empleo-fomento-empleo-291
description: "Redacta el escrito «Alzada contra sanción en materia de empleo y fomento del empleo» (formulario 291 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alzada contra sanción en materia de empleo y fomento del empleo

> Formulario 0291 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Alzada: un mes ante el órgano superior (art. 23.1 RD 928/1998, red. RD 688/2021; arts. 121-122 LPAC); no cabe si se pagó con la reducción del 40 % (art. 23.1, párr. 2.º); silencio desestimatorio a los tres meses (art. 23.2).
- Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Arts. 14-16 LISOS tras la Ley 3/2023: suprimidos el art. 15.1 y la letra b) del 16.1, y modificadas las letras c), d) y e) del 16.1 (DF 1.ª).

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
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, apartado»; «…LEVE:»; «…ación profesional para el empleo. GRAVE:»; «…n profesional para el empleo. MUY GRAVE:»; «…al y como sucedieron son los siguientes:»; «…nfracción no son ciertos, por cuanto que»; «…n califica genéricamente los hechos como»; «…d a dictarse la resolución sancionadora:»; «… procedentes. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- 14 / 15 / 16

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la resolución sancionadora fue dictada por órgano incompetente / Si la resolución sancionadora es contraria al principio de tipicidad / Si la resolución sancionadora vulnera el derecho a la tutela judicial efectiva / Si la resolución sancionadora vulnera la presunción de inocencia / Si la resolución sancionadora vulnera los derechos de defensa por falta de inform
- ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- (Si no se refleja el nombre de los trabajadores en el acta)…
- (Si el acta se limita a calificar los hechos de forma genérica)…
- IV.- La sanción impuesta vulnera el principio de proporcionalidad establecido en el artículo 39 del Real Decre…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículos 54 del Real Decreto Legislativo 5/2000
- artículos 14 a 16 de la LISOS
- artículos 15 y 16 LISOS
- artículos 23 del Real Decreto 928/1998
- artículo 39 del Real Decreto Legislativo 5/2000
- Ley 39/2015
- Ley 3/2023

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

### Formulario 0291 · Alzada contra sanción en materia de empleo y fomento del empleo

- Año del modelo: 2017
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 5 bloques de alternativas señalados; 3 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Avisos de la revisión: Alzada: un mes ante el órgano superior (art. 23.1 RD 928/1998, red. RD 688/2021; arts. 121-122 LPAC); no cabe si se pagó con la reducción del 40 % (art. 23.1, párr. 2.º); silencio desestimatorio a los tres meses (art. 23.2). · Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Arts. 14-16 LISOS tras la Ley 3/2023: suprimidos el art. 15.1 y la letra b) del 16.1, y modificadas las letras c), d) y e) del 16.1 (DF 1.ª).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO SUPERIOR JERÁRQUICO DEL QUE DICTÓ LA RESOLUCIÓN
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de recurso de alzada, ante el órgano superior jerárquico del que dictó la resolución, contra resolución sancionadora por infracción leve, grave o muy grave, conforme establecen los artículos 54 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 121 y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas, por las siguientes causas establecidas en los artículos 14 a 16 de la LISOS:

- No comunicar las contrataciones realizadas

- No comunicar la terminación de los contratos de trabajo

- No registrar el contrato de trabajo y sus prórrogas

- Incumplir las obligaciones formales o documentales no graves ni muy graves exigidas en la normativa sobre formación profesional para el empleo

- Incumplir las medidas de reserva, duración o preferencia en el empleo

- Incumplir la obligación legal de reserva de puestos de trabajo para personas con discapacidad, o de aplicación de medidas alternativas

- No notificar las contrataciones de duración determinada o no entregar la copia básica de los contratos a los representantes de los trabajadores

- Publicidad de ofertas de empleo engañosas o ilegales

- Incumplimiento grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo

- Ejercer ilegalmente actividades de intermediación laboral

- Establecer condiciones discriminatorias para el acceso al empleo

- Obtener o disfrutar indebidamente de incentivos a las políticas activas de empleo concedidos

- No aplicar o desviar los incentivos a las políticas activas de empleo concedidos

- Incumplimiento muy grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo

- Aplicar de forma indebida o no aplicar a los fines previstos las donaciones y acciones de patrocinio recibidas como alternativa a la obligación de reserva de empleo a favor de las personas con discapacidad

Actualizado conforme a las modificaciones de los artículos 15 y 16 LISOS introducidas por la Ley 3/2023, de Empleo

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada la resolución sancionadora dictada por [ÓRGANO O PERSONA] en el expediente número [Nº DE EXPEDIENTE], y en la que se acuerda imponer a la empresa una multa de [IMPORTE] euros.

Que, contra dicha resolución, por considerarla no ajustada a Derecho, interpone RECURSO DE ALZADA en el plazo de un mes concedido al efecto, conforme establecen los artículos 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas, en base a los siguientes hechos y fundamentos legales:

HECHOS

PRIMERO.- Que con fecha [FECHA] se dictó resolución sancionadora que tiene su origen en el acta de infracción número [NÚMERO], en la que se impone una multa de [IMPORTE] euros, ya que, de conformidad con el artículo [ELEGIR: 14 / 15 / 16], apartado [COMPLETAR] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

LEVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No comunicar las contrataciones realizadas.

No comunicar la terminación de los contratos de trabajo.

No registrar el contrato de trabajo y sus prórrogas.

Incumplir las obligaciones formales o documentales no graves ni muy graves exigidas en la normativa sobre formación profesional para el empleo.

GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Incumplir las medidas de reserva, duración o preferencia en el empleo.

Incumplir la obligación legal de reserva de puestos de trabajo para personas con discapacidad, o de aplicación de medidas alternativas.

No notificar las contrataciones de duración determinada o no entregar la copia básica de los contratos a los representantes de los trabajadores.

Publicidad de ofertas de empleo engañosas o ilegales.

Incumplimiento grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo.

MUY GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Ejercer ilegalmente actividades de intermediación laboral.

Establecer condiciones discriminatorias para el acceso al empleo.

Obtener o disfrutar indebidamente de los incentivos a las políticas activas de empleo concedidos

No aplicar o desviar los incentivos a las políticas activas de empleo concedidos

Incumplimiento muy grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo.

Aplicar de forma indebida o no aplicar a los fines previstos las donaciones y acciones de patrocinio recibidas como alternativa a la obligación de reserva de empleo a favor de las personas con discapacidad.

SEGUNDO.- Que en el acta de infracción más arriba referenciada y en el informe complementario posterior que sirven de fundamento a la resolución sancionadora, se reflejan unos hechos que no responden a la realidad de lo acaecido, al no describirse pormenorizadamente el supuesto comportamiento infractor, ni destacar cuáles son los hechos relevantes a efectos de la tipificación y graduación de la sanción. En concreto, los hechos tal y como sucedieron son los siguientes: [COMPLETAR].

TERCERO.- Que la calificación realizada en el expediente sancionador de los anteriores hechos no es conforme al ordenamiento jurídico puesto que no se dan los elementos objetivos y subjetivos de la infracción presuntamente cometida, en base a las siguientes razones:

A) En relación a los elementos objetivos de la infracción, los hechos reflejados en el acta de infracción no son ciertos, por cuanto que [COMPLETAR].

[OPCIONAL — incluir si procede]

(Si no se refleja el nombre de los trabajadores en el acta)

Además, el acta de infracción nos causa una gran indefensión porque no refleja el nombre de las personas trabajadoras afectadas por la supuesta infracción que ha originado el acta, por lo que no podemos conocer con exactitud cuál ha sido el supuesto comportamiento infractor y, en consecuencia, proceder a desvirtuar tales afirmaciones.

[OPCIONAL — incluir si procede]

(Si el acta se limita a calificar los hechos de forma genérica)

Además, el acta de infracción califica genéricamente los hechos como [COMPLETAR], sin describir pormenorizadamente la conducta realizada por el empresario, y no se aportan los elementos de juicio necesarios, dado lo escaso del relato, para que el órgano competente sancionador pueda adoptar su decisión, ni tampoco para que el inculpado pueda defenderse de unos hechos que no se describen con el detalle necesario para poder ser calificados como constitutivos de esta infracción, tal y como reiteradamente viene exigiendo la jurisprudencia de nuestro Tribunal Supremo.

B) En cuanto al elemento subjetivo, los hechos acaecidos no son susceptibles de incardinarse en la infracción administrativa tal y como se hizo en el acta de infracción, sino que en atención a lo sucedido y a las circunstancias de hechos concurrentes no existe culpabilidad del empresario.

CUARTO.- Que la sanción impuesta, consistente en el pago de una multa en cuantía de [IMPORTE] euros, vulnera el principio de proporcionalidad y demás principios que informan el ejercicio de la potestad sancionadora en materia de infracciones en el orden social, atendiendo al relato de hechos más arriba reseñado.

Que para la demostración de las afirmaciones anteriormente manifestadas, se propone la práctica de los siguientes MEDIOS DE PRUEBA, que incomprensiblemente los órganos instructor y sancionador no admitieron con anterioridad a dictarse la resolución sancionadora: [COMPLETAR].

A los anteriores hechos son de aplicación los siguientes

FUNDAMENTOS DE DERECHO

I.- Procede la interposición del presente recurso de alzada conforme establecen los artículos 54 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, 23 del Real Decreto 928/1998, de 14 de mayo, por el que se aprueba el Reglamento General sobre Procedimientos para la Imposición de las Sanciones por Infracciones de Orden Social y para los Expedientes Liquidatorios de Cuotas de la Seguridad Social, y 121 y 122 de la Ley 39/2015, de 1 de octubre, del Procedimiento Administrativo Común de las Administraciones Públicas.

II.-

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la resolución sancionadora fue dictada por órgano incompetente / Si la resolución sancionadora es contraria al principio de tipicidad / Si la resolución sancionadora vulnera el derecho a la tutela judicial efectiva / Si la resolución sancionadora vulnera la presunción de inocencia / Si la resolución sancionadora vulnera los derechos de defensa por falta de información / Si el acta de infracción adolecía de graves irregularidades / Si se han infringido los trámites esenciales de comprobación de los hechos — el texto de cada opción no venía en el formulario original]

III.–

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (No comunicar las contrataciones realizadas)
— (No comunicar la terminación de los contratos de trabajo)
— (Incumplir las obligaciones formales o documentales no graves ni muy graves exigidas en la normativa sobre formación profesional para el empleo)
— (Incumplir las medidas de reserva, duración o preferencia en el empleo)
— (Incumplir la obligación legal de reserva de puestos de trabajo para personas con discapacidad, o de aplicación de medidas alternativas)
— (No notificar las contrataciones de duración determinada o no entregar la copia básica de los contratos a los representantes de los trabajadores)
— (Publicidad de ofertas de empleo engañosas o ilegales)
— (Incumplimiento grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo)
— (Ejercer ilegalmente actividades de intermediación laboral)
— (Establecer condiciones discriminatorias para el acceso al empleo)
— (Obtener o disfrutar indebidamente incentivos a las políticas de empleo concedidos)
— (No aplicar o desviar incentivos a las políticas de empleo concedidos)
— (Incumplimiento muy grave de las obligaciones establecidas en la normativa sobre formación profesional para el empleo)
— (Aplicar de forma indebida o no aplicar a los fines previstos las donaciones y acciones de patrocinio recibidas como alternativa a la obligación de reserva de empleo a favor de las personas con discapacidad)

[OPCIONAL — incluir si procede]

IV.- La sanción impuesta vulnera el principio de proporcionalidad establecido en el artículo 39 del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, puesto que no se adapta a la gravedad de la infracción, así como a las circunstancias de hecho concurrentes que no han sido tenidas en cuenta a la hora de graduar la multa infligida. Al no considerarse relevantes las circunstancias de graduación, la sanción debe imponerse en la cuantía inferior del grado mínimo, máxime cuando el acta de infracción no contiene una descripción detallada de tales circunstancias, incurriéndose en arbitrariedad y discrecionalidad impropia de un expediente administrativo sancionador.

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por interpuesto Recurso de Alzada con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que declare la invalidez de la resolución sancionadora impugnada y del acta de infracción, con el consiguiente archivo del expediente sancionador o, subsidiariamente y para el caso de no estimar la petición de archivo del expediente, disponga la reducción de la sanción inicialmente propuesta a la cuantía inferior de su grado mínimo, sin perjuicio de la interposición ulterior de los recursos procedentes.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
