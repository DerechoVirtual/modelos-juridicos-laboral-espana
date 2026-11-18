---
name: impugnar-liquidacion-intereses-ejecucion-laboral-163
description: "Redacta el escrito «Impugnar la liquidación de intereses en la ejecución laboral» (formulario 163 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Impugnar la liquidación de intereses en la ejecución laboral

> Formulario 0163 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NÚMERO (3 veces)
- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS
- [ ] bien en todo o bien en parte
- [ ] IMPORTE (6 veces)
- [ ] Nº
- [ ] LUGAR
- [ ] FECHA
- [ ] Otro dato sin etiqueta, marcado `[COMPLETAR]`. Su contexto en el formulario: «…D»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 269 de la Ley 36/2011
- artículo 29.3 del ET
- art. 29.3 ET
- art. 29.3 del TRET
- art. 251 de la LRJS
- art. 576 de la LEC
- art. 576 LEC
- art. 230 LRJS

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

### Formulario 0163 · Impugnar la liquidación de intereses en la ejecución laboral

- Año del modelo: 2021
- Revisión 17-11-2026: 15 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Digo
MOTIVOS
Suplico
Firmas

Proceso de ejecución número [NÚMERO]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE]

D [COMPLETAR], procurador/letrado/graduado social, en nombre y representación de la D./Dña. [NOMBRE Y APELLIDOS], conforme consta debidamente acreditado en la ejecución núm. [NÚMERO], derivada del proceso núm. [NÚMERO], que se sigue ante ese Tribunal, comparezco y como mejor proceda en derecho, DIGO:

Que evacuando el traslado y dentro del plazo concedido al efecto, paso a IMPUGNAR la liquidación de intereses practicada en este proceso de ejecución, de conformidad a lo dispuesto en el artículo 269 de la Ley 36/2011, de 10 de octubre, reguladora de la jurisdicción social (LRJS), en base a los siguientes

MOTIVOS

PRIMERO.- La liquidación de intereses practicada no se ajusta a lo dispuesto en el artículo 29.3 del ET puesto que los intereses a aplicar son los de mora laboral.

Así lo expresa la doctrina consolidada de la Sala de lo Social del Tribunal Supremo, que se condensa STS (Cuarta) de 5 de mayo de 2.014 (recurso 1680/2013) que establece la aplicación flexible del interés «indemnizatorio» del Código Civil como regla general en toda clase de deudas laborales, de manera tal que el mismo se devengue siempre desde la reclamación del débito, cualquiera que éste sea y siempre que haya prosperado [bien en todo o bien en parte], y tratándose de concretas deudas salariales la solución ofrecida por el legislador -ex art. 29.3 ET - ha de operar también de forma objetiva, sin tener en cuenta ni la posible razonabilidad de la oposición empresarial a su pago, ni que en los concretos periodos económicos esa cifra -diez por ciento- sea superior o inferior a la inflación.

La jurisprudencia ha indicado que, en cuanto a la diferencia entre los intereses moratorios y los procesales, que la finalidad del interés moratorio es la de resarcir y reparar el perjuicio causado por el incumplimiento de los plazos estipulados, como es el caso objeto de este proceso, mientras que la del interés procesal es doble pues además de penalizar el retardo en el cumplimiento de la obligación tiene una finalidad disuasoria o punitiva, desmotivando la interposición de recursos, previéndose a tal fin un recargo de dos puntos sobre el interés moratorio, tal como indica STS 9 de febrero de 2015 (Rec. 2054/2014).

En este caso, son de aplicación los intereses moratorios atendida la naturaleza de la deuda, por lo que solicitamos que se aplique el interés de mora laboral al 10% conforme a lo prevenido en el art. 29.3 del TRET, desde el momento de la reclamación, por lo que los intereses ascienden a un total de [IMPORTE] euros.

SEGUNDO.- Subsidiariamente, sería en todo caso de aplicación el interés de mora procesal, conforme al art. 251 de la LRJS, en relación al art. 576 de la LEC al que se remite, el cual opera ex lege, de forma automática y sin necesidad de especial pronunciamiento, el cual se devenga desde la fecha de la sentencia dictada en primera instancia.

En cuanto al “dies a quo” de los intereses procesales, como regla general la obligación de pagar intereses procesales nace en el momento de la firmeza de la sentencia de condena, pero sus efectos se retrotraen a la fecha de la primera sentencia definitiva que condenó al pago de cantidad líquida, lo cual viene siendo establecido por el Tribunal Supremo de forma constante desde su Sentencia de fecha 11 de febrero de 1997 (Rec. 3099/1996), y así se recoge expresamente en el art. 251 de la LRJS, que se remite al art. 576 de la LECiv, precepto que dispone que desde que fuere dictada en primera instancia, toda sentencia o resolución que condene al pago de una cantidad de dinero líquida determinará, en favor del acreedor, el devengo de un interés anual igual al del interés legal del dinero incrementado en dos puntos o el que corresponda por pacto de las partes o por disposición especial de la ley.

En los casos de revocación parcial, el tribunal resolverá sobre los intereses de demora procesal conforme a su prudente arbitrio, habiendo reiterado la jurisprudencia que, incluso en caso de no disponerse nada en la sentencia revocatoria parcial que reduce la cantidad líquida objeto de condena fijada en la primera sentencia, la fecha del devengo de los intereses ex art. 576 LEC lo es desde la fecha de la primera sentencia pero por la suma fijada en la segunda sentencia.

Por tanto, en caso de entender que proceden los intereses procesales, la fecha ha de ser la de primera instancia devengando la cantidad adeudada el interés legal más dos puntos, lo que arroja un total de [IMPORTE] euros.

TERCERO.- En cuanto al “dies ad quem” o fecha final del periodo, también debe impugnarse la liquidación, puesto que la consignación realizada por la empresa no se hizo como medio extintivo de la obligación (arts. 1.176 y siguientes del Código Civil) en trámite de ejecución de sentencia, sino como requisito de "consignación aseguratoria" de la condena para poder recurrir en suplicación (art. 230 LRJS), habiendo expresado la jurisprudencia que ello no comporta ofrecimiento de pago alguno, sino como se ha dicho tan sólo su aseguramiento, tal como se indica en la STS de 05 de mayo de 2014 (Recurso 1680/2013).

En suma, el devengo de los intereses no se paraliza con la consignación efectuada ante el Tribunal al momento de recurrir la sentencia, por lo que el periodo de liquidación de intereses ha de comprender desde la fecha de la reclamación o, en su caso, desde la sentencia de primera instancia, hasta el día en que se puso a disposición de esta parte actora la cantidad objeto de la condena.

De acuerdo a lo expuesto, el periodo de intereses sería de [Nº] días, solicitándose con carácter principal la cantidad [IMPORTE] euros, por aplicación del interés moratorio y, con carácter subsidiario, la cantidad de [IMPORTE] euros por aplicación de los intereses procesales, formulando impugnación de la liquidación practicada a fin de que se dicte otra en la que se calculen los intereses conforme a lo interesado por esta parte.

Por lo expuesto,

SUPLICO AL TRIBUNAL: Que admita este escrito con sus copias, se tenga por impugnada liquidación y que, con estimación de las alegaciones de esta parte, se fije la cantidad de [IMPORTE] euros, en concepto de liquidación de intereses moratorios, o de forma subsidiaria, la de [IMPORTE] euros, en concepto de intereses procesales.

Es Justicia que pido,

En [LUGAR], a [FECHA].

Fdo.:(firma letrado/graduado social/procurador)

════════════════════════════════════════════════════════════════════════
