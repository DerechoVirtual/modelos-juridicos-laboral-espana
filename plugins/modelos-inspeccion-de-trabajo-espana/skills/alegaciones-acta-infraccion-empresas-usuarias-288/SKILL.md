---
name: alegaciones-acta-infraccion-empresas-usuarias-288
description: "Redacta el escrito «Alegaciones al acta de infracción de empresas usuarias» (formulario 288 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alegaciones al acta de infracción de empresas usuarias

> Formulario 0288 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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
- Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Las graves de los arts. 19.2.b, 19.2.e, 19 ter.2.b y 19 ter.2.e se sancionan con 1.000-10.000 € (art. 40.1.c bis); el 19 ter.2.e cuenta una infracción por trabajador.

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
- [ ] Otros 9 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…LEVE:»; «…l aplicable al puesto de trabajo. GRAVE:»; «… a las autoridades españolas. MUY GRAVE:»; «…al y como sucedieron son los siguientes:»; «…nfracción no son ciertos, por cuanto que»; «…n califica genéricamente los hechos como»; «…consistente en que se tome declaración a»; «…s escritos que se acompañan como números»; «… procedentes. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- artículo 19, apartado 1, / artículo 19, apartado 2, / artículo 19, apartado 3, / artículo 19 ter, apartado 1, / artículo 19 ter, apartado 2, / artículo 19 ter, apartado 3, / artículo 19 quater
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

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

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

### Formulario 0288 · Alegaciones al acta de infracción de empresas usuarias

- Año del modelo: 2017
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 5 bloques de alternativas señalados; 4 párrafos opcionales señalados; 18 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Alegaciones: 15 días hábiles ante el órgano instructor (art. 17.1 RD 928/1998; art. 52.1.b LISOS). Si la sanción es solo pecuniaria, en el mismo plazo cabe pagar con reducción del 40 % renunciando a recursos (arts. 14.6 y 17.1). El expediente caduca a los 6 meses desde la fecha del acta hasta la notificación de la resolución (art. 20.3). · Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Las graves de los arts. 19.2.b, 19.2.e, 19 ter.2.b y 19 ter.2.e se sancionan con 1.000-10.000 € (art. 40.1.c bis); el 19 ter.2.e cuenta una infracción por trabajador.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO COMPETENTE PARA SANCIONAR POR RAZÓN DE LA MATERIA, ARTS. 48 Y 52.1 b) LISOS
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de escrito de alegaciones, ante el órgano competente para dictar resolución, en el caso de acta de infracción leve, grave o muy grave de las empresas usuarias, por las siguientes causas establecidas en el artículo 19, 19 ter o 19 quater de la LISOS, con solicitud de sobreseimiento del expediente sancionador o, subsidiariamente, reducción de la sanción:

- No cumplimentar el contrato de puesta a disposición

- No facilitar los datos relativos a la retribución total aplicable al puesto de trabajo

- No formalizar por escrito el contrato de puesta a disposición

- Formalizar contratos de puesta a disposición para supuestos no previstos o sin realizar la previa evaluación de riesgos

- Impedir a los trabajadores el ejercicio de los derechos legales

- Falta de información al trabajador temporal

- Formalizar contratos de puesta a disposición para cubrir puestos o funciones que hayan sido amortizados, o ya cubiertos por trabajadores puestos a disposición

- Permitir el inicio de la prestación de servicios de trabajadores puestos a disposición sin haber recibido información sobre riesgos y medidas preventivas, poseer la formación necesaria y tener un estado de salud compatible con el puesto de trabajo

- Actos del empresario lesivos del derecho de huelga

- Formalizar contratos de puesta a disposición para la realización de trabajos u ocupaciones peligrosos para la seguridad o la salud

- No facilitar la información a la ETT con la antelación suficiente sobre el inicio de un envío temporal de una persona trabajadora desplazada a otro Estado miembro de la Unión Europea o signatario del Acuerdo del Espacio Económico Europeo

- No facilitar información a la ETT establecida en otro Estado miembro de la Unión Europea o signatario del Acuerdo sobre el Espacio Económico Europeo sobre el inicio del envío temporal de una persona trabajadora desplazada a España, con la antelación suficiente para que dicha empresa pueda comunicar el desplazamiento a las autoridades españolas

- Formalizar contratos de puesta a disposición con ETTs que no estén válidamente constituidas como tales según la legislación del Estado de establecimiento o que no reúnan los requisitos exigidos por la citada legislación para poner a disposición de empresas usuarias, con carácter temporal, personas trabajadoras por ellas contratadas

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada el acta de infracción número [NÚMERO], con la que no estoy de acuerdo con el relato de hechos en los términos descritos, ni con su calificación jurídica, ni con la propuesta de sanción en la misma contenida, por lo que, dentro del plazo de quince días hábiles concedido al efecto, formulo el presente ESCRITO DE ALEGACIONES en base a los siguientes hechos y fundamentos de derecho:

HECHOS

PRIMERO.- Que con fecha [FECHA] se dictó acta de infracción número en la que se propone una multa de [IMPORTE] euros, ya que, de conformidad con el [ELEGIR: artículo 19, apartado 1, / artículo 19, apartado 2, / artículo 19, apartado 3, / artículo 19 ter, apartado 1, / artículo 19 ter, apartado 2, / artículo 19 ter, apartado 3, / artículo 19 quater] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

LEVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No cumplimentar el contrato de puesta a disposición.

No facilitar los datos relativos a la retribución total aplicable al puesto de trabajo.

GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

No formalizar por escrito el contrato de puesta a disposición.

Formalizar contratos de puesta a disposición para supuestos no previstos o sin realizar la previa evaluación de riesgos.

Impedir a los trabajadores el ejercicio de los derechos legales.

Falta de información al trabajador temporal.

Formalizar contratos de puesta a disposición para cubrir puestos o funciones que hayan sido amortizados, o ya cubiertos por trabajadores puestos a disposición.

Permitir el inicio de la prestación de servicios de trabajadores puestos a disposición sin haber recibido información sobre riesgos y medidas preventivas, poseer la formación necesaria y tener un estado de salud compatible con el puesto de trabajo.

Formalizar contratos de puesta a disposición para la cobertura de puestos de trabajo respecto de los que no se haya realizado previamente la preceptiva evaluación de riesgos.

No facilitar la información a la ETT con la antelación suficiente sobre el inicio de un envío temporal de una persona trabajadora desplazada a otro Estado miembro de la Unión Europea o signatario del Acuerdo del Espacio Económico Europeo.

No facilitar información a la ETT establecida en otro Estado miembro de la Unión Europea o signatario del Acuerdo sobre el Espacio Económico Europeo sobre el inicio del envío temporal de una persona trabajadora desplazada a España, con la antelación suficiente para que dicha empresa pueda comunicar el desplazamiento a las autoridades españolas.

MUY GRAVE: [COMPLETAR]

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Actos del empresario lesivos del derecho de huelga.

Formalizar contratos de puesta a disposición para la realización de trabajos u ocupaciones peligrosos para la seguridad o la salud.

Formalizar contratos de puesta a disposición con ETTs que no estén válidamente constituidas como tales según la legislación del Estado de establecimiento o que no reúnan los requisitos exigidos por la citada legislación para poner a disposición de empresas usuarias, con carácter temporal, personas trabajadoras por ellas contratadas.

SEGUNDO.- Que, en el acta de infracción arriba referenciada, se reflejan unos hechos que no responden a la realidad de lo acaecido, al no describirse pormenorizadamente el supuesto comportamiento infractor, ni destacar cuáles son los hechos relevantes a efectos de la tipificación y graduación de la sanción. En concreto, los hechos tal y como sucedieron son los siguientes: [COMPLETAR].

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

III.- Notificada el acta de infracción el día [FECHA], se formula el presente escrito de alegaciones dentro del indicado plazo de quince días.

IV.-

[ELEGIR UNA DE ESTAS ALTERNATIVAS Y SUPRIMIR LAS DEMÁS:]
— (No cumplimentar el contrato de puesta a disposición)
— (No facilitar los datos relativos a la retribución total aplicable al puesto de trabajo)
— (No formalizar por escrito el contrato de puesta a disposición)
— (Formalizar contratos de puesta a disposición para supuestos no previstos o sin realizar la previa evaluación de riesgos)
— (Impedir a los trabajadores el ejercicio de los derechos legales)
— (Falta de información al trabajador temporal)
— (Formalizar contratos de puesta a disposición para cubrir puestos o funciones que hayan sido amortizados, o ya cubiertos por trabajadores puestos a disposición)
— (Permitir el inicio de la prestación de servicios de trabajadores puestos a disposición sin haber recibido información sobre riesgos y medidas preventivas, poseer la formación necesaria y tener un estado de salud compatible con el puesto de trabajo)
— (Formalizar contratos de puesta a disposición para la cobertura de puestos de trabajo respecto de los que no se haya realizado previamente la preceptiva evaluación de riesgos)
— (Actos del empresario lesivos del derecho de huelga)
— (Formalizar contratos de puesta a disposición para la realización de trabajos u ocupaciones peligrosos para la seguridad o la salud)
— (No facilitar la información a la ETT sobre el inicio del envío temporal de una persona trabajadora desplazada a España, con la antelación suficiente para que dicha empresa pueda comunicar el desplazamiento a las autoridades españolas)

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por presentado este escrito de alegaciones con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que se deje sin efecto el acta de infracción y, en consecuencia, acuerde el sobreseimiento del expediente sancionador o, subsidiariamente y para el caso de no estimar la petición de archivo del expediente, disponga la reducción de la sanción inicialmente propuesta a la cuantía inferior de su grado mínimo, sin perjuicio de la interposición ulterior de los recursos procedentes.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
