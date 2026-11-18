---
name: citacion-oficial-subinspector-laboral-empleo-seguridad-394
description: "Redacta el escrito «Citación oficial del Subinspector Laboral de Empleo y Seguridad Social» (formulario 394 de inspección de trabajo y sanciones, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Citación oficial del Subinspector Laboral de Empleo y Seguridad Social

> Formulario 0394 del plugin **Inspección de Trabajo y sanciones** · revisado el 17-11-2026.

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

- Cuantías de obstrucción desfasadas (6.250 € era el máximo anterior de las graves): hoy 751-7.500 € graves y 7.501-225.018 € muy graves (art. 40.1 LISOS); representación ante la ITSS apud acta o por registro electrónico (art. 21.4 RD 138/2000, red. RD 1011/2023).
- La exigencia del «Libro de visitas» (casilla 1) debe revisarse: la Ley 23/2015 prevé diligencias de cada actuación (art. 21.6) y el art. 50.3.b LISOS sigue mencionando el libro; si la Orden ESS/1452/2016 lo suprimió: NO VERIFICADO.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] FECHA (2 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] NOMBRE Y APELLIDOS
- [ ] Otros 21 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…IÓN Datos Empresa Nombre o Razón Social:»; «…Actividad:»; «…Actividad: [COMPLETAR] N.I.F. o C.I.F.:»; «…N.I.F. o C.I.F.: [COMPLETAR] C.C.C.:»; «…C.C.C.: [COMPLETAR] Domicilio:»; «…Domicilio: [COMPLETAR] Localidad:»; «…Localidad: [COMPLETAR] Provincia:»; «…Provincia: [COMPLETAR] Código Postal:»; «…, a [FECHA]. RECIBÍ Nombre:»; «…. RECIBÍ Nombre: [COMPLETAR] D.N.I.:»; «…RAL DE EMPLEO Y SEGURIDAD SOCIAL Nombre:»; «…Firmado:»; …

## Párrafos opcionales (24)

Inclúyelos solo si encajan en los hechos:

- [OPCIONAL — incluir si procede] 2. Comunicación de apertura a la Autoridad Laboral.…
- [OPCIONAL — incluir si procede] 3. Cuadro horario y calendario laboral.…
- [OPCIONAL — incluir si procede] 4. Recibos de pago de salario desde [COMPLETAR] a…
- [OPCIONAL — incluir si procede] 5. Justificante de inscripción de la empresa en la Seguridad Social.…
- [OPCIONAL — incluir si procede] 6. Documento de asociación a efectos de Accidentes de Trabajo.…
- [OPCIONAL — incluir si procede] 7. Partes de alta y baja de trabajadores en la Seguridad Social desde [COMPLET…
- [OPCIONAL — incluir si procede] 8. Justificante de pago de cuotas a la Seguridad Social (Modelos Relación Nomi…
- [OPCIONAL — incluir si procede] 9. Justificante de aplazamiento o fraccionamiento de pago de cuotas a la Segur…
- [OPCIONAL — incluir si procede] 10. Resumen de horas extraordinarias realizadas desde [COMPLETAR] a…
- [OPCIONAL — incluir si procede] 11. Contratos de trabajo registrados por la Oficina de Empleo, desde [COMPLETA…
- [OPCIONAL — incluir si procede] 12. Justificante de haberse comunicado a la oficina de empleo las contratacion…
- [OPCIONAL — incluir si procede] 13. Autorización administrativa para trabajar los trabajadores extranjeros (pe…
- [OPCIONAL — incluir si procede] 14. Parte de alta y justificante de pago de cuotas al Régimen Especial de Trab…
- [OPCIONAL — incluir si procede] 15. Escritura de la sociedad, modificaciones y libro de socios.…
- [OPCIONAL — incluir si procede] 16. Libros de contabilidad (Diario mayor y balances) de los años:…
- [OPCIONAL — incluir si procede] 17. Balance de sumas y saldos al máximo nivel de los años:…
- [OPCIONAL — incluir si procede] 18. Declaración del Impuesto de Sociedades de los años:…
- [OPCIONAL — incluir si procede] 19. Documento Acreditativo de alta en el I.A.E.…
- [OPCIONAL — incluir si procede] 20. Declaración de retenciones del IRPF (modelo 190) de los años:…
- [OPCIONAL — incluir si procede] 21. Declaraciones de operaciones con terceros (modelo 347) de los años:…
- [OPCIONAL — incluir si procede] 22. Conforme a lo dispuesto por el art. 21.2 del RD 138/2000, de 4 febrero, Re…
- [OPCIONAL — incluir si procede] 23.…
- [OPCIONAL — incluir si procede] 24..…
- ════════════════════════════════════════════════════════════════════════…

## Correcciones de la revisión (2)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 14.4 de la Ley 23/2015
- art. 40.1 TRLISOS
- art. 32.2 Real Decreto 928/1998
- art. 21.2 del RD 138/2000
- Real Decreto Legislativo 5/2000

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

### Formulario 0394 · Citación oficial del Subinspector Laboral de Empleo y Seguridad Social

- Año del modelo: 2015
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 24 desplegables y casillas convertidos en elección en blanco; 12 campos de relleno marcados en blanco; 12 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: Cuantías de obstrucción desfasadas (6.250 € era el máximo anterior de las graves): hoy 751-7.500 € graves y 7.501-225.018 € muy graves (art. 40.1 LISOS); representación ante la ITSS apud acta o por registro electrónico (art. 21.4 RD 138/2000, red. RD 1011/2023). · La exigencia del «Libro de visitas» (casilla 1) debe revisarse: la Ley 23/2015 prevé diligencias de cada actuación (art. 21.6) y el art. 50.3.b LISOS sigue mencionando el libro; si la Orden ESS/1452/2016 lo suprimió: NO VERIFICADO.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

CITACIÓN
Requerimiento a la cita
Lugar y fecha
Recibí y firma del subinspector/a
Autorización a citación
Firmas de mandante y mandatario
Documentación requerida

CITACIÓN

Datos Empresa

Nombre o Razón Social: [COMPLETAR]

Actividad: [COMPLETAR]

N.I.F. o C.I.F.: [COMPLETAR]

C.C.C.: [COMPLETAR]

Domicilio: [COMPLETAR]

Localidad: [COMPLETAR]

Provincia: [COMPLETAR]

Código Postal: [COMPLETAR]

En virtud de lo dispuesto en el art. 13.3 en relación con el art. 14.4 de la Ley 23/2015, de 21 de julio, Ordenadora del Sistema de Inspección de Trabajo y Seguridad Social, se requiere a la empresa indicada para que el próximo día [FECHA] a las [Nº] horas, presente en las oficinas de la Inspección Provincial de Trabajo y Seguridad Social de esta capital, ante el Subinspector que suscribe, la documentación que se relaciona al margen, señalada con una (X).

La incomparecencia o la no presentación de toda la documentación requerida constituye acto de obstrucción, de acuerdo con el art. 50 del Texto Refundido de la Ley sobre Infracciones y Sanciones en el Orden Social (TRLISOS), aprobado por Real Decreto Legislativo 5/2000, de 4 de agosto, sancionable con una multa de hasta 7.500 EUROS si es grave, o de hasta 225.018 EUROS si es muy grave (art. 40.1 TRLISOS) [NOTA DE REVISIÓN: 6.250 € era el máximo anterior de las graves. Si la obstrucción afecta a la comprobación del alta y pudiera dar lugar a los arts. 22.2 o 23.1.a, las graves van de 3.750 a 12.000 € (art. 40.1.f). Fuente: RDLeg 5/2000 (LISOS), BOE-A-2000-15060, arts. 40.1 y 50 (red. RDL 32/2021).], y dará lugar a levantar, en su caso, las actas correspondientes y practicar las liquidaciones que procedan por estimación (art. 32.2 Real Decreto 928/1998, de 14 de mayo, Reglamento general sobre procedimientos para la imposición de sanciones por infracciones de orden social y para los expedientes liquidatorios de cuotas de la Seguridad Social).

En [LUGAR], a [FECHA].

RECIBÍ

Nombre: [COMPLETAR]

D.N.I.: [COMPLETAR]

Firmado: EL/LA SUBINSPECTOR/A LABORAL DE EMPLEO Y SEGURIDAD SOCIAL

Nombre: [COMPLETAR]

Firmado: [COMPLETAR]

AUTORIZACIÓN A LA CITACIÓN

D./D.ª [NOMBRE Y APELLIDOS]: con D.N.I. en calidad de [COMPLETAR] de la empresa de referencia, AUTORIZO a: con D.N.I. para que lo represente como mandatario en los términos del art. 21.2 del RD 138/2000, de 4 febrero, ante la Inspección [NOTA DE REVISIÓN: RD 138/2000 vigente, modificado por RD 1011/2023: desde 6-3-2024 la representación se acredita apud acta (presencial o en sede electrónica) o por el Registro Electrónico de Apoderamientos de la ITSS (art. 21.4 y 5). Fuente: RD 138/2000, BOE-A-2000-3088, art. 21 (red. RD 1011/2023, BOE-A-2023-24844).] Provincial de Trabajo y Seguridad Social, en relación con la presente actuación.

FIRMA DEL MANDANTE / FIRMA DEL MANDATARIO

RELACIÓN QUE SE CITA

[OPCIONAL — incluir si procede] 1. Libro de visitas de la Inspección de Trabajo y Seguridad Social.

[OPCIONAL — incluir si procede] 2. Comunicación de apertura a la Autoridad Laboral.

[OPCIONAL — incluir si procede] 3. Cuadro horario y calendario laboral.

[OPCIONAL — incluir si procede] 4. Recibos de pago de salario desde [COMPLETAR] a

[OPCIONAL — incluir si procede] 5. Justificante de inscripción de la empresa en la Seguridad Social.

[OPCIONAL — incluir si procede] 6. Documento de asociación a efectos de Accidentes de Trabajo.

[OPCIONAL — incluir si procede] 7. Partes de alta y baja de trabajadores en la Seguridad Social desde [COMPLETAR] a

[OPCIONAL — incluir si procede] 8. Justificante de pago de cuotas a la Seguridad Social (Modelos Relación Nominal de Trabajadores RNT y Relación de Liquidación de Cotizaciones RLC) desde [COMPLETAR] a [COMPLETAR] (incluidos los meses no pagados).

[OPCIONAL — incluir si procede] 9. Justificante de aplazamiento o fraccionamiento de pago de cuotas a la Seguridad Social.

[OPCIONAL — incluir si procede] 10. Resumen de horas extraordinarias realizadas desde [COMPLETAR] a

[OPCIONAL — incluir si procede] 11. Contratos de trabajo registrados por la Oficina de Empleo, desde [COMPLETAR] hasta

[OPCIONAL — incluir si procede] 12. Justificante de haberse comunicado a la oficina de empleo las contrataciones efectuadas desde [COMPLETAR] hasta

[OPCIONAL — incluir si procede] 13. Autorización administrativa para trabajar los trabajadores extranjeros (permiso por cuenta propia o por cuenta ajena) y, en su caso, autorización previa del empleador, así como contratos de trabajo de los trabajadores extranjeros.

[OPCIONAL — incluir si procede] 14. Parte de alta y justificante de pago de cuotas al Régimen Especial de Trabajadores Autónomos, desde [COMPLETAR] a

[OPCIONAL — incluir si procede] 15. Escritura de la sociedad, modificaciones y libro de socios.

[OPCIONAL — incluir si procede] 16. Libros de contabilidad (Diario mayor y balances) de los años:

[OPCIONAL — incluir si procede] 17. Balance de sumas y saldos al máximo nivel de los años:

[OPCIONAL — incluir si procede] 18. Declaración del Impuesto de Sociedades de los años:

[OPCIONAL — incluir si procede] 19. Documento Acreditativo de alta en el I.A.E.

[OPCIONAL — incluir si procede] 20. Declaración de retenciones del IRPF (modelo 190) de los años:

[OPCIONAL — incluir si procede] 21. Declaraciones de operaciones con terceros (modelo 347) de los años:

[OPCIONAL — incluir si procede] 22. Conforme a lo dispuesto por el art. 21.2 del RD 138/2000, de 4 febrero, Reglamento de Organización y Funcionamiento de la Inspección de Trabajo y Seguridad Social se solicita la personación del sujeto obligado.

[OPCIONAL — incluir si procede] 23.

[OPCIONAL — incluir si procede] 24..

════════════════════════════════════════════════════════════════════════
