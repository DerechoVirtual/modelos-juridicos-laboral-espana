---
name: memoria-sobre-organizacion-empresa-trabajo-temporal-258
description: "Redacta el escrito «Memoria sobre la organización de una empresa de trabajo temporal» (formulario 258 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Memoria sobre la organización de una empresa de trabajo temporal

> Formulario 0258 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] SEDE (2 veces)
- [ ] Nº (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] IMPORTE
- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 19 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…D./Dña. [NOMBRE Y APELLIDOS] La entidad»; «…resa de trabajo temporal, que denominará»; «…MPRESA DE TRABAJO TEMPORAL - Nombre ETT:»; «…. - NIF y CCC:»; «…. - Domicilio social:»; «…ación profesional. - Empleados actuales:»; «…. - Centros de trabajo. La empresa tiene»; «…Centro de trabajo:»; «…. 2) EQUIPO DIRECTIVO -»; «…. 2) EQUIPO DIRECTIVO - [COMPLETAR]. -»; «…presa se organiza de la siguiente forma:»; «…do los siguientes procesos tecnológicos:»; …

## Párrafos opcionales (1)

Inclúyelos solo si encajan en los hechos:

- Centro de trabajo: [COMPLETAR].…

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 4.2 d) del Real Decreto 417/2015

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

### Formulario 0258 · Memoria sobre la organización de una empresa de trabajo temporal

- Año del modelo: 2017
- Revisión 17-11-2026: 2 citas normativas corregidas tras comprobarlas en el BOE; 1 párrafos repetibles señalados; 24 campos de relleno marcados en blanco; 1 encabezamientos del órgano social completados (Sección de lo Social del Tribunal de Instancia, LO 1/2025); 1 notas de revisión repetidas retiradas

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]
DATOS BÁSICOS DE LA EMPRESA DE TRABAJO TEMPORAL
EQUIPO DIRECTIVO
ESTRUCTURA ORGANIZATIVA
PREVISIONES PARA EL PERIODO
Firmas

Modelo de memoria explicativa de la estructura organizativa de la empresa, detallada por centros de trabajo, que debe acompañarse a la solicitud de autorización inicial de una empresa de trabajo temporal, entre otros documentos, por medios electrónicos, conforme a lo establecido en el artículo 4.2 d) del Real Decreto 417/2015, por el que se aprueba el Reglamento de las empresas de trabajo temporal

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

D./Dña. [NOMBRE Y APELLIDOS]

La entidad [COMPLETAR] pretende constituirse como empresa de trabajo temporal, que denominará [COMPLETAR], a cuyo fin acompaña esta Memoria explicativa de su estructura organizativa a la solicitud de autorización como tal, de conformidad con lo dispuesto en el artículo 4.2 d) del Real Decreto 417/2015, de 29 de mayo, por el que se aprueba el Reglamento de las empresas de trabajo temporal.

La empresa dispone de una estructura organizativa que le permitirá, en su caso, cumplir las obligaciones que asume como empleador de trabajo temporal en relación con el objeto social, que es la contratación de personas trabajadoras para cederlas temporalmente a otra empresa usuaria y actuar como agencias de colocacióny desarrollar actividades de formación para la cualificación profesional.

1) DATOS BÁSICOS DE LA EMPRESA DE TRABAJO TEMPORAL

- Nombre ETT: [COMPLETAR].
- NIF y CCC: [COMPLETAR].
- Domicilio social: [COMPLETAR].
- Actividad: contratación de personas trabajadoras para cederlas temporalmente a otra empresa usuaria y actuar como agencias de colocacióny desarrollar actividades de formación para la cualificación profesional.
- Empleados actuales: [COMPLETAR].
- Garantía financiera: Se ha constituido la garantía financiera de [IMPORTE] euros, conforme se acredita mediante la documentación que asimismo se acompaña a la solicitud.
- Centros de trabajo. La empresa tiene [COMPLETAR] centros de trabajo:
[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

Centro de trabajo: [COMPLETAR].

2) EQUIPO DIRECTIVO

- [COMPLETAR].
- [COMPLETAR].

3) ESTRUCTURA ORGANIZATIVA

La empresa se organiza de la siguiente forma: [COMPLETAR].

Para la selección y formación de las personas trabajadoras contratadas se han utilizado los siguientes procesos tecnológicos: [COMPLETAR].

- Plantilla actual de la empresa: [COMPLETAR].
- Desglose de la plantilla por funciones y centros de trabajo: [COMPLETAR].
- Niveles alcanzados de capacitación técnico-profesional por las personas trabajadoras: [COMPLETAR].
- Política de RRHH: [COMPLETAR].

Se acompaña el siguiente gráfico de la estructura organizativa.

4) PREVISIONES PARA EL PERIODO [COMPLETAR]

Actuaciones de la empresa y Plan de Trabajo previsto en términos de:

- Equipo Directivo: [COMPLETAR].
- RRHH y Estructura Organizativa: [COMPLETAR].

En [LUGAR], a [FECHA].

D./Dña. [NOMBRE Y APELLIDOS]

Gerente
Apoderado
Representante de la empresa

════════════════════════════════════════════════════════════════════════
