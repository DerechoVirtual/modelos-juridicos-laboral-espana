---
name: embargo-preventivo-bienes-tras-demanda-medida-cautelar-122
description: "Redacta el escrito «Embargo preventivo de bienes tras la demanda: medida cautelar» (formulario 122 de proceso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Embargo preventivo de bienes tras la demanda: medida cautelar

> Formulario 0122 del plugin **Proceso laboral** · revisado el 17-11-2026.

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

- «Juzgado de lo Social» → Sección de lo Social del Tribunal de Instancia (LO 1/2025, DA 1.ª); el embargo preventivo cabe en cualquier momento antes de la sentencia (art. 79.4 LRJS).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] SEDE (2 veces)
- [ ] Nº (3 veces)
- [ ] Nº DE PROCEDIMIENTO
- [ ] FECHA (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] 728.2 de la LEC
- [ ] LUGAR
- [ ] Otros 12 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…– Plaza n.º [Nº]»; «…Parte actora:»; «…Parte demandada:»; «…de conciliación y juicio para el próximo»; «…sulta de la demanda es la fabricación de»; «…ervicios en el taller de la Empresa como»; «…ia falta de ocupación. – Documentos tres»; «… bienes que se relacionan a continuación»; «…: a. Requerir al administrador/a Don/Dña»; «…la vista. b. Se cite como testigos a Don»; «…y Doña»; «… lugar y fecha arriba mencionados. Fdo.:»

## Correcciones de la revisión (1)

El formulario lleva notas de revisión. Aplica lo que dicen y **quítalas** del escrito final.

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 79.2 a 4 de la LRJS
- artículo 79 de la LRJS
- artículo 728 de la LEC

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

### Formulario 0122 · Embargo preventivo de bienes tras la demanda: medida cautelar

- Año del modelo: 2022
- Revisión 17-11-2026: 3 citas normativas corregidas tras comprobarlas en el BOE; 11 campos de relleno marcados en blanco; 3 etiquetas sin dato marcadas en blanco; 1 notas de revisión repetidas retiradas; 4 huecos del original que se habían perdido sin marca, marcados (IMPORTE, Nº, Nº DE PROCEDIMIENTO)
- Avisos de la revisión: «Juzgado de lo Social» → Sección de lo Social del Tribunal de Instancia (LO 1/2025, DA 1.ª); el embargo preventivo cabe en cualquier momento antes de la sentencia (art. 79.4 LRJS).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Encabezamiento
Alegaciones
Suplico
Lugar y fecha
Otrosí
Suplico
Firmas
Sección de lo Social del Tribunal de Instancia de [SEDE] – Plaza n.º [Nº] [COMPLETAR]

[NOTA DE REVISIÓN: Desde el 31-12-2025 los Juzgados de lo Social son la Sección de lo Social del Tribunal de Instancia; el Tribunal no se numera, se numera la plaza. En la demanda inicial (antes del reparto) se omite la plaza. Fuente: arts. 84.2.i) y 94 LOPJ (red. LO 1/2025); LO 1/2025 DA 1.ª y DT 1.ª (la plaza conserva la numeración del Juzgado; Juzgados de lo Social transformados el 31-12-2025); LOPJ (LO 6/1985), BOE-A-1985-12666; LO 1/2025, BOE-A-2025-76.]

Autos núm. [Nº DE PROCEDIMIENTO]

Parte actora: [COMPLETAR]

Parte demandada: [COMPLETAR]

A LA SECCIÓN DE LO SOCIAL DEL TRIBUNAL DE INSTANCIA DE [SEDE] – PLAZA N.º [Nº]

Alegaciones

Primera.– Antecedentes. Demanda interpuesta

En fecha [FECHA], interpuse demanda de reclamación de derecho y cantidad contra la Empresa, estando señalados los actos de conciliación y juicio para el próximo [COMPLETAR].

El objeto de la demanda era la reclamación de diferencias salariales devengadas durante los seis meses previos a su interposición, por cuanto la Empresa me viene abonando desde dicha fecha una suma inferior a la que resulta de las hojas de salario. La cantidad reclamada en la demanda asciende a [IMPORTE] € brutos.

Segundo.– Acreditación de venta de bienes por la Empresa demandada

La actividad de la Empresa tal y como resulta de la demanda es la fabricación de [COMPLETAR], prestando mis servicios en el taller de la Empresa como [COMPLETAR].

Con posterioridad a la interposición de la demanda esta parte ha tenido conocimiento directo de que la Empresa está realizando actos de disposición y ventas de la maquinaria de producción, indispensable para la realización de la actividad, así como de otros bienes de la Empresa, como dos vehículos comerciales, varios ordenadores y mobiliario de oficina.

A los efectos de acreditar lo anterior se acompañan a este escrito como:

– Documento uno fotografías del taller antes de la venta de la maquinaria y después.

– Documento dos denuncia interpuesta ante la Inspección de Trabajo, relatando la venta de las máquinas y la consecuencia falta de ocupación.

– Documentos tres [COMPLETAR]

De lo anterior se deduce que la Empresa, está liquidando sus bienes, sin posibilidad de generar nuevos ingresos, por lo que resulta necesario se adopte medida cautelar del artículo 79.2 a 4 de la LRJS consistente en el embargo preventivo de los bienes que se relacionan a continuación [COMPLETAR], y cuyo valor se estima en la suma de [IMPORTE] € más un 10% calculado provisionalmente como costas de ejecución.

Tercero.– Concurrencia de requisitos legales

Concurren los requisitos necesarios para la adopción de la medida cautelar establecidos tanto en el artículo 79 de la LRJS citado como en el artículo 728 de la LEC, consistentes en apariencia de buen derecho o «fumus boni iurius» [728.2 de la LEC], y «periculum in mora» 728.1 de la LEC.

Respecto al primero de los requisitos o la apariencia de buen derecho, resultan de la demanda razones que permiten al Juzgador, sin prejuzgar sobre el fondo del asunto prever, un resultado favorable a mi representado por cuanto se está ejercitando una acción de reclamación de cantidad por diferencias salariales entre las propias nóminas realizadas por la Empresa, y los ingresos efectuados por transferencia bancaria, existiendo además riesgo en caso de demora en la resolución judicial, por cuanto al estar la Empresa vendiendo los activos necesarios para la actividad productiva que realiza, presumiblemente se está situando en una situación de insolvencia que le impedirá abonar el importe reclamado en el presente procedimiento.

Cuarto.– Concurrencia de razones de urgencia

En su virtud,

AL TRIBUNAL SUPLICO: que, teniendo por presentado este escrito, con sus copias y documentos que lo acompañan, se sirva admitirlo y, en mérito de su contenido, ACUERDE LA ADOPCIÓN DE LA MEDIDA CAUTELAR INTERESADA, consistente en el embargo de los bienes relacionados en el cuerpo del presente escrito.

Es Justicia que pido en [LUGAR], a [FECHA].

PRIMER OTROSÍ DIGO: Que para el supuesto de que se acuerde la celebración de vista con audiencia de la Empresa para la adopción de la medida cautelar, se proceda a:

a. Requerir al administrador/a Don/Dña [COMPLETAR], para que comparezca personalmente a la vista.

b. Se cite como testigos a Don [COMPLETAR] y Doña [COMPLETAR], trabajadores de la Empresa con conocimiento directo de las ventas realizadas en las últimas semanas, que pueden ser citados en el domicilio de ésta.

SUPLICO: Que tenga por hechas las anteriores manifestaciones a los efectos legales oportunos, y en su caso acuerde la práctica de las diligencias de citación de solicitadas para el acto de la vista.

Es Justicia que reitero en lugar y fecha arriba mencionados.

Fdo.: [COMPLETAR]

Ldo/a. Clgdo/a. núm. [Nº].

════════════════════════════════════════════════════════════════════════
