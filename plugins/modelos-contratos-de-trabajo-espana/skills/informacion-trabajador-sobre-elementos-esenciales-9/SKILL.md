---
name: informacion-trabajador-sobre-elementos-esenciales-9
description: "Redacta el escrito «Información al trabajador sobre los elementos esenciales del contrato: carta» (formulario 9 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información al trabajador sobre los elementos esenciales del contrato: carta

> Formulario 0009 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- La opción A no recoge todos los extremos del art. 3.2 RD 723/2026 (periodo de prueba, formación, ETT, horas extraordinarias y cambios de jornada o turno, medidas LGTBI, mejoras voluntarias y planes de pensiones, supuestos de modificación); la remisión genérica al ET y al convenio para la extinción solo vale si es precisa (art. 3.3).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] ÓRGANO
- [ ] Nº
- [ ] Otros 17 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…tud de información escrita presentada el»; «…n laboral y duración:. Tipo de contrato:»; «…de trabajo: Centro de trabajo ubicado en»; «….»; «… funciones: Grupo profesional/Categoría:»; «…. Descripción resumida de funciones:»; «…io base: €/mes. Complementos salariales:»; «…Periodicidad de pago: mediante [ÓRGANO].»; «…horas semanales. Distribución horaria:»; «…lectivo aplicable: Convenio Colectivo de»; «…, Código»; «…, Código [COMPLETAR], publicado en el»; …

## Elecciones que hay que hacer

- naturales / laborables

## Párrafos opcionales (19)

Inclúyelos solo si encajan en los hechos:

- Fecha de inicio de la relación laboral y duración:. Tipo de contrato: [COMPLETAR].…
- Lugar de trabajo: Centro de trabajo ubicado en [COMPLETAR]. [COMPLETAR].…
- Puesto de trabajo y funciones: Grupo profesional/Categoría: [COMPLETAR]. Descripción resumida de funciones: [C…
- Retribución: Salario base: €/mes. Complementos salariales: [COMPLETAR]. Periodicidad de pago: mediante [ÓRGANO…
- Jornada y tiempo de trabajo: Jornada ordinaria de [Nº] horas semanales. Distribución horaria: [COMPLETAR]. Vac…
- Convenio colectivo aplicable: Convenio Colectivo de [COMPLETAR], Código [COMPLETAR], publicado en el [COMPLETA…
- Protección social y Mutua: Entidad colaboradora de la Seguridad Social: [COMPLETAR]. [COMPLETAR].…
- Información sobre decisiones algorítmicas o automatizadas:.…
- Planes y protocolos de la empresa:.…
- Extinción del contrato: El procedimiento de extinción y los plazos de preaviso se regirán por lo establecido e…
- País o países de destino:.…
- Duración prevista del trabajo en el extranjero:.…
- Moneda de pago del salario:.…
- Retribuciones en dinero o en especie y compensaciones adicionales:…
- Condiciones de repatriación:.…
- En caso de desplazamientos a la Unión Europea (UE) o Espacio Económico Europeo (EEE) en el marco de una presta…
- Retribución en el país de acogida:.…
- Reembolso de gastos de viaje, alojamiento y manutención:.…
- Portal web oficial único: [COMPLETAR]…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 8.5 del ET
- art. 8 ET
- Real Decreto 723/2026

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

### Formulario 0009 · Información al trabajador sobre los elementos esenciales del contrato: carta

- Año del modelo: 2026
- Revisión 17-11-2026: 1 citas normativas corregidas tras comprobarlas en el BOE; 1 desplegables y casillas convertidos en elección en blanco; 19 párrafos opcionales señalados; 20 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco; 1 huecos del original que se habían perdido sin marca, marcados (NOMBRE Y APELLIDOS)
- Avisos de la revisión: La opción A no recoge todos los extremos del art. 3.2 RD 723/2026 (periodo de prueba, formación, ETT, horas extraordinarias y cambios de jornada o turno, medidas LGTBI, mejoras voluntarias y planes de pensiones, supuestos de modificación); la remisión genérica al ET y al convenio para la extinción solo vale si es precisa (art. 3.3).

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

OPCIÓN A: INFORMACIÓN GENERAL
OPCIÓN B: INFORMACIÓN ADICIONAL POR PRESTACIÓN DE SERVICIOS EN EL EXTRANJERO
Firmas

En virtud de lo establecido en el Real Decreto 723/2026, de 9 de septiembre, por el que se transpone la Directiva (UE) 2019/1152 del Parlamento Europeo y del Consejo, de 20 de junio de 2019, relativa a unas condiciones laborales transparentes y previsibles en la Unión Europea, que desarrolla el art. 8.5 del ET, la empresa tiene obligación de informar por escrito a las personas trabajadoras sobre los elementos esenciales del contrato y las principales condiciones de ejecución de la prestación laboral. La obligación se entiende cumplida si dicha información ya figura en el contrato de trabajo formalizado por escrito. Si el contrato escrito solo contiene la información parcialmente, la empresa debe facilitar por escrito el resto, en los plazos y términos del propio real decreto.

Esta obligación no exime del cumplimiento de las obligaciones de formalización escrita del contrato ni de los derechos de información de la representación legal previstos en el art. 8 ET; y a la inversa, cumplir esas obligaciones del ET no exime de cumplir los deberes de información que establece esta norma.

Para las relaciones laborales vigentes el 5 de octubre de 2026, la empresa debe facilitar esta información a la persona trabajadora que lo solicite en el plazo de 30 días hábiles desde la solicitud.

ATT.

En [LUGAR], a [FECHA].

Estimado/a Sr./Sra. [NOMBRE Y APELLIDOS]

En virtud de lo establecido en el Real Decreto 723/2026, de 9 de septiembre

En respuesta a su solicitud de información escrita presentada el [COMPLETAR], y conforme a la Disposición Transitoria Única del Real Decreto 723/2026, de 9 de septiembre

[NOMBRE Y APELLIDOS], por medio del presente escrito le facilitamos la información relativa a las condiciones de su relación laboral:

OPCIÓN A: INFORMACIÓN GENERAL

[OPCIONAL — incluir si procede]

Fecha de inicio de la relación laboral y duración:. Tipo de contrato: [COMPLETAR].

[OPCIONAL — incluir si procede]

Lugar de trabajo: Centro de trabajo ubicado en [COMPLETAR]. [COMPLETAR].

[OPCIONAL — incluir si procede]

Puesto de trabajo y funciones: Grupo profesional/Categoría: [COMPLETAR]. Descripción resumida de funciones: [COMPLETAR].

[OPCIONAL — incluir si procede]

Retribución: Salario base: €/mes. Complementos salariales: [COMPLETAR]. Periodicidad de pago: mediante [ÓRGANO]. [COMPLETAR].

[OPCIONAL — incluir si procede]

Jornada y tiempo de trabajo: Jornada ordinaria de [Nº] horas semanales. Distribución horaria: [COMPLETAR]. Vacaciones: días [ELEGIR: naturales / laborables] al año.

[OPCIONAL — incluir si procede]

Convenio colectivo aplicable: Convenio Colectivo de [COMPLETAR], Código [COMPLETAR], publicado en el [COMPLETAR] de fecha [FECHA]. Estado: [COMPLETAR].

[OPCIONAL — incluir si procede]

Protección social y Mutua: Entidad colaboradora de la Seguridad Social: [COMPLETAR]. [COMPLETAR].

[OPCIONAL — incluir si procede]

Información sobre decisiones algorítmicas o automatizadas:.

[OPCIONAL — incluir si procede]

Planes y protocolos de la empresa:.

[OPCIONAL — incluir si procede]

Extinción del contrato: El procedimiento de extinción y los plazos de preaviso se regirán por lo establecido en el Estatuto de los Trabajadores y el Convenio Colectivo aplicable.

OPCIÓN B: INFORMACIÓN ADICIONAL POR PRESTACIÓN DE SERVICIOS EN EL EXTRANJERO

[OPCIONAL — incluir si procede]

País o países de destino:.

[OPCIONAL — incluir si procede]

Duración prevista del trabajo en el extranjero:.

[OPCIONAL — incluir si procede]

Moneda de pago del salario:.

[OPCIONAL — incluir si procede]

Retribuciones en dinero o en especie y compensaciones adicionales:

o Complementos o dietas por desplazamiento:.
o Compensación por gastos:.

[OPCIONAL — incluir si procede]

Condiciones de repatriación:.

[OPCIONAL — incluir si procede]

En caso de desplazamientos a la Unión Europea (UE) o Espacio Económico Europeo (EEE) en el marco de una prestación transnacional:

[OPCIONAL — incluir si procede]

Retribución en el país de acogida:.

[OPCIONAL — incluir si procede]

Reembolso de gastos de viaje, alojamiento y manutención:.

[OPCIONAL — incluir si procede]

Portal web oficial único: [COMPLETAR]

Atentamente,

Firma: [COMPLETAR]

════════════════════════════════════════════════════════════════════════
