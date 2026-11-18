---
name: contrato-actuacion-toreros-novilleros-rejoneadores-132
description: "Redacta el escrito «Contrato de actuación de toreros, novilleros y rejoneadores» (formulario 132 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Contrato de actuación de toreros, novilleros y rejoneadores

> Formulario 0132 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] LUGAR
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS (13 veces)
- [ ] NIF (4 veces)
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE
- [ ] Nº (2 veces)
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… en representación del Jefe de Cuadrilla»; «…se obliga a celebrar una corrida de»; «…za y fecha que se indica a continuación:»; «…, en representación conferida a»; «…n la corrida de referencia actuando como»; «…zo de Espadas, para la lidia y muerte de»; «…nando en dicha actuación con los espadas»; «…:»; «…: [COMPLETAR] FECHA:»; «…:»; «…: [COMPLETAR] FECHA:»

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0132 · Contrato de actuación de toreros, novilleros y rejoneadores

- Año del modelo: 2022
- Revisión 17-11-2026: 29 campos de relleno marcados en blanco; 4 etiquetas sin dato marcadas en blanco; 2 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
ESTIPULACIONES

Los contratos de actuación se deben formalizar por escrito. Debe constar con claridad todas las condiciones esenciales y complementarias, en su caso, detallando el nombre y apellidos, documento nacional de identidad de los Jefes de Cuadrilla, Subalternos y Mozos de espada que formen parte de las cuadrillas, así como su afiliación a la Seguridad Social. Los contratos deberán aparecer claramente legibles, con identificación de las partes y acreditación suficiente de la representación con la que firman, y de la identidad del representante. Cuando en el contrato no se indique la retribución a percibir por el Jefe de Cuadrilla, o se empleen expresiones tales como «cantidad convenida», o similares, se entenderán siempre como pactados, al menos, los importes mínimos establecidos en el VI Convenio colectivo nacional taurino.

Los organizadores de espectáculos taurinos presentarán los contratos que suscriban con los Jefes de Cuadrilla en la Comisión de Seguimiento, Vigilancia y Control para su preceptivo visado, desde la que en su caso se remitirá copia a las asociaciones empresariales y profesionales a que pertenezcan la empresa y los actuantes.

En [LUGAR], a [FECHA].

REUNIDOS

De una parte, D./Dña. [NOMBRE Y APELLIDOS], con NIF [NIF], en representación de [NOMBRE DEL REPRESENTADO/A], con NIF [NIF] y domicilio social en [LOCALIDAD], en calidad de empresa organizadora de espectáculos taurinos.

De otra parte, D./Dña. [NOMBRE Y APELLIDOS], con NIF [NIF], en representación del Jefe de Cuadrilla [COMPLETAR], con NIF [NIF] y domicilio social en [LOCALIDAD].

Ambas partes se reconocen recíprocamente capacidad para otorgar el presente contrato, a cuyo efecto libremente convienen las siguientes

ESTIPULACIONES

Primera. D./Dña. [NOMBRE Y APELLIDOS] se obliga a celebrar una corrida de [COMPLETAR] en la plaza y fecha que se indica a continuación: [COMPLETAR].

Segunda. D./Dña. [NOMBRE Y APELLIDOS], en representación conferida a [COMPLETAR] se obliga a tomar parte en la corrida de referencia actuando como [COMPLETAR], acompañado de su correspondiente y reglamentaria cuadrilla de Picadores, Banderilleros y Mozo de Espadas, para la lidia y muerte de [COMPLETAR] reses de la ganadería de D./Dña. [NOMBRE Y APELLIDOS], alternando en dicha actuación con los espadas [COMPLETAR].

Tercera. La Empresa abonará, antes del sorteo, la cantidad de [IMPORTE] euros, en concepto de honorarios del Jefe de Cuadrilla en los términos establecidos en el artículo 10.1 del Convenio Colectivo Nacional Taurino, cantidad se entregará al diestro o la persona que, a este efecto, le represente. Si la empresa rehusase el abono de la cantidad pactada a la hora señalada, el Jefe de Cuadrilla y su cuadrilla podrán abstenerse de torear, con derecho a exigir, como indemnización de daños y perjuicio, el importe total de los acuerdos establecidos, sin perjuicio de otros daños soportados, si estos se acreditasen.

Cuarta. Si por causa de fuerza mayor justificada, la Empresa se viese obligada a suspender el festejo y avisase al diestro contratado antes de emprender el viaje, éste no tendrá derecho a reclamación alguna; pero si hubiese emprendido el viaje, o se encontrase en el lugar del festejo, vendrá la Empresa obligada a abonarle todos los gastos que se le ocasionen a él y su Cuadrilla, hasta el regreso a sus respectivas residencias habituales, así como el sueldo del Mozo de Espadas y del Ayuda. Si la corrida no se celebrase por causa no atribuible a fuerza mayor, o el diestro no fuera anunciado, la Empresa abonará el importe total del contrato. Si una vez comenzado el festejo se suspendiese antes de la terminación, el Espada percibirá sus honorarios como si hubiese sido celebrada en su totalidad. En caso de incumplimiento injustificado del presente contrato por el matador, asumirá las responsabilidades dimanantes de dicho incumplimiento.

Quinta. La Empresa se obliga a presentar este contrato para su visado en la comisión de Seguimiento Vigilancia y Control del Convenio Colectivo Nacional Taurino. En caso contrario, o si el visado fuera denegado por causa imputable a la empresa, el diestro anunciado podrá abstenerse de torear, con derecho a la indemnización expresada en la cláusula tercera. Igualmente será rescindible el presente contrato si no obtuvieran el preceptivo visado los contratos correspondientes a los demás toreros integrantes del cartel. El presente contrato deberá ser asimismo registrado en la asociación profesional a la que, en su caso, pertenezca el diestro actuante.

Sexta. Las actuación profesional a que se refiere el presente contrato no podrá ser televisada ni captada o fijada por cualquier medio o sistema, para su posterior comercialización, sin que previamente se haya hecho constar en el presente contrato la correspondiente autorización del actuante. En tal caso, la retribución en concepto de derechos de imagen y los términos de la cesión de la explotación de los mismos, se harán constar en el presente contrato o en documento anexo. A falta de acuerdo expreso que refleje las condiciones de la cesión de la explotación de la imagen del actuante, se entenderá que la autorización se refiere a la realización de una única emisión televisiva de forma simultánea a la celebración del espectáculo.

Séptima. Por el presente, las partes manifiestan su consentimiento expreso para que los datos personales utilizados por la Comisión de Seguimiento, Vigilancia y Control sean incorporados al fichero denominado Contratos, del que es responsable la citada Comisión. Queda enteradas de que de acuerdo con capítulo II de la LO 3/2018 tiene derecho de acceso, rectificación, cancelación y oposición de los datos obrantes en dicho fichero, sin perjuicio y con independencia de las consecuencias que el ejercicio de estos derechos pudieran ocasionar a la relación contractual, así como de las obligaciones legales derivadas de dicha relación. En caso que no desee que sus datos personales sean tratados con los fines señalados, puede ejercitar el derecho de oposición, junto con el de acceso, rectificación y cancelación mediante comunicación dirigida a c/ Carretas 27, 1.º Derecha, 28012 Madrid.

Cláusulas adicionales y cuadrilla completa
Profesión	Nombre y Apellidos	DNI	SS	N.º Registro
Matador.	D./Dña. [NOMBRE Y APELLIDOS]
Picador.	D./Dña. [NOMBRE Y APELLIDOS]
Picador.	D./Dña. [NOMBRE Y APELLIDOS]
Banderillero.	D./Dña. [NOMBRE Y APELLIDOS]
Banderillero.	D./Dña. [NOMBRE Y APELLIDOS]
Banderillero.	D./Dña. [NOMBRE Y APELLIDOS]
Mozo de Esp.	D./Dña. [NOMBRE Y APELLIDOS]
Ayuda M. de Esp.	D./Dña. [NOMBRE Y APELLIDOS]

Así lo convienen y estipulan, obligándose ambas partes a cuanto dejan consignado, y en señal de conformidad y previa lectura, firman el presente contrato en el lugar y fecha indicados

LA EMPRESA	VISADO COMISIÓN SEGUIMIENTO V. Y CONTROL CONVENIO COLECTIVO TAURINO	EL ACTUANTE

REGISTRO ENTIDAD EMPRESARIAL

N.º [Nº]: [COMPLETAR]

FECHA: [COMPLETAR]

REGISTRO ASOCIACIÓN PROFESIONAL

N.º [Nº]: [COMPLETAR]

FECHA: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
