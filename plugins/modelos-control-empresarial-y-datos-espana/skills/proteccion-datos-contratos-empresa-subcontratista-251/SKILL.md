---
name: proteccion-datos-contratos-empresa-subcontratista-251
description: "Redacta el escrito «Protección de datos en contratos con empresa subcontratista: cláusula» (formulario 251 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Protección de datos en contratos con empresa subcontratista: cláusula

> Formulario 0251 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

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

- Cláusula construida sobre el consentimiento para tratamientos que se basan en el contrato y la ley (art. 6.1.b y c RGPD): reescribir como cláusula informativa y reservar el consentimiento a fines no necesarios (art. 6.3 LOPDGDD).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…cha de autorización Firmas 1. La EMPRESA»; «…de [MES] de [AÑO]. El/La trabajador/a:»; «…Por la empresa:»

## Correcciones de la revisión (3)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 8 de la LOPDGDD
- art. 42 del Estatuto de los Trabajadores
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

### Formulario 0251 · Protección de datos en contratos con empresa subcontratista: cláusula

- Año del modelo: 2018
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 puntualizaciones normativas añadidas en el texto; 2 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Cláusula construida sobre el consentimiento para tratamientos que se basan en el contrato y la ley (art. 6.1.b y c RGPD): reescribir como cláusula informativa y reservar el consentimiento a fines no necesarios (art. 6.3 LOPDGDD).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Compromiso
Lugar y fecha de autorización
Firmas

1. La EMPRESA [COMPLETAR] se compromete y obliga a que los datos de carácter personal, a los que acceda en virtud del presente contrato de trabajo, serán tratados de acuerdo con las estipulaciones del artículo 4 y siguientes de la Ley Orgánica 3/2018, de 5 de diciembre, de Protección de Datos Personales y garantía de los derechos digitales (en adelante designada como LOPDGDD).

2. La base jurídica principal para el tratamiento y cesión de los datos personales recabados por la EMPRESA en la relación laboral es el art. 6.1.b) y c) del Reglamento (UE) 2016/679 [NOTA DE REVISIÓN: El art. 88 RGPD solo habilita normas nacionales o convenios específicos para el ámbito laboral; las bases de licitud están en el art. 6.1: b) ejecución del contrato y c) obligación legal. Fuente: Reglamento (UE) 2016/679 (RGPD), CELEX 32016R0679, arts. 6.1 y 88.] del Parlamento Europeo y del Consejo, de 27 de abril de 2016, relativo a la protección de las personas físicas en lo que respecta al tratamiento de datos personales y a la libre circulación de estos datos, en relación con el art. 88 del mismo Reglamento y el art. 8 de la LOPDGDD [NOTA DE REVISIÓN (comprobar): El art. 6 LOPDGDD regula el consentimiento; la obligación legal como base está en el art. 8 LOPDGDD. Fuente: LO 3/2018 (LOPDGDD), BOE-A-2018-16673, arts. 6 y 8; Reglamento (UE) 2016/679 (RGPD), CELEX 32016R0679, art. 88.] en tanto que necesarios para el cumplimiento y mantenimiento de la relación de trabajo, así como el art. 42 del Estatuto de los Trabajadores, en cuanto al cumplimiento de las relaciones contractuales en que la EMPRESA actúe en su condición de subcontratista.

3. El trabajador autoriza expresamente a que los datos recabados sean tratados [NOTA DE REVISIÓN: Los tratamientos necesarios para el contrato y para cumplir obligaciones legales no se basan en el consentimiento (art. 6.1.b y c RGPD); presentarlos como «autorización» confunde la base y obliga a respetar su retirada. El consentimiento solo para fines no necesarios, sin condicionar el contrato (art. 6.3 LOPDGDD). Fuente: Reglamento (UE) 2016/679 (RGPD), CELEX 32016R0679, art. 6.1; LO 3/2018 (LOPDGDD), BOE-A-2018-16673, art. 6.3.] por la EMPRESA con la finalidad de llevar a cabo la gestión fiscal y laboral, incluyendo recogida de datos relativos a su situación personal y familiar a estos efectos, contratos, nóminas, seguridad social, prevención de riesgos laborales y resto de obligaciones y trámites laborales y fiscales, autorizando la cesión de sus datos a otras personas o entidades relacionadas a los efectos del cumplimiento y mantenimiento de la relación de trabajo, tales como la Asesoría de la Empresa, entidades bancarias, Mutuas y entidades aseguradoras, el servicio de prevención de riesgos laborales y vigilancia de la salud.

4. En especial, el trabajador autoriza expresamente la cesión de sus datos personales a las empresas contratistas de la EMPRESA que ésta tenga que facilitar en cumplimiento de sus obligaciones legales según relaciones de subcontratación de obras y servicios suscritos, incluyendo cesión de nóminas, TC2, informes de accidentes, certificados de aptitud y/o formación en prevención de riesgos laborales y similares a tales empresas contratistas

5. Los datos se conservarán durante el tiempo necesario para cumplir con la finalidad para la que se obtuvieron y para determinar las posibles responsabilidades que se pudieran derivar de dicha finalidad y del tratamiento de los datos

6. Por otro lado, le informamos de su derecho a ejercer los derechos de acceso, rectificación o supresión, o la limitación de su tratamiento, o a oponerse al mismo. Le advertimos de su derecho a retirar, en cualquier momento, el consentimiento prestado para tratar sus datos, sin que ello afecte a la licitud del tratamiento basado en el consentimiento previo a su retirada. Finalmente, le recordamos, por imperativo legal, su derecho a presentar una reclamación ante la Agencia Española de Protección de Datos.

El/La trabajador/a queda informado/a y consiente en [LUGAR], a [DÍA] de [MES] de [AÑO].

El/La trabajador/a: [COMPLETAR]

Por la empresa: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
