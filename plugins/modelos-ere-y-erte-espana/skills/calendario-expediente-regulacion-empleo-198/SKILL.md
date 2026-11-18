---
name: calendario-expediente-regulacion-empleo-198
description: "Redacta el escrito «Calendario del expediente de regulación de empleo» (formulario 198 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Calendario del expediente de regulación de empleo

> Formulario 0198 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] Otros 395 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…spensión o reducción de jornada) Nº ERE:»; «…DENOMINACIÓN SOCIAL DE LA EMPRESA:»; «…): La Jornada habitual de la empresa es:»; «…adores es: Los turnos de la empresa son:»; «…TADO: El periodo de suspensión es desde:»; «…do entre: El porcentaje de reducción es:»; «…El Horario de la reducción es:»; «…CALENDARIO 2020 ENERO»; «…FEBRERO»; «…FEBRERO [COMPLETAR] MARZO L»; «…MARZO L [COMPLETAR] M»; «…MARZO L [COMPLETAR] M [COMPLETAR] M»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

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

### Formulario 0198 · Calendario del expediente de regulación de empleo

- Año del modelo: 2020
- Revisión 17-11-2026: 388 campos de relleno marcados en blanco; 5 etiquetas sin dato marcadas en blanco; 2 huecos del original que se habían perdido sin marca, marcados (COMPLETAR)

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MODELO ORIENTATIVO DE CALENDARIO EN REGULACIÓN DE EMPLEO
    (Documento a presentar a la autoridad laboral tras la finalización del periodo de consultas en los
                            supuestos de suspensión o reducción de jornada)

Nº ERE:[COMPLETAR]
DENOMINACIÓN SOCIAL DE LA EMPRESA: [COMPLETAR]
NOMBRE TRABAJADOR AFECTADO: ……………………………………………………………………..
NOMBRE TRABAJADOR AFECTADO: ……………………………………………………………………..
………………………………………………………………………………………………………………………
LES AFECTA LA MISMA SUSPENSIÓN/REDUCCIÓN A TODOS LOS TRABAJADORES
AFECTADOS SI _ NO _

-EN CONDICIONES NORMALES (antes de la aplicación del ERE):
La Jornada habitual de la empresa es: [COMPLETAR]
El Horario habitual de los trabajadores es:
Los turnos de la empresa son: [COMPLETAR]
El horario/turno del trabajador afectado es:

- EN APLICACIÓN DEL ERE PRESENTADO:
El periodo de suspensión es desde: [COMPLETAR]
La reducción de jornada se aplica durante el periodo comprendido entre:

El porcentaje de reducción es: [COMPLETAR]
El Horario de la reducción es: [COMPLETAR]
El calendario de suspensión afecta a los días CONCRETOS:
-
-
-

Si la suspensión afecta a días laborables completos, se presentará también sombreado en gris, los días
del cuadro siguiente.
La reducción de jornada se identificará subrayando los días correspondientes.
www.larioja.org

                                                   CALENDARIO 2020

                    ENERO [COMPLETAR] FEBRERO [COMPLETAR] MARZO
  L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D
                   1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 1
  6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8
 13 [COMPLETAR] 14 [COMPLETAR] 15 16 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 13 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 [COMPLETAR] 9 [COMPLETAR] 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 13 [COMPLETAR] 14 [COMPLETAR] 15
 20 [COMPLETAR] 21 [COMPLETAR] 22 23 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 20 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 [COMPLETAR] 16 [COMPLETAR] 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 20 [COMPLETAR] 21 [COMPLETAR] 22
 27 [COMPLETAR] 28 [COMPLETAR] 29 30 31 [COMPLETAR] 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 27 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 23 [COMPLETAR] 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 27 [COMPLETAR] 28 [COMPLETAR] 29
                                                                                                      30 [COMPLETAR] 31

                       ABRIL [COMPLETAR] MAYO [COMPLETAR] JUNIO
  L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D
                   1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7
  6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 [COMPLETAR] 10 [COMPLETAR] 8 [COMPLETAR] 9 [COMPLETAR] 10 [COMPLETAR] 11 12 [COMPLETAR] 13 [COMPLETAR] 14
 13 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 13 14 15 [COMPLETAR] 16 [COMPLETAR] 17 [COMPLETAR] 15 [COMPLETAR] 16 [COMPLETAR] 17 [COMPLETAR] 18 19 [COMPLETAR] 20 [COMPLETAR] 21
 20 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 20 21 22 [COMPLETAR] 23 [COMPLETAR] 24 [COMPLETAR] 22 [COMPLETAR] 23 [COMPLETAR] 24 [COMPLETAR] 25 26 [COMPLETAR] 27 [COMPLETAR] 28
 27 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 30 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 27 28 29 [COMPLETAR] 30 [COMPLETAR] 31 [COMPLETAR] 29 [COMPLETAR] 30

                       JULIO [COMPLETAR] AGOSTO [COMPLETAR] SEPTIEMBRE
  L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D
                   1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6
  6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 10 11 12 [COMPLETAR] 13
 13 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 13 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 17 18 19 [COMPLETAR] 20
 20 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 20 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 24 25 26 [COMPLETAR] 27
 27 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 30 31 [COMPLETAR] 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 27 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 30 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 30

                   OCTUBRE [COMPLETAR] NOVIEMBRE [COMPLETAR] DICIEMBRE
  L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D [COMPLETAR] L [COMPLETAR] M [COMPLETAR] M [COMPLETAR] J [COMPLETAR] V [COMPLETAR] S [COMPLETAR] D
                       1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 1 [COMPLETAR] 1 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6
  5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 [COMPLETAR] 10 [COMPLETAR] 11 [COMPLETAR] 2 [COMPLETAR] 3 [COMPLETAR] 4 [COMPLETAR] 5 [COMPLETAR] 6 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 7 [COMPLETAR] 8 [COMPLETAR] 9 10 11 [COMPLETAR] 12 [COMPLETAR] 13
 12 [COMPLETAR] 13 [COMPLETAR] 14 15 16 [COMPLETAR] 17 [COMPLETAR] 18 [COMPLETAR] 9 [COMPLETAR] 10 [COMPLETAR] 11 [COMPLETAR] 12 [COMPLETAR] 13 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 14 [COMPLETAR] 15 [COMPLETAR] 16 17 18 [COMPLETAR] 19 [COMPLETAR] 20
 19 [COMPLETAR] 20 [COMPLETAR] 21 22 23 [COMPLETAR] 24 [COMPLETAR] 25 [COMPLETAR] 16 [COMPLETAR] 17 [COMPLETAR] 18 [COMPLETAR] 19 [COMPLETAR] 20 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 21 [COMPLETAR] 22 [COMPLETAR] 23 24 25 [COMPLETAR] 26 [COMPLETAR] 27
 26 [COMPLETAR] 27 [COMPLETAR] 28 29 30 [COMPLETAR] 31 [COMPLETAR] 23 [COMPLETAR] 24 [COMPLETAR] 25 [COMPLETAR] 26 [COMPLETAR] 27 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 28 [COMPLETAR] 29 [COMPLETAR] 30 31

      ATENCIÓN: Este calendario se presentará por cada uno de los trabajadores afectados. Si la
   totalidad de los trabajadores afectados tienen la misma reducción o misma suspensión se deberá
                                         indicar expresamente

“En todo caso, la comunicación deberá contemplar el calendario con los días concretos de suspensión de contratos o reducción de jornada
individualizados por cada uno de los trabajadores afectados. En el supuesto de reducción de la jornada, se determinará el porcentaje de [COMPLETAR]
disminución temporal, computada sobre la base diaria, semanal, mensual o anual, los periodos concretos en los que se va a producir la
reducción así como el horario de trabajo afectado por la misma, durante todo el periodo que se extienda su vigencia.” Real Decreto
1483/2012, de 29 de octubre, por el que se aprueba el Reglamento de los procedimientos de despido colectivo y de suspensión de [COMPLETAR]
contratos y reducción de jornada, ART.20.6

════════════════════════════════════════════════════════════════════════
