---
name: despido-nulo-negar-reincorporacion-tras-excedencia-65
description: "Redacta el escrito «Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda» (formulario 65 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda

> Formulario 0065 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- Nulidad objetiva: los arts. 53.4.b) y 55.5.b) ET (redacción LO 1/2025, DF 26.ª, en vigor el 3-4-2025) incluyen permisos del 37.3.b), 4, 5 y 6, adaptaciones del 34.8 y excedencia del 46.3; el art. 55.5.a) incluye el permiso parental del 48 bis.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE
- [ ] LOCALIDAD (3 veces)
- [ ] FECHA (8 veces)
- [ ] IMPORTE (2 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 22 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…y con domicilio en [LOCALIDAD], de»; «…ación por DESPIDO NULO contra la empresa»; «…, dedicada a la actividad de»; «… con domicilio social en [LOCALIDAD], de»; «…, ostentando»; «…, ostentando [COMPLETAR] de»; «… [COMPLETAR] realizando las funciones de»; «…atuto de los Trabajadores y del artículo»; «…del Convenio»; «…uede valerse por sí mismo/a por razón de»; «…empresa de acuerdo con lo preceptuado en»; «…con el resultado de»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 46.3 del Estatuto de los Trabajadores
- art. 2 de la Ley 36/2011
- arts. 9.1 y 9.5 de la LOPJ
- arts. 6 y 10 de la Ley 36/2011
- art. 113 de la Ley 36/2011
- Real Decreto-ley 5/2023
- Ley Orgánica 1/2025

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

### Formulario 0065 · Despido nulo por negar la reincorporación tras excedencia por cuidado de pareja de hecho: demanda

- Año del modelo: 2023
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 40 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (FECHA)
- Avisos de la revisión: Nulidad objetiva: los arts. 53.4.b) y 55.5.b) ET (redacción LO 1/2025, DF 26.ª, en vigor el 3-4-2025) incluyen permisos del 37.3.b), 4, 5 y 6, adaptaciones del 34.8 y excedencia del 46.3; el art. 55.5.a) incluye el permiso parental del 48 bis.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Encabezamiento. Parte actora
Encabezamiento. Formulación.
Hechos
Fundamentos de Derecho
Suplico de demanda
Otrosí 1. Representación
Otrosí 2. Medios de prueba
Firmas
A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA QUE POR TURNO CORRESPONDA

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI [DNI/NIE] y con domicilio en [LOCALIDAD], de [COMPLETAR], ante el Tribunal de Instancia comparezco y como mejor proceda en Derecho digo:

Que, por medio del presente escrito, en tiempo y forma legal, formulo demanda en reclamación por DESPIDO NULO contra la empresa [COMPLETAR], dedicada a la actividad de [COMPLETAR] y con domicilio social en [LOCALIDAD], de [COMPLETAR], demanda que fundamento en los siguientes

Hechos

PRIMERO.— Que ingresé a prestar servicios por cuenta de la empresa demandada con fecha [FECHA], ostentando [COMPLETAR] de [COMPLETAR] realizando las funciones de [COMPLETAR] y percibiendo un salario mensual de [IMPORTE] euros, que incluida la prorrata de pagas extras asciende a [IMPORTE] euros mensuales.

SEGUNDO.— En fecha [FECHA], y por aplicación del artículo 46.3 del Estatuto de los Trabajadores y del artículo [COMPLETAR] del Convenio [COMPLETAR] solicité excedencia por cuidado de un familiar, D./Dña. [NOMBRE Y APELLIDOS] consanguíneo/a de mi pareja de hecho, D./Dña. [NOMBRE Y APELLIDOS] que no puede valerse por sí mismo/a por razón de [COMPLETAR] y no desempeña actividad retribuida.

Anunciando con un mes de antelación mi reingreso en la empresa de acuerdo con lo preceptuado en [COMPLETAR], siendo la fecha de la reincorporación al puesto de trabajo el día [FECHA]

TERCERO.— En fecha [FECHA] intenté reincorporarme a mi puesto de trabajo, manifestándoseme por la dirección de la empresa que no podía reincorporarme pues mi puesto estaba ocupado por otra persona, situación que ha resultado irrevocable.

CUARTO.— Que se presentó papeleta de demanda de conciliación, ante el servicio administrativo correspondiente, el día [FECHA], habiéndose celebrado el preceptivo acto conciliatorio el día [FECHA] con el resultado de [COMPLETAR].

QUINTO.— Que [COMPLETAR] desempeño cargo de representante de los trabajadores.

Fundamentos de Derecho

PRIMERO.— Ley 36/2011, de 10 de octubre LRJS, en especial sus arts. 17 y 103, relativos a la legitimación activa que corresponde al/ a la trabajador/a despedido/a y la pasiva a la empresa demandada.

SEGUNDO.— Corresponde a la jurisdicción social, con arreglo a lo dispuesto en el art. 2 de la Ley 36/2011, de 10 de octubre LRJS y arts. 9.1 y 9.5 de la LOPJ.

TERCERO Corresponde la competencia al Tribunal al que nos dirigimos con arreglo a lo dispuesto en los arts. 6 y 10 de la Ley 36/2011, de 10 de octubre LRJS.

CUARTO El procedimiento adecuado es el correspondiente a la modalidad procesal de despido, con arreglo a lo dispuesto en los arts. 103 y ss. de la Ley 36/2011, de 10 de octubre LRJS.

QUINTO En cuanto al fondo del asunto, se considera el despido nulo, con arreglo a lo dispuesto en los arts. 46.3, arts. 53.4. b) y 55.5.b) del ET, en la redacción dada por el Real Decreto-ley 5/2023, de 28 de junio (art. 46.3), y por la disposición final vigesimosexta de la Ley Orgánica 1/2025, de 2 de enero (arts. 53.4.b) y 55.5.b), en vigor desde el 3 de abril de 2025).

Siendo un despido nulo, con arreglo a lo dispuesto en el art. 113 de la Ley 36/2011, de 10 de octubre LRJS, se condenará a la inmediata readmisión del trabajador/a con abono de los salarios dejados de percibir. La sentencia será ejecutada de forma provisional en los términos establecidos por el artículo 297, tanto si fuera recurrida por el empresario como si lo fuera por el trabajador.

SEXTO.— Convenio Colectivo [COMPLETAR] de fecha [FECHA] publicado en [COMPLETAR] en fecha [FECHA].

SÉPTIMO.— Normas concordantes y complementarias que resulten de aplicación.

Por lo expuesto,

SUPLICO AL TRIBUNAL que, habiendo por presentada esta demanda con sus copias y documentos que se acompañan, se sirva admitirla, tenga por formulada demanda por despido nulo, contra la empresa [COMPLETAR], se proceda a citar a las partes para los actos de conciliación y juicio, por el que seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba que expresamente se solicita, se dicte en su día sentencia estimando íntegramente la demanda, se declare nulo el despido, con el efecto de readmisión inmediata y abono de los salarios dejados de percibir, junto con los demás pronunciamientos legales que procedan.

PRIMER OTROSÍ DIGO: Que acudiré a juicio con asistencia y defensa de [COMPLETAR] D./Dª [NOMBRE Y APELLIDOS], señalándose a efectos de citaciones y notificaciones su domicilio, sito en [LOCALIDAD] de [COMPLETAR], para lo que se indica, a los efectos oportunos [COMPLETAR].

SEGUNDO OTROSÍ DIGO: Que, como medios de prueba, independientemente de los que pueda proponer en el acto de juicio, propongo:

INTERROGATORIO del representante de la empresa demandada.

DOCUMENTAL: [COMPLETAR]

1 .- Consistente en que se reclame a la empresa demandada para que aporte al acto de juicio/con una antelación mínima de [Nº] días al acto del Juicio oral, la siguiente documentación:

.- Nóminas del último año trabajado.

.- [COMPLETAR]

2.- Se tenga por aportada la siguiente documentación:

.- [COMPLETAR]

SUPLICO AL TRIBUNAL, que tenga por realizadas las anteriores manifestaciones a los efectos oportunos.

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Firmas actor/a y representante

════════════════════════════════════════════════════════════════════════
