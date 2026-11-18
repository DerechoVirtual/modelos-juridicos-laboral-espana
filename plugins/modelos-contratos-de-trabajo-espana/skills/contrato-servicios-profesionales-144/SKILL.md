---
name: contrato-servicios-profesionales-144
description: "Redacta el escrito «Contrato de servicios profesionales» (formulario 144 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato de servicios profesionales

> Formulario 0144 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (5 veces)
- [ ] DNI/NIE (2 veces)
- [ ] NIF
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (2 veces)
- [ ] NÚMERO
- [ ] IMPORTE
- [ ] Nº (5 veces)
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a la prevención de riesgos laborales) En»; «…, quien interviene en su condición de»; «…y representante legal de la mercantil»; «…otorgada ante el Notario de»; «… el presente contrato MANIFIESTAN I. Que»; «…ión de los servicios profesionales de un»; «…, para el desarrollo de»; «…, profesional de»; «…el ámbito de dirección y organización de»; «… la Empresa al Profesional dentro de los»; «…ad equivalente a los honorarios fijos de»

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- El trabajador autónomo declara que ha recibido y ha comprendido la información facilitada por la empresa de lo…
- Si el trabajador autónomo contratare trabajadores por cuenta ajena deberá comunicarlo de inmediato a la empres…
- El autónomo no podrá subcontratar con otros trabajadores autónomos o con otra empresa la realización de los tr…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 1544 del Código Civil

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

### Formulario 0144 · Contrato de servicios profesionales

- Año del modelo: 2022
- Revisión 17-11-2026: 3 párrafos opcionales señalados; 31 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
MANIFIESTAN
CLÁUSULAS
Firmas

Contratación de servicios profesionales de un trabajador autónomo por parte de una empresa (incluye cláusulas relativas a la prevención de riesgos laborales)

En [COMPLETAR]

REUNIDOS

De una parte,

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE], quien interviene en su condición de [COMPLETAR] y representante legal de la mercantil [COMPLETAR], con NIF nº [NIF], y domicilio en [LOCALIDAD], según consta en la escritura de poder de fecha [FECHA] otorgada ante el Notario de [COMPLETAR] con el nº [NÚMERO] de su protocolo (en adelante la Empresa)

Y, de otra parte,

D./Dña. [NOMBRE Y APELLIDOS], con DNI nº [DNI/NIE] y domicilio en [LOCALIDAD], actuando en su propio nombre y derecho (en adelante, el Profesional).

Ambas partes reconociéndose mutuamente la capacidad legal necesaria para otorgar el presente contrato

MANIFIESTAN

I. Que [COMPLETAR] está interesada en la contratación de los servicios profesionales de un [COMPLETAR], para el desarrollo de [COMPLETAR].

II. Que D./Dña. [NOMBRE Y APELLIDOS], profesional de [COMPLETAR], está cualificado y tiene los conocimiento y la experiencia necesarios para la prestación de los servicios que interesan a la Empresa, y estando dado de alta en el correspondiente epígrafe fiscal y en el Régimen Especial de Trabajadores Autónomos, está interesado en llevar a cabo las referidas funciones y actividades profesionales objeto de este contrato como trabajador autónomo.

Y, a tal efecto, convienen la formalización del presente contrato de arrendamiento de servicios, al amparo del art. 1544 del Código Civil, que se regirá por las siguientes

CLÁUSULAS

PRIMERA.- Constituye el objeto del presente contrato la prestación de servicios por parte del Profesional consistentes en:

El Profesional se obliga a desarrollar dichas labores con diligencia y atención propia de su condición profesional, por cuenta propia y fuera del ámbito de dirección y organización de [COMPLETAR].

En ningún momento podrá entenderse que la firma del presente contrato significa el establecimiento de una relación laboral alguna entre el Profesional y la Empresa.

SEGUNDA.- Los Honorarios correspondientes a los servicios objeto del presente contrato consisten en una cantidad fija de [IMPORTE] euros brutos mensuales. Sobre dicha cantidad se practicará la retención dispuesta por Ley a cuenta del Impuesto sobre la Renta de las Personas Físicas, y a su vez se verá incrementada por el porcentaje en cada momento vigente, correspondiente al Impuesto sobre el Valor Añadido.

La remuneración fija se abonará mensualmente por la Empresa al Profesional dentro de los [COMPLETAR] primeros días de cada mes, a cuyo efecto el Profesional emitirá la correspondiente factura a la Empresa en la que consignará la retención a cuenta del IRPF y el IVA correspondiente.

El precio pactado podrá ser revisado, previo acuerdo entre las partes si, durante la prestación de los servicios objeto de este contrato, se produjeran cambios imprevistos que afecten sustancialmente a su ejecución.

Todos los gastos derivados de la actividad objeto de este contrato serán a cargo y por cuenta exclusiva del Profesional.

TERCERA.- Este contrato tendrá una duración de [Nº] años, comenzando sus efectos con fecha [FECHA]. Llegada la fecha de finalización, el contrato se renovará automáticamente, por períodos de [Nº] años, de no mediar un preaviso de tres meses por alguna de las partes.

CUARTA.- Cualquiera de las partes podrá desistir de este contrato en cualquier momento, comunicándolo por escrito con un preaviso de [Nº] meses. Ambas partes renuncian a cualquier tipo de indemnización en caso de desistimiento del contrato.

No obstante lo anterior, en el caso de que la extinción contractual traiga su causa de un incumplimiento del contrato, la parte que haya incumplido sus obligaciones correrá con todos los gastos que ello origine.

QUINTA.- La Empresa se obliga desde este momento a facilitar al Profesional cuanta documentación, datos, informes y antecedentes se encuentren a su disposición necesarios para la realización de los trabajos que le son encomendados.

SEXTA.- El Profesional se compromete a la prestación del servicio, de forma personal, realizándolo a plena satisfacción de la Empresa contratante, en relación a su especialidad, cualidades y pericia.

En el ejercicio de su actividad profesional el Profesional deberá actuar lealmente y de buena fe velando por los intereses de la Empresa. Asimismo, la Empresa, en sus relaciones con el Profesional, también deberá actuar lealmente y de buena fe.

SÉPTIMA.- El Profesional no podrá durante la vigencia del contrato, ni en los [Nº] años siguientes a la finalización del mismo, usar o revelar directa o indirectamente para sus propios fines o para los de un tercero, ninguna información comercial o confidencial, relacionada o perteneciente a la Empresa, incluyendo pero no limitado a cualquier información relativa a clientes o proveedores, listas de clientes o proveedores, sus requerimientos, listas o estructuras de precios, informaciones de ventas o marketing, planes de negocio, empleados, información financiera, diseños, actividades de I+D o cualquier otra información considerada como confidencial.

Si el Profesional incumpliera lo expuesto en el párrafo anterior indemnizará a la Empresa por daños y perjuicios en una cantidad equivalente a los honorarios fijos de [COMPLETAR].

OCTAVA.- El Profesional acepta que durante la vigencia del presente contrato todas las invenciones, descubrimientos, mejoras, patentes, marcas, nombres comerciales y cualesquiera otros derechos industriales y/o intelectuales desarrollados o concebidos por él o conjuntamente con otros que se produzcan como consecuencia de sus servicios, serán propiedad de la Empresa con el consiguiente derecho de uso de los mismos.

El Profesional acepta que durante los [Nº] años posteriores a la terminación del presente contrato, todos los derechos intelectuales y/o industriales que se deriven los conocimientos adquiridos durante el desempeño de su actividad profesional en la Empresa serán propiedad de la misma.

NOVENA.- En los casos que la Empresa tenga acceso a ficheros que contengan datos de carácter personal, se aplicará la presente cláusula que tiene por objeto establecer, de conformidad con lo previsto en la Ley Orgánica de Protección de Datos de Carácter Personal, las obligaciones y responsabilidades de las partes intervinientes respecto de los datos de carácter personal contenidos en los ficheros de los clientes de la Empresa (en adelante lo ficheros) a los cuales el Profesional tenga acceso para el cumplimiento de los servicios objeto del presente contrato.

Ambas partes asumen las responsabilidades que puedan corresponderles, derivadas de la legislación vigente sobre protección de datos de carácter personal, específicamente de la legislación citada en el párrafo anterior y muy especialmente en relación a los pactos prevenidos en los párrafos siguientes.

El acceso a los ficheros de los clientes no tiene la consideración legal de comunicación o cesión de datos sino de simple acceso a los mismos como elemento necesario para la realización de los servicios contractualmente establecidos.

Los ficheros son propiedad exclusiva de la Empresa, extendiéndose también esta titularidad a cuantas elaboraciones, evaluaciones, segmentaciones o procesos similares que, en relación con los mismos, pudiera realizar la Empresa de acuerdo con los servicios pactados, declarando las partes que estos ficheros son confidenciales a todos los efectos, sujetos en consecuencia al más estricto secreto profesional, incluso una vez finalizada la relación contractual.

El Profesional, en relación con los ficheros, se obliga expresamente a:

a) Utilizar o aplicar los datos personales exclusivamente para la realización de los servicios contractualmente pactados, de acuerdo con las instrucciones impartidas, siempre que estén de acuerdo con la Ley.
b) No comunicarlos, ni siquiera a efectos de su conservación a otras personas ni tampoco las elaboraciones, evaluaciones o procesos similares citados anteriormente, ni duplicar o reproducir todo o parte de la información, resultados o relaciones sobre los mismos.

DÉCIMA.- El Profesional acepta que todos sus datos relativos a su relación mercantil con la Empresa y todos sus datos personales serán centralizados en la base de datos de Proveedores y Acreedores a la que sólo tendrá acceso el personal debidamente autorizado por la Empresa de conformidad con la Ley de Protección de Datos.

UNDÉCIMA.-

[OPCIONAL — incluir si procede]

El trabajador autónomo declara que ha recibido y ha comprendido la información facilitada por la empresa de los riesgos existentes en el centro de trabajo de esta, las medidas de emergencia que tiene que adoptar y las instrucciones necesarias para realizar su trabajo en condiciones de seguridad.

El trabajador autónomo, con carácter previo al inicio de sus trabajos, deberá acreditar:

- Haber realizado la evaluación de riesgos correspondientes a sus tareas y en su caso a requerimiento de la empresa una evaluación de riesgos específica en la que se contemple los riesgos derivados del ejercicio de su actividad en el centro de trabajo de la empresa.

- Tener la formación preventiva adecuada y suficiente para el desempeño de su trabajo. Esta formación será equiparable a la que debiera tener un trabajador por cuenta ajena que realizara el mismo trabajo.

- Ser apto desde el punto de vista médico para el desempeño de su trabajo. El certificado de aptitud deberá ser expedido por un médico especialista en medicina del trabajo.

- Que los equipos de trabajo por él utilizada tienen marcado CE o el correspondiente certificado de adecuación.

[OPCIONAL — incluir si procede]

Si el trabajador autónomo contratare trabajadores por cuenta ajena deberá comunicarlo de inmediato a la empresa quien establecerá los requisitos que en materia de prevención de riesgos laborales deberá cumplir. Mientras no se cumplan estos requisitos, el trabajador contratado por el autónomo no podrá acceder al centro de trabajo de la empresa ni realizar ningún tipo de trabajo.

[OPCIONAL — incluir si procede]

El autónomo no podrá subcontratar con otros trabajadores autónomos o con otra empresa la realización de los trabajos objeto de este contrato.

DUODÉCIMA.- Se considera como causa suficiente para la resolución del presente contrato:

— El incumplimiento por parte del AUTÓNOMO de sus obligaciones fiscales y en materia de Seguridad Social.
— El incumplimiento de las obligaciones en materia de prevención de riesgos laborales recogidas en la estipulación undécima de este contrato.

DECIMOTERCERA.- En todo lo no previsto en el presente contrato se estará a lo establecido en el Código Civil y demás normas de aplicación.

DECIMOCUARTA.- Las partes con renuncia al fuero que pudiera corresponderles se someten a la jurisdicción de los Tribunales de [LOCALIDAD].

Y en prueba de conformidad ambas partes extienden y suscriben, por duplicado ejemplar, el presente contrato, en el lugar y fecha referenciados en el encabezamiento.

EL PROFESIONAL

LA EMPRESA

Firmado: D./Dña. [NOMBRE Y APELLIDOS] 	Firmado: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
