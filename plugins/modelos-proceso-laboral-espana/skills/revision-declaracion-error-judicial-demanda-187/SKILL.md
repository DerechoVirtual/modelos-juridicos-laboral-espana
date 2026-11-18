---
name: revision-declaracion-error-judicial-demanda-187
description: "Redacta el escrito «Revisión y declaración de error judicial: demanda» (formulario 187 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Revisión y declaración de error judicial: demanda

> Formulario 0187 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- Depósito de la revisión y del error judicial en lo social: 600 € (arts. 229.1.b) y 236 LRJS); la acción de error judicial caduca a los tres meses (art. 293.1.a) LOPJ).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DOMICILIO A EFECTOS DE NOTIFICACIONES
- [ ] NOMBRE DEL REPRESENTADO/A
- [ ] COLEGIO
- [ ] Nº DE RESOLUCIÓN (2 veces)
- [ ] Nº DE PROCEDIMIENTO (2 veces)
- [ ] FECHA (5 veces)
- [ ] ÓRGANO O PERSONA (2 veces)
- [ ] ÓRGANO
- [ ] LOCALIDAD
- [ ] LUGAR
- [ ] Otros 7 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…con número de colegiado/a»; «…en el procedimiento»; «…empo y forma por esta parte por entender»; «…e de un grave error judicial, por cuanto»; «… a ser indemnizado por error judicial en»; «…En cuanto al daño generado a esta parte,»; «…gar y fecha indicados ut supra. Firmado:»

## Elecciones que hay que hacer

- poder para pleitos / designación apud acta ante el/la Letrado/a de la Administración de Justicia en el momento en que se designe
- actora / demandada

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 236.1 LRJS
- art. 510 LEC
- art. 86.3 LRJS
- art. 293 de la Ley Orgánica 6/1985
- artículos 6 y 7 de la Ley 1/2000
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

### Formulario 0187 · Revisión y declaración de error judicial: demanda

- Año del modelo: 2020
- Revisión 17-11-2026: 1 puntualizaciones normativas añadidas en el texto; 2 desplegables y casillas convertidos en elección en blanco; 24 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Depósito de la revisión y del error judicial en lo social: 600 € (arts. 229.1.b) y 236 LRJS); la acción de error judicial caduca a los tres meses (art. 293.1.a) LOPJ).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

HECHOS
FUNDAMENTOS DE DERECHO
Firmas

En virtud de lo establecido en el art. 236.1 LRJS, contra cualquier sentencia firme dictada por los órganos del orden jurisdiccional social y contra los laudos arbitrales firmes sobre materias objeto de conocimiento del orden social, procederá la revisión prevista en la LEC, por los siguientes motivos (de los art. 510 LEC y art. 86.3 LRJS):

- Si después de pronunciada, se recobraren u obtuvieren documentos decisivos, de los que no se hubiere podido disponer por fuerza mayor o por obra de la parte en cuyo favor se hubiere dictado.

- Si hubiere recaído en virtud de documentos que al tiempo de dictarse ignoraba una de las partes haber sido declarados falsos en un proceso penal, o cuya falsedad declarare después penalmente.

- Si hubiere recaído en virtud de prueba testifical o pericial, y los testigos o los peritos hubieren sido condenados por falso testimonio dado en las declaraciones que sirvieron de fundamento a la sentencia.

- Si se hubiere ganado injustamente en virtud de cohecho, violencia o maquinación fraudulenta.

- Cuando el Tribunal Europeo de Derechos Humanos haya declarado que dicha resolución ha sido dictada en violación de alguno de los derechos reconocidos en el Convenio Europeo para la Protección de los Derechos Humanos y Libertades Fundamentales y sus Protocolos, siempre que la violación, por su naturaleza y gravedad, entrañe efectos que persistan y no puedan cesar de ningún otro modo que no sea mediante esta revisión, sin que la misma pueda perjudicar los derechos adquiridos de buena fe por terceras personas.

- Si cualquier cuestión prejudicial penal diera lugar a sentencia absolutoria por inexistencia del hecho o por no haber participado el sujeto en el mismo.

El proceso de error judicial, destinado a reparar el daño producido por una resolución firme errónea que carece de posibilidad de rectificación por la vía normal de los recursos, cuando sea competencia de la Sala de lo Social del Tribunal Supremo, se seguirá por los trámites y requisitos establecidos para la declaración de error judicial en los artículos 292 y concordantes de la Ley Orgánica del Poder Judicial, con las especialidades sobre depósitos, vista y costas establecidas para la revisión y sin que la apreciación del error pueda fundamentarse en pruebas distintas de las practicadas en las actuaciones procesales origen del mismo presunto error.

Si la Sala apreciara la concurrencia de cualquiera de tales causas de inadmisión dictará auto, contra el cual no cabe recurso.

El citado precepto de la LOPJ expresa que los daños causados en cualesquiera bienes o derechos por error judicial, así como los que sean consecuencia del funcionamiento anormal de la Administración de Justicia, darán a todos los perjudicados derecho a una indemnización a cargo del estado, salvo en los casos de fuerza mayor, con arreglo a lo dispuesto en el Título V del Libro III LOPJ.

En todo caso, el daño alegado habrá de ser efectivo, evaluable económicamente e individualizado con relación a una persona o grupo de personas.

La mera revocación o anulación de las resoluciones judiciales no presupone por sí sola derecho a indemnización.

Actualizado según las modificaciones introducidas por la Ley Orgánica 1/2025, de 2 de enero, de medidas en materia de eficiencia del Servicio Público de Justicia.

A LA SALA CUARTA, DE LO SOCIAL, DEL TRIBUNAL SUPREMO

D./Dña. [NOMBRE Y APELLIDOS], Procurador/a de los Tribunales, según acredito mediante [ELEGIR: poder para pleitos / designación apud acta ante el/la Letrado/a de la Administración de Justicia en el momento en que se designe], con domicilio a efectos de notificaciones en [DOMICILIO A EFECTOS DE NOTIFICACIONES], en nombre y representación de [NOMBRE DEL REPRESENTADO/A], ante la Sala de lo Social del Tribunal Supremo comparezco y, como mejor proceda en Derecho, DIGO:

Que, en la representación que me ha sido conferida y bajo la dirección letrada de D/Dña. [NOMBRE Y APELLIDOS] adscrito/a al Ilmo. Colegio de Abogados de [COLEGIO] con número de colegiado/a [COMPLETAR], a través del presente escrito interpongo DEMANDA DE DECLARACIÓN DE ERROR JUDICIAL contra la sentencia número [Nº DE RESOLUCIÓN], en los autos número [Nº DE PROCEDIMIENTO], de fecha [FECHA], dictada por el [ÓRGANO O PERSONA].

HECHOS

PRIMERO.- Que mi representado/a ha sido parte [ELEGIR: actora / demandada] en el procedimiento [COMPLETAR], tramitado ante el [ÓRGANO].

SEGUNDO.- Que en el citado procedimiento fue dictada sentencia en fecha [FECHA], desestimando las pretensiones de esta parte.

TERCERO.- Que la supracitada sentencia devino firme, al ser recurrida en tiempo y forma por esta parte por entender [COMPLETAR], resultando desestimado finalmente el recurso mediante sentencia de fecha [FECHA].

Acompaño copia de estas resoluciones como documentos números.

CUARTO.- Que la última resolución adolece de un grave error judicial, por cuanto [COMPLETAR].

QUINTO.- Teniendo en cuenta el mencionado error, se ha producido un grave perjuicio patrimonial a los intereses de esta parte, que debe resarcirse mediante una indemnización a cargo del Estado, previa declaración judicial por causa de error, de acuerdo con el art. 293 de la Ley Orgánica 6/1985, de 1 de julio, del Poder Judicial.

Son de aplicación a los anteriores hechos los siguientes

FUNDAMENTOS DE DERECHO

PRIMERO.- La parte demandante se encuentra conveniente legitimada conforme a las reglas previstas en los artículos 16 y 17 de la Ley reguladora de la jurisdicción social, en concordancia con los artículos 6 y 7 de la Ley 1/2000, de 7 de enero, de Enjuiciamiento Civil.

SEGUNDO.- La solicitud de declaración se formula mediante Procurador/a debidamente habilitado y bajo la dirección letrada de Abogado, conforme faculta el artículo 21 de la Ley reguladora de la jurisdicción social.

TERCERO.- Es competente para la tramitación del proceso de error judicial la Sala Cuarta, de lo Social, del Tribunal Supremo, de acuerdo con el artículo 236.2 de la Ley reguladora de la jurisdicción social y el artículo 293.1.b) de la Ley Orgánica del Poder Judicial, siguiéndose las reglas de los artículos 292 y siguientes de esta última norma.

CUARTO.- De conformidad con el artículo 293.1 de la Ley Orgánica del Poder Judicial, la reclamación de indemnización por causa de error deberá ir precedida de una decisión judicial que expresamente lo reconozca. Esta previa decisión podrá resultar directamente de una sentencia dictada en virtud de recurso de revisión; del mismo modo, se obedece la prescripción de la letra a) del citado artículo, presentándose la acción judicial dentro del plazo máximo de tres meses a partir del día en que pudo ejercitarse, en este caso la notificación de la sentencia que adolece de error.

QUINTO.- De acuerdo con el artículo 293.1.c) de la Ley Orgánica del Poder Judicial, deberán ser parte en el procedimiento el Ministerio Fiscal y la Administración del Estado.

SEXTO.- Respecto del fondo del asunto, el artículo 292 de la Ley Orgánica del Poder Judicial expresa que los daños causados en cualesquiera bienes o derechos por error judicial, así como los que sean consecuencia del funcionamiento anormal de la Administración de Justicia, darán a todos los perjudicados derecho a una indemnización a cargo del estado, salvo en los casos de fuerza mayor.

De acuerdo con el citado precepto, el daño producido a esta parte es efectivo, evaluable económicamente e individualizado.

La jurisprudencia es clara en este sentido, y proclama el derecho a ser indemnizado por error judicial en [COMPLETAR].

El error judicial cometido por el Tribunal consistió en [LOCALIDAD].

En cuanto al daño generado a esta parte, [COMPLETAR].

Por lo expuesto,

SUPLICO A LA SALA que, teniendo por presentado este escrito y sus documentos acompañatorios, se sirva admitirlo y, en su virtud, tenga por instada DEMANDA DE DECLARACIÓN DE ERROR JUDICIAL contra la sentencia número [Nº DE RESOLUCIÓN] en los autos número [Nº DE PROCEDIMIENTO], de fecha [FECHA], dictada por el [ÓRGANO O PERSONA] y, tras los trámites oportunos, declare la existencia de error judicial cometido por el citado órgano jurisdiccional.

Es Justicia que pido en [LUGAR], a [FECHA].

OTROSÍ DIGO: que acompaño justificante del depósito exigido [NOTA DE REVISIÓN: En el orden social el depósito de la revisión y del error judicial es el de casación: 600 € (arts. 229.1.b) y 236 LRJS), no el del art. 513 LEC. Fuente: arts. 229.1.b) y 236.1-2 LRJS (red. LO 1/2025); LRJS (Ley 36/2011), BOE-A-2011-15936.], por realizarse los trámites bajo las reglas de la demanda de revisión (artículo 513.1 de la Ley de Enjuiciamiento Civil).

SUPLICO A LA SALA: tenga por cumplido el referido trámite.

SEGUNDO OTROSÍ DIGO: que intereso el recibimiento del pleito a prueba, aportando como prueba documental la que acompaña al cuerpo de este escrito, designando además los archivos de todas las instituciones, públicas y privadas, citadas en el mismo, y aun cuando no lo fueran.

SUPLICO A LA SALA: tenga por realizada dicha manifestación a los efectos oportunos.

Es Justicia que reitero en el lugar y fecha indicados ut supra.

Firmado: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
