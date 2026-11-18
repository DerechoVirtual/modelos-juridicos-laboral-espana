---
name: confidencialidad-control-medios-desconexion-digital-173
description: "Redacta el escrito «Confidencialidad, control de medios y desconexión digital: cláusula» (formulario 173 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Confidencialidad, control de medios y desconexión digital: cláusula

> Formulario 0173 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Desconexión: política interna previa audiencia de la RLT (art. 88.3 LOPDGDD); criterios de uso de dispositivos con participación de la RLT (art. 87.3).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de la relación que le une con la ENTIDAD»; «… devolver dichos materiales a la ENTIDAD»; «…pactada y sin conocimiento de la ENTIDAD»; «…., salvo autorización expresa de ENTIDAD»; «…e los sistemas de información en ENTIDAD»; «…os informáticos y telemáticos de ENTIDAD»; «…ausa de fuerza mayor. He sido informado:»; «…Fecha:»

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 5 de la Ley Orgánica 3/2018
- artículo 87 de la Ley Orgánica 3/2018
- artículo 88 de la Ley Orgánica 3/2018

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

### Formulario 0173 · Confidencialidad, control de medios y desconexión digital: cláusula

- Año del modelo: 2020
- Revisión 17-11-2026: 2 puntualizaciones normativas añadidas en el texto; 7 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Desconexión: política interna previa audiencia de la RLT (art. 88.3 LOPDGDD); criterios de uso de dispositivos con participación de la RLT (art. 87.3).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Encabezamiento
Obligación de secreto
Están expresamente prohibidas las siguientes actividades:
Protección de la intimidad
Incumplimiento de contrato
Desconexión digital
Firmas

La Cláusula de Confidencialidad garantiza la protección de información sensible manejada por las personas trabajadoras, promoviendo la confianza y seguridad de los datos empresariales. En cuanto a la Información sobre Control de Medios especifica las políticas de supervisión de los recursos tecnológicos proporcionados al personal, asegurando transparencia en su uso. Finalmente, el Derecho a la Desconexión Digital detalla los derechos de los empleados a desconectarse de las tecnologías laborales fuera del horario de trabajo, promoviendo un mejor equilibrio entre vida laboral y personal y protegiendo la salud mental de las personas trabajadoras.

El abajo firmante, en el marco de la relación que le une con la ENTIDAD [COMPLETAR] para el desarrollo de sus funciones en el centro donde presta sus servicios, se da por informado y se compromete a observar la siguiente cláusula de confidencialidad en cumplimiento de la normativa que regula tanto las relaciones laborales como la protección de datos personales (artículo 5 de la Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales);

1. En el caso de que, por motivos relacionados con el puesto desempeñado, entre en posesión de información, de forma verbal, o a través de documentos que tenga a su alcance, que pudieran contener datos personales o información confidencial o estratégica, deberá entenderse que dicha posesión es estrictamente temporal, con obligación de secreto y sin que ello le conceda derecho alguno de posesión, o titularidad o copia sobre la referida información, y sin que pueda ser comunicada a terceros. Asimismo, el usuario deberá devolver dichos materiales a la ENTIDAD [COMPLETAR] inmediatamente después de la finalización de las tareas que han originado el uso temporal de los mismos, y, en cualquier caso, a la finalización de la relación que le haya unido a la Corporación. La utilización continuada de la información en cualquier formato o soporte de forma distinta a la pactada y sin conocimiento de la ENTIDAD [COMPLETAR] no supondrá, en ningún caso, una modificación de esta cláusula. El incumplimiento de esta obligación puede constituir incluso un delito de revelación de secretos.

2. Están expresamente prohibidas las siguientes actividades:

– Incluir o crear ficheros paralelos, sin autorización, que contengan datos personales en el disco duro del ordenador del usuario, en la nube corporativa, en memorias USB, CD o DVD-ROM, etc., salvo autorización expresa de ENTIDAD [COMPLETAR].

– Extraer del centro de trabajo, sin la correspondiente autorización, cualquier documento, en cualquier soporte.

3.- El artículo 87 de la Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales reconoce a los trabajadores el derecho a la protección de su intimidad en el uso de los dispositivos digitales puestos a su disposición por su empleador, si bien, el precepto señala que éste podrá acceder a los contenidos derivados del uso de medios digitales facilitados a los trabajadores a los solos efectos de controlar el cumplimiento de las obligaciones laborales o estatutarias y de garantizar la integridad de dichos dispositivos. Es por ello, que en la organización se han establecido unos criterios de utilización de los dispositivos digitales y unas normas de uso de los sistemas de información en ENTIDAD [COMPLETAR], de las que se informa expresamente en documento independiente [NOTA DE REVISIÓN: Art. 87.3 LOPDGDD: los criterios de utilización se elaboran con participación de la RLT; si se admite el uso privado, hay que precisar los usos autorizados y las garantías de intimidad. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 87.3.].

En todo caso, la Gerencia recuerda que está expresamente prohibido utilizar los recursos informáticos y telemáticos de ENTIDAD [COMPLETAR], incluidos Internet y el correo electrónico, para actividades que no se hallen directamente relacionadas con el puesto de trabajo del usuario. En este sentido, la empresa se reserva la posibilidad de adoptar las medidas que estime más oportunas de vigilancia y control (como revisiones de los equipos o del servidor de correo electrónico) para verificar el cumplimiento por el usuario de sus obligaciones y deberes (laborales o equivalentes), con los límites establecidos por la Ley y la jurisprudencia.

4.- Consecuentemente, el uso reiterado y abusivo de los recursos de la Corporación, para fines particulares y ajenos a la labor profesional podrá suponer un quebranto de la buena fe contractual, así como un abuso de confianza en el desempeño del trabajo, constituyendo un incumplimiento grave y culpable del contrato de trabajo.

5.-Se reconoce el derecho a la desconexión digital, conforme establece el artículo 88 de la Ley Orgánica 3/2018 [NOTA DE REVISIÓN: El art. 88 LOPDGDD remite la forma de ejercicio a la negociación colectiva o al acuerdo con la RLT y exige una política interna previa audiencia de la RLT (88.3). La cláusula individual no la sustituye. Concordante: art. 20 bis ET. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 88; RDLeg 2/2015 (ET), BOE-A-2015-11430, art. 20 bis.], de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales. Por esta razón se establece que las personas trabajadoras tienen derecho a no responder cualquier tipo de comunicación por cualquier canal (correo electrónico, teléfono, WhatsApp, redes sociales, etcétera) fuera de su horario de trabajo salvo causa de fuerza mayor.

He sido informado: [COMPLETAR]

Fecha: [COMPLETAR]

Firma: D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
