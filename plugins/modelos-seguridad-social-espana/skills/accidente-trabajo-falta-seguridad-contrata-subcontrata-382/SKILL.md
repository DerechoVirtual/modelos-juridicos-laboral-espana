---
name: accidente-trabajo-falta-seguridad-contrata-subcontrata-382
description: "Redacta el escrito «Accidente de trabajo por falta de seguridad en contrata o subcontrata: demanda de indemnización» (formulario 382 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Accidente de trabajo por falta de seguridad en contrata o subcontrata: demanda de indemnización

> Formulario 0382 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] CALLE
- [ ] NÚMERO
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE (3 veces)
- [ ] FECHA (3 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 16 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…, n.º [NÚMERO], de»; «… de daños y perjuicios contra la empresa»; «…y contra la empresa»; «…, dedicadas ambas a la actividad de»; «…en los siguientes HECHOS Primero.— Desde»; «…presto mis servicios en la empresa»; «…, con la categoría/grupo profesional de»; «…euros mensuales. Segundo.— Desde»; «…, la empresa»; «…viviendas que está construyendo sitas en»; «…staba realizando los siguientes trabajos»; «…ado las siguientes medidas de seguridad:»; …

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto Legislativo 8/2015
- Ley 31/1995

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

### Formulario 0382 · Accidente de trabajo por falta de seguridad en contrata o subcontrata: demanda de indemnización

- Año del modelo: 2013
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 29 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025)

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

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, con DNI n.º [DNI/NIE], y con domicilio en la calle [CALLE], n.º [NÚMERO], de [COMPLETAR], ante el Tribunal de Instancia comparezco y como mejor proceda en Derecho digo:

Que por medio del presente escrito promuevo demanda en reclamación de indemnización de daños y perjuicios contra la empresa [COMPLETAR] con domicilio en [LOCALIDAD] y contra la empresa [COMPLETAR], con domicilio en [LOCALIDAD], dedicadas ambas a la actividad de [COMPLETAR], demanda que fundamento en los siguientes

HECHOS

Primero.— Desde [COMPLETAR] presto mis servicios en la empresa [COMPLETAR], con la categoría/grupo profesional de [COMPLETAR] y salario de [IMPORTE] euros mensuales.

Segundo.— Desde [COMPLETAR], la empresa [COMPLETAR] contrató con la empresa con la que yo presto servicios la realización de toda la obra de albañilería de las viviendas que está construyendo sitas en [COMPLETAR].

Tercero.— El día [FECHA], mientras realizaba mi trabajo de albañil en las citadas viviendas, sufrí un accidente cuando estaba realizando los siguientes trabajos [COMPLETAR].

Cuarto.— El accidente de trabajo se produjo como consecuencia de que la empresa no había adoptado las siguientes medidas de seguridad: [COMPLETAR].

Quinto.— A consecuencia del accidente, presento las siguientes secuelas irreversibles: [COMPLETAR].

Sexto.— El daño sufrido deriva del accidente de trabajo producido por falta de medidas de seguridad, tal y como ha quedado consignado en el hecho cuarto.

Séptimo.— En concepto de indemnización de daños y perjuicios reclamo la cantidad de [IMPORTE] euros, que se fija teniendo en cuenta mi edad, cargas familiares, lesiones que presento tras la curación, limitaciones para desempeñar mi trabajo habitual, etc.(Si se utiliza el baremo de tráfico hacerlo constar)

Octavo.— Presenté papeleta de demanda de conciliación ante la SMAC, el día [FECHA] habiéndose celebrado el preceptivo acto conciliatorio el día [FECHA] con el resultado de [COMPLETAR].

FUNDAMENTOS DE DERECHO

Primero.— Ley reguladora de la Jurisdicción Social: Artículos 1, 2, 65, 80 y concordantes.

Segundo.— Real Decreto Legislativo 8/2015 [NOTA DE REVISIÓN: Errata. Fuente: LGSS (RDLeg 8/2015), BOE-A-2015-11724.], de 30 de octubre, por el que se aprueba el Texto Refundido de la Ley General de la Seguridad Social: Artículo 164.3.

Tercero.— Ley 31/1995, de 8 de noviembre, de Prevención de Riesgos Laborales, en especial los artículos 14, 15, 24 y 42.

Cuarto.— Código Civil: Artículo 1101.

Por todo lo expuesto,

SUPLICO AL TRIBUNAL que, teniendo por presentado este escrito con sus copias y documentos que acompaño, se sirva admitirlo y tenga por formulada demanda de indemnización de daños y perjuicios por falta de medidas de seguridad contra la empresa [COMPLETAR] y [COMPLETAR], se proceda a citar a las partes para los actos de conciliación y subsiguiente juicio y, seguido que sea por todos sus trámites, incluido el recibimiento del mismo a prueba que expresamente se solicita, se dicte en su día sentencia estimando la presente demanda, condenando solidariamente a las empresas demandadas a abonar al actor la cantidad de [IMPORTE] euros, importe de la indemnización de daños y perjuicios.

Es justicia que pido en [LUGAR], a [DÍA] de [MES] de [AÑO].

Firma

════════════════════════════════════════════════════════════════════════
