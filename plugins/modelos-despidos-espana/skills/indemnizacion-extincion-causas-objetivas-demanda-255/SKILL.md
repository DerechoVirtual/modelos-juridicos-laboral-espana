---
name: indemnizacion-extincion-causas-objetivas-demanda-255
description: "Redacta el escrito «Indemnización por extinción por causas objetivas: demanda» (formulario 255 de despido y extinción del contrato, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Indemnización por extinción por causas objetivas: demanda

> Formulario 0255 del plugin **Despido y extinción del contrato** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS
- [ ] Nº (3 veces)
- [ ] CALLE (2 veces)
- [ ] FECHA (6 veces)
- [ ] IMPORTE (5 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] LUGAR
- [ ] Otros 11 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… por causas objetivas, contra la empresa»; «…, dedicada a la actividad de»; «…ervicios durante los siguientes períodos»; «…en el grupo profesional»; «…poral estando prevista su duración hasta»; «… trabajo las siguientes características:»; «…e la empresa se dedica a la actividad de»; «…y ocupa»; «…, con el resultado de»; «…rcero.— Convenio colectivo del Sector de»; «…o por causas objetivas contra la empresa»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Ley 36/2011
- Real Decreto Legislativo 2/2015

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

### Formulario 0255 · Indemnización por extinción por causas objetivas: demanda

- Año del modelo: 2013
- Revisión 17-11-2026: 30 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (Nº)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Receptor
Demandante
Interposición
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Firmas

A la Sección de lo Social del Tribunal de Instancia de [SEDE]

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI núm. [Nº], y con domicilio en la calle [CALLE], ante el Tribunal de Instancia comparezco y, como mejor proceda en Derecho, digo:

Que por medio del presente escrito, en tiempo y forma legal, formulo demanda en reclamación de indemnización por extinción del contrato por causas objetivas, contra la empresa [COMPLETAR], dedicada a la actividad de [COMPLETAR], con domicilio social en la calle [CALLE], demanda que fundamento en los siguientes

HECHOS

Primero.— Que ingresé a prestar servicios por cuenta de la demandada con fecha [FECHA], habiendo prestado servicios durante los siguientes períodos [COMPLETAR] en el grupo profesional [COMPLETAR], percibiendo un salario mensual de [IMPORTE] euros, que incluida la prorrata de pagas extras asciende a [IMPORTE] euros mensuales, salario que se me abona mensualmente mediante transferencia bancaria a la cuenta núm. [Nº]. Mi contrato es temporal estando prevista su duración hasta [COMPLETAR], siendo mi jornada de [Nº] horas semanales.

Segundo.— Los servicios los presté en el centro de trabajo de la demandada, sito en [LOCALIDAD], en la sección de [LOCALIDAD], teniendo el trabajo las siguientes características: [COMPLETAR].

Tercero.— Con fecha [FECHA] recibí una carta de la demandada en la que me comunicaba la extinción del contrato por causas objetivas y textualmente hacía constar:

Cuarto.— Con fecha [FECHA] se produjo la extinción de mi contrato de trabajo, habiendo cesado de prestar servicios para la demandada a partir de dicha fecha.

Quinto.— Que la demandada no me ha abonado cantidad alguna en concepto de indemnización.

Sexto.— Que la indemnización que me corresponde por la extinción del contrato, teniendo en cuenta mi salario y antigüedad en la empresa, es de [IMPORTE] euros (salario diario x 20 x número de años de servicio, con un máximo de doce mensualidades).

Séptimo.— Que la empresa se dedica a la actividad de [COMPLETAR] y ocupa [COMPLETAR] trabajadores.

Octavo.— Que se presentó papeleta de demanda proponiendo acto de conciliación ante el servicio administrativo correspondiente el día [FECHA], habiéndose celebrado el preceptivo acto conciliatorio el día [FECHA], con el resultado de [COMPLETAR].

FUNDAMENTOS DE DERECHO

Primero.— Ley 36/2011, de 10 de octubre, reguladora de la Jurisdicción Social, en especial los artículos 1 y 2.

Segundo.— Texto Refundido de la Ley del Estatuto de los Trabajadores aprobado por Real Decreto Legislativo 2/2015, de 23 de octubre, en especial su artículo 53.1.b) que establece que simultáneamente a la entrega de la comunicación escrita ha de ponerse a disposición del trabajador la indemnización de veinte días por año de servicio, prorrateándose por meses los períodos de tiempo inferiores a un año y con un máximo de doce mensualidades, y en el presente supuesto el empresario no me ha abonado cantidad alguna, por lo que le reclamo la cantidad de [IMPORTE] euros correspondiente a dicha indemnización.

Tercero.— Convenio colectivo del Sector de [COMPLETAR].

Cuarto.— Todas las normas concordantes y complementarias aplicables al caso.

Por todo ello,

SUPLICO AL TRIBUNAL que, habiendo por presentada esta demanda con sus copias y documentos que acompaño, se sirva admitirla, tenga por formulada demanda en reclamación de indemnización por extinción de contrato por causas objetivas contra la empresa [COMPLETAR], se proceda a citar a las partes para los actos de conciliación y subsiguiente juicio, por el que, en definitiva, seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba que expresamente se solicita, se dicte en su día sentencia, estimando íntegramente la presente demanda, condenando a la empresa demandada a abonarme en concepto de indemnización por la extinción de mi contrato de trabajo por causas objetivas, la cantidad de [IMPORTE] euros.

Es justicia que pido en [LUGAR], a [FECHA].

Firma

════════════════════════════════════════════════════════════════════════
