---
name: despido-colectivo-acuerdo-demanda-sindicatos-no-lo-391
description: "Redacta el escrito «Despido colectivo con acuerdo: demanda de sindicatos que no lo firmaron» (formulario 391 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Despido colectivo con acuerdo: demanda de sindicatos que no lo firmaron

> Formulario 0391 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (12 veces)
- [ ] DNI/NIE (4 veces)
- [ ] CALLE (10 veces)
- [ ] NÚMERO (10 veces)
- [ ] FECHA
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 17 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…l, formulan demanda contra: - La empresa»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…nº [NÚMERO] de»; «…- La empresa se dedica a la actividad de»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 51.1 ET
- artículo 51.2 ET
- artículo 124.11 LRJS
- artículo 64.1 LRJS
- Ley 36/2011
- Ley 3/2012
- Ley 11/2013
- Real Decreto Legislativo 2/2015
- Real Decreto 1483/2012

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

### Formulario 0391 · Despido colectivo con acuerdo: demanda de sindicatos que no lo firmaron

- Año del modelo: 2015
- Revisión 17-11-2026: saltos de párrafo recuperados (texto venía pegado); restos de formato retirados; notas del formulario agrupadas al final (11); 55 campos de relleno marcados en blanco
- Avisos de la revisión: Despido colectivo: art. 51 ET (consultas de hasta 30 días, 15 si menos de 50 trabajadores; comisión constituida en 7 días o 15 sin representantes; plan de recolocación externa de al menos seis meses si afecta a más de 50) y RD 1483/2012.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Identificación de los demandantes
Hechos
Fundamentos de derecho
Suplico
Lugar y fecha
Firmas
A la Sala de lo Social (1)

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE]

y domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE]

y domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE]

y domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR], D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI nº [DNI/NIE]

y domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR], representantes sindicales, pertenecientes al Sindicato… con implantación suficiente en el ámbito del despido (2) ante la Sala de lo Social comparecen y como mejor proceda en derecho, dicen:

Que por medio del presente escrito, en tiempo y forma legal, formulan demanda contra:

- La empresa [COMPLETAR] con domicilio social en la calle [CALLE] nº [NÚMERO] de [COMPLETAR],

- Los siguientes miembros del comité de empresa: (3)

* D./Dña. [NOMBRE Y APELLIDOS], con domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR]

* D./Dña. [NOMBRE Y APELLIDOS] con domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR]

* D./Dña. [NOMBRE Y APELLIDOS] con domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR]

* D./Dña. [NOMBRE Y APELLIDOS] con domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR]

* D./Dña. [NOMBRE Y APELLIDOS] con domicilio en la calle [CALLE] nº [NÚMERO] de [COMPLETAR]

en reclamación de que se declare no ajustada a derecho la decisión extintiva adoptada por la empresa, demanda que fundamentan en los siguientes

HECHOS:

Primero: En fecha [FECHA] se inició el período de consultas de la empresa con los representantes de los trabajadores, es decir, con los nueve miembros del comité de empresa.

Segundo: El último día de dicho período de consultas se alcanzó un acuerdo entre el empresario y los cinco miembros del comité de empresa que aparecen demandados (4), acuerdo que no fue suscrito por los otros cuatro miembros del comité de empresa.

Tercero: En el acuerdo alcanzado se establecía que concurrían las causas organizativas y de producción (5) alegadas por la empresa en la comunicación de apertura del período de consultas, por lo que procedía la extinción de los quince contratos de trabajo propuestos por la empresa.

Cuarto: No es cierto que concurran dichas causas (6), ya que si bien es cierto que ha habido una disminución del volumen de la contrata que la empleadora tiene suscrita con la empresa principal, no es menos cierto que a los pocos días se ha producido un incremento del volumen de la contrata, hasta alcanzar niveles superiores a los contratados hasta esa fecha. Por dicha circunstancia es evidente que no concurren las causas organizativas y productivas alegadas por la demandada para justificar el despido de quince trabajadores.

Quinto.- Los trabajadores despedidos (7) ostentan la siguiente categoría, antigüedad y salario:

Antigüedad salario categoría

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

Sexto.- La empresa se dedica a la actividad de [COMPLETAR], y ocupa [COMPLETAR] trabajadores (8).

Séptimo.- No se ha presentado papeleta de conciliación ante el servicio administrativo correspondiente, ya que están exceptuados del requisito de intento de conciliación, o en su caso de mediación, los procesos relativos a la impugnación del despido colectivo por los representantes de los trabajadores (9).

Fundamentos de derecho

Primero.- Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social, teniendo en cuenta las modificaciones introducidas por la Ley 3/2012 de 6 de julio y por el RD Ley 11/2013, de 2 de agosto, en especial los artículos 1, 2 y 124.apartados del 1 al 12.

Segundo.- Texto Refundido del Estatuto de los Trabajadores, aprobado por Real Decreto Legislativo 2/2015, de 23 de octubre, artículo 51.

Tercero.- Real Decreto 1483/2012, de 29 de octubre, por el que se aprueba el reglamento de los procedimientos de despido colectivo y de suspensión de contratos y de reducción de jornada y, en especial, los artículos 2, 3, 4 y 7.

Cuarto.- Convenio Colectivo del Sector de [COMPLETAR]

Quinto- Todas las normas concordantes y complementarias aplicables al caso

Por todo ello

SUPLICO A LA SALA que, habiendo por presentada esta demanda con sus copias y documentos que acompaño, se sirva admitirla, tenga por formulada demanda por despido improcedente contra la empresa [COMPLETAR] y contra los miembros del comité de empresa [COMPLETAR] se proceda a citar a las partes para los actos de conciliación y subsiguiente juicio por el que, en definitiva, seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba, que expresamente se solicita, se dicte en su día sentencia, estimando íntegramente la presente demanda, declarando no ajustada a derecho la decisión extintiva (10) que afecta a quince contratos de trabajo.

Es justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma [COMPLETAR] (11).

NOTAS DEL FORMULARIO

(1) Si el despido extiende sus efectos al ámbito territorial de una Comunidad Autónoma, es competente para conocer de la demanda la Sala de lo Social del Tribunal Superior de Justicia de dicha Comunidad. Si extiende sus efectos a un ámbito territorial superior al de una Comunidad Autónoma, es competente la Sala de lo Social de la Audiencia Nacional.

(2) La demanda puede ser presentada por todos los representantes de los trabajadores de la empresa o sólo por parte de ellos, siempre que el acuerdo de presentar la demanda se adopte por la mayoría de miembros del comité de empresa ya que, al tratarse de un órgano colegiado, sus decisiones han de ser adoptadas por acuerdo mayoritario de sus miembros.

Asimismo puede presentarse por los representantes sindicales de un solo sindicato o de varios, siempre que tengan implantación suficiente en el ámbito del despido colectivo. Si no tienen implantación suficiente no están legitimados para presentar la demanda –STS de 21 de octubre de 2014, recurso 11/2014.

(3) En el caso de que el período de consultas hubiera finalizado con acuerdo, los representantes de los trabajadores, que formulan la demanda y no firmaron dicho acuerdo, deberán demandar a los firmantes del mismo (artículo 124.4).

(4) La demanda deberá presentarse en el plazo de caducidad de veinte días desde la fecha del acuerdo alcanzado en el período de consultas o de la notificación a los representantes de los trabajadores de la decisión empresarial de despido colectivo.

(5) A tenor del artículo 51.1 ET, se entiende que concurren causas organizativas cuando se produzcan cambios, entre otros, en el ámbito de los sistemas y métodos de trabajo del personal o en el modo de organizar la producción y causas productivas cuando se produzcan cambios, entre otros, en la demanda de los productos o servicios que la empresa pretende colocar en el mercado.

(6) La demanda podrá fundarse en los siguientes motivos:

a) Que no concurre la causa legal indicada en la comunicación escrita.

b) Que no se ha realizado el período de consultas o entregado la documentación prevista en el artículo 51.2 ET.

c) Que la decisión extintiva se ha adoptado con fraude, dolo, coacción o abuso de derecho.

d) Que la decisión extintiva se ha efectuado vulnerando derechos fundamentales y libertades públicas.

(7) El artículo 51.1 ET dispone que se entenderá por despido colectivo la extinción de contratos de trabajo fundada en causas económicas, técnicas, organizativas o de producción cuando, en un período de noventa días la extinción afecta al menos a;

1-Diez trabajadores, en las empresas que ocupen menos de cien trabajadores.

2-El 10% del número de trabajadores de la empresa en aquellas que ocupen entre cien y trescientos trabajadores

3-Treinta trabajadores en las empresas que ocupen más de trescientos trabajadores.

4-La totalidad de la plantilla de la empresa, siempre que el número de trabajadores afectados sea superior a cinco, cuando aquel se produzca como consecuencia de la cesación total de su actividad empresarial.

La sentencia declarará nula la decisión extintiva cuando el empresario no haya realizado el período de consultas o entregado la documentación prevista en el artículo 51.2 ET o cuando la medida empresarial se haya efectuado con vulneración de derechos fundamentales y libertades públicas. La sentencia declarará no ajustada a derecho la decisión extintiva cuando el empresario no haya acreditado la concurrencia de la causa legal indicada en la comunicación extintiva (artículo 124.11 LRJS).

(8) El número de trabajadores de la empresa es importante para saber si ha de seguirse el cauce del despido colectivo (artículo 51.1 ET).

(9) Así lo establece el artículo 64.1 LRJS.

(10) Así está previsto en el artículo 124.11 párrafo 3º LRJS.

(11) Si el demandante va a acudir a juicio asistido de letrado o representado por graduado social o procurador, lo hará constar en la demanda por medio de OTROSÍ (véase demanda de despido tipo).

Si el demandante quiere solicitar la práctica de pruebas, lo hará asimismo por medio de OTROSÍ (véase demanda de despido tipo).

════════════════════════════════════════════════════════════════════════
