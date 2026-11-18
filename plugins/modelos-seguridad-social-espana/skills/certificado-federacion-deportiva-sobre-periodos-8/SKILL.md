---
name: certificado-federacion-deportiva-sobre-periodos-8
description: "Redacta el escrito «Certificado de la federación deportiva sobre periodos de actividad como deportista profesional» (formulario 8 de seguridad social y accidentes de trabajo, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Certificado de la federación deportiva sobre periodos de actividad como deportista profesional

> Formulario 0008 del plugin **Seguridad Social y accidentes de trabajo** · revisado el 17-11-2026.

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

- RD 739/2026 en vigor desde el 25-12-2026; la federación certifica solo si el club cesó o no tiene datos, con el modelo del anexo II (art. 3, párrafo segundo).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA
- [ ] Otros 3 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ión. Federación deportiva que certifica:»; «…ortista profesional: Nombre y apellidos:»; «…DNI/NIE:»

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- Real Decreto 739/2026

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

### Formulario 0008 · Certificado de la federación deportiva sobre periodos de actividad como deportista profesional

- Año del modelo: 2026
- Revisión 17-11-2026: 1 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: RD 739/2026 en vigor desde el 25-12-2026; la federación certifica solo si el club cesó o no tiene datos, con el modelo del anexo II (art. 3, párrafo segundo).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Firmas

En los supuestos en que el club o entidad deportiva correspondiente haya cesado en su actividad, o no disponga de la información necesaria para acreditar los periodos de actividad de la persona deportista profesional, la federación deportiva competente emitirá dicha certificación conforme al modelo siguiente, siempre y cuando disponga de dicha información.

Federación deportiva que certifica: [COMPLETAR]

Motivo de la certificación por la federación (artículo 3, párrafo segundo, del Real Decreto 739/2026, de 23 de septiembre, por el que se establece el régimen jurídico para el cómputo como cotizados al Régimen General de la Seguridad Social, a efectos de la pensión de jubilación, de los periodos de actividad ejercidos como deportista profesional con anterioridad a su integración en el Régimen General de la Seguridad Social):

 El club o entidad deportiva ha cesado en su actividad.

 El club o entidad deportiva no dispone de la información necesaria para acreditar los periodos.

Datos personales de la persona que ejerció la actividad como deportista profesional:

Nombre y apellidos: [COMPLETAR]

DNI/NIE: [COMPLETAR]

Periodo de ejercicio en España como deportista profesional comprendido entre el 15 de marzo de 1980 y la fecha de integración en el Régimen General correspondiente a su colectivo según la normativa aplicable:

Desde: Hasta:

La presente certificación se expide en virtud de lo dispuesto en el artículo 3, párrafo segundo, del Real Decreto 739/2026, de 23 de septiembre, a efectos de acreditar los periodos de actividad desarrollados por la persona interesada como deportista profesional en virtud de un contrato profesional correspondiente a una relación laboral de carácter especial conforme a lo dispuesto en el Estatuto de los Trabajadores y en la normativa reguladora de la relación laboral especial de las personas deportistas profesionales vigentes en cada momento con la finalidad de que dichos periodos puedan ser computados como cotizados en el procedimiento de reconocimiento o revisión de la pensión de jubilación. Y para que conste, se expide la presente certificación a petición de la persona interesada.

En [LUGAR], a [FECHA].

(Firma de la persona representante de la federación deportiva competente)

════════════════════════════════════════════════════════════════════════
