---
name: salarios-contra-grupo-laboral-empresas-demanda-387
description: "Redacta el escrito «Salarios contra grupo laboral de empresas: demanda» (formulario 387 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Salarios contra grupo laboral de empresas: demanda

> Formulario 0387 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS
- [ ] NÚMERO (3 veces)
- [ ] CALLE (2 veces)
- [ ] FECHA (3 veces)
- [ ] IMPORTE (7 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, nº [NÚMERO] de»; «…amación de cantidad, contra las empresas»; «…,»; «…, [COMPLETAR] y»; «…ido laboral, dedicadas a la actividad de»; «…, nº [NÚMERO], de»; «…estar servicios por cuenta de la empresa»; «…correspondientes al grupo profesional de»; «…los conceptos que asimismo se fijan. Año»; «…- Mes de»; «…en cuantía de [IMPORTE] euros. - Mes de»; «…euros. -P/P extra de»; …

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

### Formulario 0387 · Salarios contra grupo laboral de empresas: demanda

- Año del modelo: 2015
- Revisión 17-11-2026: 31 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Parte
HECHOS
FUNDAMENTOS DE DERECHO
Suplico
Lugar y fecha
Otrosí
A la Sección de lo Social del Tribunal de Instancia de [SEDE]

D. [NOMBRE Y APELLIDOS], con D.N.I. nº [NÚMERO], domiciliado en la calle [CALLE], nº [NÚMERO] de [COMPLETAR], ante el Tribunal de Instancia comparezco y, como mejor proceda en derecho digo:

Que por medio del presente escrito, en tiempo y forma legal, formulo demanda, en reclamación de cantidad, contra las empresas [COMPLETAR], [COMPLETAR] y [COMPLETAR], que forman un grupo de empresas en sentido laboral, dedicadas a la actividad de [COMPLETAR], con domicilio social en la calle [CALLE], nº [NÚMERO], de [COMPLETAR], demanda que fundamento en los siguientes

HECHOS

Primero.- Que ingresé a prestar servicios por cuenta de la empresa [COMPLETAR] con fecha [FECHA], realizando funciones correspondientes al grupo profesional de [COMPLETAR], percibiendo un salario mensual de [IMPORTE] euros que, incluida la prorrata de pagas extras asciende a la cantidad de [IMPORTE] euros mensuales.

Segundo.- Que por la empresa demandada no me han sido abonadas las cantidades que a continuación se consignan, correspondientes a los conceptos que asimismo se fijan.

Año [COMPLETAR]

- Mes de [COMPLETAR] en cuantía de [IMPORTE] euros.

- Mes de [COMPLETAR] en cuantía de [IMPORTE] euros.

-P/P extra de [COMPLETAR] en cuantía de [IMPORTE] euros

-TOTAL [IMPORTE] euros.

Tercero.- Que la empresa forma parte de un grupo de empresas en sentido laboral. En efecto concurren los requisitos exigidos por la jurisprudencia para considerar que existe grupo de empresas de dicha naturaleza:

-Ha habido prestación de servicios simultánea de los trabajadores [COMPLETAR] a las tres empresas del grupo.

-Existe unidad de caja.

-Existe una única dirección y un mismo Consejo de Administración en todas las empresas.

-La empresa [COMPLETAR] es titular de la totalidad de las acciones de las otras dos empresas.

Al existir grupo de empresas en sentido laboral, procede la condena solidaria de todas las empresas del grupo al abono de las cantidades pendientes de pago.

Cuarto.- Que se presentó papeleta de demanda proponiendo acto de conciliación ante el correspondiente servicio administrativo el día [FECHA], habiéndose celebrado el preceptivo acto conciliatorio el día [FECHA], con el resultado de

FUNDAMENTOS DE DERECHO

Primero.- Ley 36/2011, de 10 de octubre, Reguladora de la Jurisdicción Social, en especial los artículos 1, 2, 16, 23, 63 y 80.

Segundo.- Texto Refundido de la Ley del Estatuto de los trabajadores, aprobado por Real Decreto Legislativo 2/2015, de 23 de octubre, en especial los artículos 4. 2 f), 26, 29, 32 y 33.

Tercero.- Convenio Colectivo del Sector de [COMPLETAR]

Cuarto.- Todas las normas concordantes y complementarias aplicables al caso.

Por todo ello

SUPLICO AL TRIBUNAL que habiendo por presentada esta demanda con sus copias, se sirva admitirla, tenga por formulada demanda, en reclamación de cantidad, se proceda a citar a las partes para los actos de conciliación y subsiguiente juicio, por el que, en definitiva, seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba, que expresamente se solicita, se dicte en su día sentencia, estimando íntegramente la presente demanda, condenando solidariamente a las demandadas a abonarme la cantidad de [IMPORTE] euros mas los correspondiente intereses.

Es Justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma

OTROSÍ DIGO: Que acompaño una copia de la demanda para que sea citado el Fondo de Garantía Salarial, dándose traslado de la misma a fin de que pueda asumir sus obligaciones legales e instar lo que a su derecho convenga

════════════════════════════════════════════════════════════════════════
