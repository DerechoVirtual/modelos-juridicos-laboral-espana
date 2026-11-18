---
name: mecanismo-red-peticion-empresa-constituir-comision-64
description: "Redacta el escrito «Mecanismo RED: petición de la empresa para constituir la comisión negociadora» (formulario 64 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Mecanismo RED: petición de la empresa para constituir la comisión negociadora

> Formulario 0064 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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

- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ET. A todas las personas trabajadoras de»; «…En»; «…En [COMPLETAR] Muy Sres. Nuestros:»

## Elecciones que hay que hacer

- reducción de la jornada / suspensión de contratos
- cíclica / sectorial

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 41.4 ET
- artículos 47 bis y 41.4 del Estatuto de los Trabajadores
- artículo 47 bis.3 del Estatuto de los Trabajadores
- artículo 6 del RD 608/2023

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

### Formulario 0064 · Mecanismo RED: petición de la empresa para constituir la comisión negociadora

- Año del modelo: 2023
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 1 desplegables convertidos en elección en blanco; 5 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

La dirección de la empresa debe comunicar de manera fehaciente a las personas trabajadoras o a sus representantes su intención de iniciar el procedimiento, a los efectos de la conformación de la comisión representativa de los trabajadores en el centro/s de trabajo afectado/s.

La comisión negociadora debe quedar constituida con carácter previo a la apertura del período de consultas, en un plazo máximo de 5 días desde la comunicación, o de 10 si alguno de los centros de trabajo afectados no cuenta con representantes de los trabajadores.

En el supuesto de que no exista representación legal de las personas trabajadoras, la comisión representativa se integrará por los sindicatos más representativos del sector al que pertenezca la empresa y con legitimación para formar parte de la comisión negociadora del convenio colectivo de aplicación; o, en su defecto, por 3 trabajadores de la propia empresa, elegidos conforme a lo recogido en el artículo 41.4 ET.

A todas las personas trabajadoras de [COMPLETAR]

En [COMPLETAR]

Muy Sres. Nuestros: [COMPLETAR]

En virtud de la presente les comunicamos que la dirección de la empresa entiende necesaria la adopción de la medida consistente en la [ELEGIR: reducción de la jornada / suspensión de contratos] de las personas trabajadoras de la empresa, como consecuencia de la activación por parte del Consejo de Ministros, con fecha [FECHA] del Mecanismo RED de Flexibilidad y Estabilización del Empleo en su modalidad [ELEGIR: cíclica / sectorial].

Por ello, y al amparo de lo establecido en los artículos 47 bis y 41.4 del Estatuto de los Trabajadores, les comunicamos que pueden atribuir su representación para la negociación de un acuerdo en el periodo de consultas previsto en el artículo 47 bis.3 del Estatuto de los Trabajadores y artículo 6 del RD 608/2023, de 11 de julio, a una comisión de un máximo de tres miembros integrada por personas trabajadoras de la empresa y elegida por Ustedes democráticamente.

Dicha comisión representativa de las personas trabajadoras deberá quedar constituida con carácter previo a la comunicación empresarial del inicio del periodo de consultas, y en todo caso en el plazo máximo de 10 días al no existir representación legal en este centro de trabajo.

Les rogamos que firmen esta comunicación como prueba de su recepción y quedamos a la espera de su contestación.

Atentamente,

Empresa

Recibí

Personas trabajadoras

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
