---
name: respuesta-empresa-suspension-permiso-fallecimiento-13
description: "Redacta el escrito «Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales» (formulario 13 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales

> Formulario 0013 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

## Antes de usarlo: avisos de la revisión

El planteamiento del formulario está desfasado en algo. Corrígelo antes de redactar:

- RDL 20/2026: medidas temporales hasta que concluya la campaña de peligro alto de incendios de 2026 (art. 1.1); el permiso por fallecimiento dura hasta cinco días hábiles tras el sepelio (art. 4.1).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de [AÑO]. Muy Sr./Sra. nuestro/a:»; «… permiso retribuido por fallecimiento de»; «…e protección civil en las poblaciones de»

## Elecciones que hay que hacer

- 2 / 4

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto-ley 20/2026

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

### Formulario 0013 · Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales

- Año del modelo: 2026
- Revisión 17-11-2026: 1 desplegables y casillas convertidos en elección en blanco; 5 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: RDL 20/2026: medidas temporales hasta que concluya la campaña de peligro alto de incendios de 2026 (art. 1.1); el permiso por fallecimiento dura hasta cinco días hábiles tras el sepelio (art. 4.1).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

En virtud de lo establecido en el Real Decreto-ley 20/2026, de 29 de julio, por el que se establecen medidas urgentes de protección laboral y social frente a los incendios forestales si, como consecuencia de los incendios forestales que den lugar a la adopción de medidas de protección civil que afecten a la población, tales como evacuaciones, restricciones de acceso, confinamientos u otras de naturaleza análoga, hasta que concluya la campaña anual de peligro alto de incendios forestales del año 2026, las personas trabajadoras, cuando su domicilio se encuentre en algún municipio afectado, tendrán derecho a suspender su contrato de trabajo y solicitar la prestación extraordinaria por emergencia extrema si se encuentran en determinadas situaciones (imposibilidad de acceder al domicilio, labores de traslado, cuidado de personas,…). Asimismo, en caso de fallecimiento de familiares como consecuencia de causas relacionadas con los incendios, tendrán derecho a una ampliación del permiso retribuido por fallecimiento.

Sr./Sra. [NOMBRE Y APELLIDOS]

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Muy Sr./Sra. nuestro/a: [COMPLETAR]

Acusamos recibo de su solicitud de [FECHA]

suspensión del contrato de trabajo

disfrute del permiso retribuido por fallecimiento de [COMPLETAR] como consecuencia de los incendios forestales que han dado lugar a la adopción de medidas de protección civil en las poblaciones de [COMPLETAR] y le comunicamos su derecho a lo solicitado en virtud de lo establecido en el art. [ELEGIR: 2 / 4] del Real Decreto-ley 20/2026, de 29 de julio, por el que se establecen medidas urgentes de protección laboral y social frente a los incendios forestales.

Sin otro particular, le saluda atentamente,

Fdo.: La empresa

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
