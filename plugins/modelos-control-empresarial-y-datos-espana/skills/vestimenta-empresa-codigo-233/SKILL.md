---
name: vestimenta-empresa-codigo-233
description: "Redacta el escrito «Vestimenta en la empresa: código» (formulario 233 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Vestimenta en la empresa: código

> Formulario 0233 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

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

El formulario no tiene campos marcados: revisa el texto por si hay datos implícitos.

## Párrafos opcionales (29)

Inclúyelos solo si encajan en los hechos:

- • Trajes oscuros de corte clásico…
- • Corbatas conservadoras…
- • Camisas de vestir de colores o estampados clásicos…
- • Zapatos de hombre de cuero oscuro…
- • Calcetines oscuros…
- • Traje sastre de color oscuro…
- • Faldas de corte clásico hasta la rodilla o la pantorrilla…
- • Blusas planas con escotes conservadores y con mangas…
- • Medias lisas…
- • Zapatos de mujer de corte clásico de tacón cerrado o planos…
- • Joyas y complementos pequeños y discretos…
- • Pantalones tipo chinos o kahkis…
- • Vestidos y faldas hasta la rodilla o largas de colores claros…
- • Camisas tipo Oxford…
- • Camisas de manga corta o tipo polo…
- • Zapatos tipo casual de hombre (mocasines, náuticos) y zapatos abiertos de mujer…
- • Jerséis y cárdigan…
- • Estampados llamativos…
- • Camisas/blusas muy escotadas y sin mangas…
- • Vestidos/faldas por encima de la rodilla…
- • Vaqueros…
- • Camisetas deportivas…
- • Camisetas sin mangas…
- • Zapatillas de deporte, chanclas o sandalias…
- • Sudaderas…
- • Bermudas y pantalones cortos…
- • Pendientes en los hombres…
- • Joyas llamativas…
- Todos los trabajadores deben proyectar una imagen profesional adecuada a los principios de la empresa, por lo …

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

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

### Formulario 0233 · Vestimenta en la empresa: código

- Año del modelo: 2019
- Revisión 17-11-2026: 29 párrafos opcionales señalados

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

VESTIMENTA ADECUADA
VESTIMENTA INADECUADA

Información a los trabajadores sobre su código o política de vestimenta en la empresa

Con el fin de orientar a los trabajadores sobre las normas de uso de vestimenta y apariencia personal, el siguiente código establece qué prendas son apropiadas qué prendas son inapropiadas y no deben usarse en el entorno laboral.

VESTIMENTA ADECUADA

1) Atuendo formal

[OPCIONAL — incluir si procede]

• Trajes oscuros de corte clásico

[OPCIONAL — incluir si procede]

• Corbatas conservadoras

[OPCIONAL — incluir si procede]

• Camisas de vestir de colores o estampados clásicos

[OPCIONAL — incluir si procede]

• Zapatos de hombre de cuero oscuro

[OPCIONAL — incluir si procede]

• Calcetines oscuros

[OPCIONAL — incluir si procede]

• Traje sastre de color oscuro

[OPCIONAL — incluir si procede]

• Faldas de corte clásico hasta la rodilla o la pantorrilla

[OPCIONAL — incluir si procede]

• Blusas planas con escotes conservadores y con mangas

[OPCIONAL — incluir si procede]

• Medias lisas

[OPCIONAL — incluir si procede]

• Zapatos de mujer de corte clásico de tacón cerrado o planos

[OPCIONAL — incluir si procede]

• Joyas y complementos pequeños y discretos

2) Atuendo informal

[OPCIONAL — incluir si procede]

• Pantalones tipo chinos o kahkis

[OPCIONAL — incluir si procede]

• Vestidos y faldas hasta la rodilla o largas de colores claros

[OPCIONAL — incluir si procede]

• Camisas tipo Oxford

[OPCIONAL — incluir si procede]

• Camisas de manga corta o tipo polo

[OPCIONAL — incluir si procede]

• Zapatos tipo casual de hombre (mocasines, náuticos) y zapatos abiertos de mujer

[OPCIONAL — incluir si procede]

• Jerséis y cárdigan

VESTIMENTA INADECUADA

[OPCIONAL — incluir si procede]

• Estampados llamativos

[OPCIONAL — incluir si procede]

• Camisas/blusas muy escotadas y sin mangas

[OPCIONAL — incluir si procede]

• Vestidos/faldas por encima de la rodilla

[OPCIONAL — incluir si procede]

• Vaqueros

[OPCIONAL — incluir si procede]

• Camisetas deportivas

[OPCIONAL — incluir si procede]

• Camisetas sin mangas

[OPCIONAL — incluir si procede]

• Zapatillas de deporte, chanclas o sandalias

[OPCIONAL — incluir si procede]

• Sudaderas

[OPCIONAL — incluir si procede]

• Bermudas y pantalones cortos

[OPCIONAL — incluir si procede]

• Pendientes en los hombres

[OPCIONAL — incluir si procede]

• Joyas llamativas

[OPCIONAL — incluir si procede]

Todos los trabajadores deben proyectar una imagen profesional adecuada a los principios de la empresa, por lo que es importante que se cuide el aspecto físico con un adecuado aseo personal (cuidado del cabello, manos y uñas, maquillaje...) y una adecuada limpieza de las prendas, los zapatos y los complementos.

════════════════════════════════════════════════════════════════════════
