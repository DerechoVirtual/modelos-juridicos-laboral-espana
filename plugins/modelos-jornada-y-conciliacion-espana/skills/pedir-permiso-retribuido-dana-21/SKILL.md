---
name: pedir-permiso-retribuido-dana-21
description: "Redacta el escrito «Pedir permiso retribuido por la DANA» (formulario 21 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Pedir permiso retribuido por la DANA

> Formulario 0021 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- Medidas excepcionales del RDL 7/2024 (BOE-A-2024-23422, arts. 42-45) ligadas a la DANA de 28-10 a 4-11-2024 y solo mientras duren sus causas; para nuevos episodios rigen el art. 37.3.g) ET (hasta cuatro días por imposibilidad de acceso) y el ERTE de fuerza mayor del art. 47.6 ET. No se ha revisado el RDL 24/2026 (BOE-A-2026-20264), que contiene nuevas medidas DANA.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] NOMBRE Y APELLIDOS

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA OPCIÓN Y REDACTARLA: Estado de las vías de circulación o transporte público / Indicaciones de autoridades / Labores de limpieza o acondicionamiento de vivienda habitual / Trámites para documentos oficiales o públicos / Desaparición de familiar o persona conviviente / Fallecimiento familiar / Deber de cuidado de familiar o persona conviviente — el texto de cada opción no venía en el form

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 42.1 del Real Decreto-ley 7/2024

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

### Formulario 0021 · Pedir permiso retribuido por la DANA

- Año del modelo: 2024
- Revisión 17-11-2026: 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 2 campos de relleno marcados en blanco
- Avisos de la revisión: Medidas excepcionales del RDL 7/2024 (BOE-A-2024-23422, arts. 42-45) ligadas a la DANA de 28-10 a 4-11-2024 y solo mientras duren sus causas; para nuevos episodios rigen el art. 37.3.g) ET (hasta cuatro días por imposibilidad de acceso) y el ERTE de fuerza mayor del art. 47.6 ET. No se ha revisado el RDL 24/2026 (BOE-A-2026-20264), que contiene nuevas medidas DANA.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

Las personas trabajadoras podrán ausentarse del trabajo, con derecho a remuneración, por una serie de causas relacionadas con la DANA y mientras duren las mismas.

Att.

En [LUGAR], a [FECHA].

Estimados/as señores/as,

Por medio de la presente, y en virtud de lo establecido en el art. 42.1 del Real Decreto-ley 7/2024, de 11 de noviembre, por el que se adoptan medidas urgentes para el impulso del Plan de respuesta inmediata, reconstrucción y relanzamiento frente a los daños causados por la Depresión Aislada en Niveles Altos (DANA) en diferentes municipios entre el 28 de octubre y el 4 de noviembre de 2024, les solicito el disfrute de un permiso retribuido por el siguiente motivo:

[ELEGIR UNA OPCIÓN Y REDACTARLA: Estado de las vías de circulación o transporte público / Indicaciones de autoridades / Labores de limpieza o acondicionamiento de vivienda habitual / Trámites para documentos oficiales o públicos / Desaparición de familiar o persona conviviente / Fallecimiento familiar / Deber de cuidado de familiar o persona conviviente — el texto de cada opción no venía en el formulario original]

Atentamente,

Fdo. La persona trabajadora

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
