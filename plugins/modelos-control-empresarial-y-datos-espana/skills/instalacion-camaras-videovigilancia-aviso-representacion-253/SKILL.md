---
name: instalacion-camaras-videovigilancia-aviso-representacion-253
description: "Redacta el escrito «Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores» (formulario 253 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores

> Formulario 0253 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

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

- Además de informar (art. 89.1 LOPDGDD), el comité emite informe previo sobre sistemas de control del trabajo (art. 64.5.f ET) en 15 días (art. 64.6 ET).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 2 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…resente les informamos de que la empresa»; «… de datos de la Empresa, en la dirección»

## Correcciones de la revisión (7)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 20.3 del Estatuto de los Trabajadores
- art. 22 LOPDGDD
- artículo 89 LOPDGDD
- artículo 64.1 ET
- art. 12 RGPD
- artículos 15 a 22 RGPD
- Ley Orgánica 3/2018

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

### Formulario 0253 · Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores

- Año del modelo: 2018
- Revisión 17-11-2026: 7 citas normativas corregidas tras comprobarlas en el BOE; 4 campos de relleno marcados en blanco
- Avisos de la revisión: Además de informar (art. 89.1 LOPDGDD), el comité emite informe previo sobre sistemas de control del trabajo (art. 64.5.f ET) en 15 días (art. 64.6 ET).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Información y finalidad
Tratamiento de datos de imágenes
Deber de informar a los representantes de los trabajadores
Firmas

La LOPDGDD obliga a informar con carácter previo a los representantes de los trabajadores sobre la instalación de sistemas de videovigilancia. También a los trabajadores debiendo instalarse además un cartel informativo. En base al RGPD y doctrina judicial debe informarse claramente sobre la finalidad: las funciones de control empresarial sólo pueden satisfacer un derecho o un interés legítimo del empleador. Si se pretende una finalidad sancionadora ante un incumplimiento del trabajador este punto debe ser informado por el empleador. Admás, la medida de control sólo será válida si supera el juicio de proporcionalidad (idoneidad, necesidad y proporcionalidad).

Por medio de la presente les informamos de que la empresa [COMPLETAR], va a proceder a la instalación de cámaras de videovigilancia en el centro de trabajo, de acuerdo con lo establecido en el Reglamento (UE) 2016/679 del Parlamento Europeo y del Consejo, de 27 de abril de 2016, relativo a la protección de las personas físicas en lo que respecta al tratamiento de datos personales y a la libre circulación de estos datos (en adelante RGPD), y conforme a lo establecido en la Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales (en adelante, LOPDGDD) [NOTA DE REVISIÓN: «LOPD» designa la derogada LO 15/1999; usar LOPDGDD para la LO 3/2018. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673.].

Respecto al tratamiento de datos de imágenes en el lugar de trabajo, el artículo 20.3 del Estatuto de los Trabajadores dispone que «El empresario podrá adoptar las medidas que estime más oportunas de vigilancia y control para verificar el cumplimiento por el trabajador de sus obligaciones y deberes laborales, guardando en su adopción y aplicación la consideración debida a su dignidad y teniendo en cuenta, en su caso, la capacidad real de los trabajadores con discapacidad [NOTA DE REVISIÓN: Cita literal del art. 20.3 ET corregida. Fuente: RDLeg 2/2015 (ET), BOE-A-2015-11430, art. 20.3.]».

Por su parte, en el art. 22 LOPDGDD se regulan [NOTA DE REVISIÓN: Coherencia con la sigla. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 22.] los tratamientos con fines de videovigilancia, mientras que en el artículo 89 LOPDGDD se especifica [NOTA DE REVISIÓN: Coherencia con la sigla. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 89.] el derecho a la intimidad frente al uso de dispositivos de videovigilancia y de grabación de sonidos en el lugar de trabajo. En dicho precepto se establece la necesidad de informar a las personas trabajadoras y, en su caso, a los representantes, acerca de esta medida.

Por otro lado, la normativa laboral exige su comunicación a los representantes de los trabajadores, en tanto que el artículo 64.1 ET dispone que «El comité de empresa tendrá derecho a ser informado y consultado por el empresario sobre aquellas cuestiones que puedan afectar a los trabajadores....», y en el punto 5 que «El comité de empresa tendrá derecho a emitir informe, con carácter previo a la ejecución por parte del empresario de las decisiones adoptadas por éste, sobre las siguientes cuestiones: f) La implantación y revisión de sistemas de organización y control del trabajo, estudios de tiempos, establecimiento de sistemas de primas e incentivos y valoración de puestos de trabajo».

Es por ello, que la Empresa, por medio de la presente comunicación, informa a los representantes de los trabajadores:

— Acerca de la puesta en marcha en la entidad de un sistema de videovigilancia, con conexión a Central de Alarmas, con las finalidades de control de la actividad laboral y con fines de seguridad en las instalaciones, con respecto a los principios de proporcionalidad e intervención mínima.

— El sistema únicamente captará la imagen, pero no el sonido.

— Se colocarán carteles informativos en todas las entradas de la empresa, con el fin de dar cumplimiento al mandato del art. 12 RGPD y 22.4 LOPDGDD, [NOTA DE REVISIÓN: Coherencia con la sigla. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 22.4.] informando de la existencia del tratamiento, la identidad del responsable y la posibilidad de ejercitar los derechos previstos en los artículos 15 a 22 RGPD [NOTA DE REVISIÓN: Errata. Fuente: Reglamento (UE) 2016/679 (RGPD), CELEX 32016R0679, arts. 15-22.].

— Igualmente, va a facilitarse dicha información a cada uno de las personas trabajadoras, mediante una circular interna, a través de la intranet corporativa.

— Las imágenes serán suprimidas en el plazo máximo de un mes desde su captación, salvo cuando hubieran de ser conservados para acreditar la comisión de actos que atenten contra la integridad de personas, bienes o instalaciones. En tal caso, las imágenes serán puestas a disposición de la autoridad competente en un plazo máximo de setenta y dos horas desde que se tuviera conocimiento de la existencia de la grabación. [NOTA DE REVISIÓN: Plazo del art. 22.3 LOPDGDD. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 22.3.]

— En ningún caso se procederá a la instalación de sistemas de grabación en lugares destinados al descanso o esparcimiento de las personas trabajadoras o los empleados públicos, tales como vestuarios, aseos, comedores y análogos.

Para cualquier duda o cuestión puede contactar con el delegado de protección de datos de la Empresa, en la dirección [COMPLETAR]

Para que así conste a todos los efectos.

En [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]

Firma Director/a de Recursos Humanos

════════════════════════════════════════════════════════════════════════
