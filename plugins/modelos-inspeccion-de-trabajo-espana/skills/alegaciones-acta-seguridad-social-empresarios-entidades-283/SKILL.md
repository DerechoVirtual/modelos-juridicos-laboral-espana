---
name: alegaciones-acta-seguridad-social-empresarios-entidades-283
description: "Redacta el escrito «Alegaciones al acta de Seguridad Social (empresarios, entidades de formación y autónomos)» (formulario 283 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Alegaciones al acta de Seguridad Social (empresarios, entidades de formación y autónomos)

> Formulario 0283 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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
- Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Especialidades: 22.2 (una infracción por trabajador) con multa de 3.750-12.000 € y 23.1.a con 12.001-225.018 €, más incrementos del 20-50 % si hay varios trabajadores (art. 40.1.e); 22.3, 23.1.b y 23.1.k en porcentaje de lo no ingresado (art. 40.1.d); grado por cuantía (art. 39.2).

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
- [ ] NÚMERO (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] DESCRIBIR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, ya que, de conformidad con el artículo»; «…al y como sucedieron son los siguientes:»; «…nfracción no son ciertos, por cuanto que»; «…n califica genéricamente los hechos como»; «…consistente en que se tome declaración a»; «…s escritos que se acompañan como números»; «… procedentes. Es de Justicia que pide en»

## Elecciones que hay que hacer

- en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña
- personas trabajadoras / clientes

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la infracción es leve / Si la infracción es grave / Si la infracción es muy grave — el texto de cada opción no venía en el formulario original
- ELEGIR UNA OPCIÓN Y REDACTARLA: Si la infracción es leve / Si la infracción es grave / Si la infracción es muy grave — el texto de cada opción no venía en el formulario original

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

### Formulario 0283 · Alegaciones al acta de Seguridad Social (empresarios, entidades de formación y autónomos)

- Año del modelo: 2017
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 2 bloques de opciones sin texto dejados en blanco con sus rótulos; 4 párrafos opcionales señalados; 20 campos de relleno marcados en blanco
- Avisos de la revisión: Alegaciones: 15 días hábiles ante el órgano instructor (art. 17.1 RD 928/1998; art. 52.1.b LISOS). Si la sanción es solo pecuniaria, en el mismo plazo cabe pagar con reducción del 40 % renunciando a recursos (arts. 14.6 y 17.1). El expediente caduca a los 6 meses desde la fecha del acta hasta la notificación de la resolución (art. 20.3). · Cuantías vigentes (art. 40.1 LISOS, red. RDL 32/2021): leves 70-750 €; graves 751-7.500 €; muy graves 7.501-225.018 €. Especialidades: 22.2 (una infracción por trabajador) con multa de 3.750-12.000 € y 23.1.a con 12.001-225.018 €, más incrementos del 20-50 % si hay varios trabajadores (art. 40.1.e); 22.3, 23.1.b y 23.1.k en porcentaje de lo no ingresado (art. 40.1.d); grado por cuantía (art. 39.2).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

AL ÓRGANO COMPETENTE PARA SANCIONAR POR RAZÓN DE LA MATERIA, ARTS. 48 Y 52.1 b) LISOS
HECHOS
FUNDAMENTOS DE DERECHO
Firmas

Modelo de escrito de alegaciones, ante el órgano competente para dictar resolución, en el caso de acta de infracción, por las siguientes causas establecidas en el artículo 21, 22 o 23 de la LISOS, con solicitud de sobreseimiento del expediente sancionador o, subsidiariamente, reducción de la sanción:

- No conservar la documentación o los registros o soportes informáticos

- No exponer, poner a disposición o entregar los documentos de cotización

- No comunicar las bajas o variaciones de los trabajadores o su no transmisión por medios informáticos, electrónicos o telemáticos

- No cumplir el deber de información

- No comunicar el cambio en los documentos de asociación o de adhesión

- No remitir a la entidad las copias de los partes médicos de baja, confirmación de la baja o alta de incapacidad temporal facilitadas por los trabajadores, o no transmitirlos por medios informáticos, electrónicos o telemáticos

- No solicitar la inscripción, no comunicar la apertura y cese de actividad de los centros de trabajo y demás variaciones, o su no transmisión

- No solicitar o solicitar fuera de plazo la afiliación inicial o el alta de los trabajadores a su servicio

- Falta de ingreso total o parcial de las cuotas, habiendo cumplido las obligaciones de solicitud y transmisión de liquidaciones

- Incumplir las obligaciones económicas derivadas de su colaboración obligatoria

- Formalizar la protección por accidentes de trabajo y enfermedades profesionales, incapacidad temporal o la protección por cese de actividad, en entidad distinta

- Falta de entrega o no transmisión de documentos precisos para solicitar y tramitar cualquier prestación, incluido el certificado de empresa

- Falta de solicitud de afiliación o alta en el Régimen Especial de Trabajadores Autónomos

- Falta de abono de prestaciones a las entidades por las empresas responsables de su pago

- Obtener o disfrutar indebidamente cualquier tipo de reducciones, bonificaciones o incentivos en relación las cuotas sociales

- Solicitud de afiliación o alta fuera de plazo de los trabajadores a su servicio cuando no medie actuación inspectora, o su no transmisión

- No comprobar los empresarios que contraten o subcontraten con otros la afiliación o alta de los trabajadores

- No proceder al alta y cotización por los salarios de tramitación y por las vacaciones devengadas y no disfrutadas antes de la extinción de la relación laboral

- No comunicar a la entidad gestora de la prestación por desempleo las medidas de despido colectivo o de suspensión o reducción de jornada

- Ocupar a beneficiarios de pensiones incompatibles con el trabajo por cuenta ajena

- Incumplir las entidades de formación u organizadoras los requisitos de las acciones formativas

- Comunicar la baja en un régimen de la Seguridad Social de trabajadores por cuenta ajena pese a que continúen la misma actividad laboral o mantengan idéntica prestación de servicios, sirviéndose de un alta indebida en un régimen de trabajadores por cuenta propia

- Ocupar a beneficiarios o solicitantes de pensiones incompatibles con el trabajo por cuenta ajena

- No ingresar ni liquidar las cuotas de Seguridad Social, o actuar fraudulentamente para eludir esa responsabilidad

- Falsear documentos o la connivencia con los trabajadores para la obtención o disfrute fraudulento de prestaciones de la Seguridad Social o eludir obligaciones

- Pactar con sus trabajadores que paguen cuotas a cargo del empresario, o su renuncia a derechos de Seguridad Social

- Incremento indebido de la base de cotización o simulación de la contratación laboral

- Efectuar deducciones o compensaciones fraudulentas en las cuotas

- No facilitar los datos identificativos de prestaciones sociales públicas

- Falsear documentos para obtener o disfrutar indebidamente de bonificaciones en materia de formación profesional para el empleo

- No suscribir el convenio especial de trabajadores con 55 o más años afectados por un despido colectivo

- Ocupar trabajadores afectados por la suspensión de contratos o reducción de jornada

- Retener o descontar de más indebidamente, y no ingresar en plazo, la parte de cuota de Seguridad Social de sus trabajadores

- Incumplir lo dispuesto en los Reglamentos de la Unión Europea sobre Coordinación de Sistemas de Seguridad Social, respecto a la determinación de la legislación de seguridad social aplicable, cuando dicho incumplimiento dé lugar a la inscripción o alta en el sistema de seguridad social español de empresas, trabajadores por cuenta ajena o por cuenta propia, o dé lugar a la falta de alta y cotización en el sistema de seguridad social español de personas desplazadas a España desde otro Estado Miembro de la UE.

AL [ÓRGANO AL QUE SE DIRIGE]

D./Dña. [NOMBRE Y APELLIDOS], con NIF/NIE número [DNI/NIE] y domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], actuando [ELEGIR: en su propio nombre / en nombre de ..., cuya representación acredita conforme a la escritura de poder cuya copia acompaña], como mejor proceda comparece y DICE:

Que el día [FECHA] me ha sido notificada el acta de infracción número [NÚMERO], con la que no estoy de acuerdo con el relato de hechos en los términos descritos, ni con su calificación jurídica, ni con la propuesta de sanción en la misma contenida, por lo que, dentro del plazo de quince días hábiles concedido al efecto, formulo el presente ESCRITO DE ALEGACIONES en base a los siguientes hechos y fundamentos de derecho:

HECHOS

PRIMERO.- Que con fecha [FECHA] se dictó acta de infracción número [NÚMERO] en la que se propone una multa de [IMPORTE] euros, ya que, de conformidad con el artículo [COMPLETAR] del Real Decreto Legislativo 5/2000, de 4 de agosto, por el que se aprueba el texto refundido de la Ley sobre Infracciones y Sanciones en el Orden Social, los hechos descritos han sido calificados como constitutivos de la siguiente infracción

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la infracción es leve / Si la infracción es grave / Si la infracción es muy grave — el texto de cada opción no venía en el formulario original]

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

[ELEGIR UNA OPCIÓN Y REDACTARLA: Si la infracción es leve / Si la infracción es grave / Si la infracción es muy grave — el texto de cada opción no venía en el formulario original]

En virtud de lo expuesto,

SOLICITA DE ESE que, tenga por presentado este escrito de alegaciones con los documentos que se acompañan y, previa la práctica de las pruebas propuestas y la tramitación que proceda, dicte resolución en la que se deje sin efecto el acta de infracción y, en consecuencia, acuerde el sobreseimiento del expediente sancionador o, subsidiariamente y para el caso de no estimar la petición de archivo del expediente, disponga la reducción de la sanción inicialmente propuesta a la cuantía inferior de su grado mínimo, sin perjuicio de la interposición ulterior de los recursos procedentes.

Es de Justicia que pide en [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
