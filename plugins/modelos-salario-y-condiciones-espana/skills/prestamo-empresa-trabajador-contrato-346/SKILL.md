---
name: prestamo-empresa-trabajador-contrato-346
description: "Redacta el escrito «Préstamo de la empresa al trabajador: contrato» (formulario 346 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Préstamo de la empresa al trabajador: contrato

> Formulario 0346 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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

- [ ] LUGAR
- [ ] FECHA (2 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] DNI/NIE (2 veces)
- [ ] LOCALIDAD (2 veces)
- [ ] IMPORTE (2 veces)
- [ ] NÚMERO (2 veces)
- [ ] Nº
- [ ] Otros 4 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…de la empresa»; «…del convenio colectivo aplicable, de»; «…- El préstamo tiene como causa»; «…jadora a la empresa en el plazo total de»

## Elecciones que hay que hacer

- representante legal / gerente / administrador único
- trimestral / mensual

## Párrafos opcionales (3)

Inclúyelos solo si encajan en los hechos:

- - El trabajador/la trabajadora tiene la antigüedad mínima de [Nº] años en la empresa.…
- - El préstamo tiene como causa [COMPLETAR].…
- - El préstamo no supera el límite del % del salario bruto del trabajador/de la trabajadora.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- art. 42.1 Ley 35/2006

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

### Formulario 0346 · Préstamo de la empresa al trabajador: contrato

- Año del modelo: 2017
- Revisión 17-11-2026: 2 desplegables y casillas convertidos en elección en blanco; 3 párrafos opcionales señalados; 19 campos de relleno marcados en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

REUNIDOS
ESTIPULACIONES
Firmas

Modelo de contrato de préstamo de la empresa al trabajador, en el que debemos tener en cuenta que estos préstamos se constituyen como créditos comunes y, por tanto, con libertad de pactos por las partes, si bien se permite que se pacten en condiciones más favorables para los empleados que las de las entidades financieras y tienen una especial consideración fiscal:

- Es retribución en especie y, en consecuencia, el trabajador debe tributarlo como rendimiento del trabajo (art. 42.1 Ley 35/2006; Consulta Vinculante DGT V2548-11).

- La empresa debe ingresar en Hacienda una cantidad en concepto de “ingreso a cuenta”, que pagará ella o el trabajador, y que es el resultado de aplicar al valor de la retribución en especie el porcentaje de retención del IRPF que corresponda al trabajador de la siguiente fórmula (Consulta Vinculante DGT V0552-13):

(Interés legal del dinero – Interés pactado) x Porcentaje de retención del trabajador

Y debe comunicarlo en los modelos 111 (trimestral/mensual – Casillas 04, 05 y 06) y en el modelo 190 (resumen anual – Clave A – Subclave 01).

Se puede pactar su fecha de devolución, si es con o sin intereses (aunque es recomendable pactarlos a un tipo de interés inferior al que se ofrece en el mercado, ya que así tributan por la diferencia entre el interés pagado y dicho interés legal, en vez de por el interés legal del dinero), las cuotas resultantes, los límites en el plazo de devolución y el importe a prestar.

Los convenios colectivos suelen establecer condiciones para estos préstamos, a veces limitadoras (antigüedad mínima del trabajador, causas concretas para su otorgamiento, limitación en la cuantía del préstamo y del salario para poder percibirlo).

En [LUGAR], a [FECHA].

REUNIDOS

DE UNA PARTE,

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto de DNI número [DNI/NIE], [ELEGIR: representante legal / gerente / administrador único] de la empresa [COMPLETAR], en cuya representación actúa en el presente acto conforme a las facultades que al efecto tiene otorgadas, con domicilio social en [LOCALIDAD].

Y, DE OTRA PARTE,

D./Dña. [NOMBRE Y APELLIDOS], mayor de edad, provisto/a de DNI número [DNI/NIE], actuando en su propio nombre y derecho, con domicilio en [LOCALIDAD].

Se reconocen ambos la capacidad suficiente para otorgar el presente CONTRATO DE PRÉSTAMO DE LA EMPRESA AL TRABAJADOR por su condición de tal, conforme a las siguientes

ESTIPULACIONES

Primera

La empresa entregará a la persona trabajadora, que acepta en este acto, la cantidad de [IMPORTE] euros en concepto de préstamo por su condición de tal, que hará efectiva mediante transferencia bancaria que realizará en fecha de hoy en la cuenta bancaria donde la empresa realiza los ingresos mensuales de su nómina.

Segunda

El préstamo que se otorga cumple los requisitos establecidos en la cláusula número [NÚMERO] del convenio colectivo aplicable, de [COMPLETAR], para poder otorgarse, es decir:

[OPCIONAL — incluir si procede]

- El trabajador/la trabajadora tiene la antigüedad mínima de [Nº] años en la empresa.

[OPCIONAL — incluir si procede]

- El préstamo tiene como causa [COMPLETAR].

[OPCIONAL — incluir si procede]

- El préstamo no supera el límite del % del salario bruto del trabajador/de la trabajadora.

Tercera

La cantidad prestada deberá ser devuelta y reintegrada por el trabajador/la trabajadora a la empresa en el plazo total de [COMPLETAR], mediante ingresos o transferencias mensuales que al efecto realizará antes del día [FECHA] de cada mes en la cuenta bancaria nº [NÚMERO] de la empresa.

Cuarta

Se pacta un interés sobre el importe del préstamo del % anual, inferior al interés legal actual vigente del %, que se liquidará mensualmente junto con la amortización del capital indicada en la estipulación anterior y el trabajador ingresará o transferirá en la misma cuenta bancaria.

Quinta

El prestatario/La prestataria podrá reintegrar el capital prestado antes de su vencimiento sin coste alguno.

Sexta

El salario del trabajador/la trabajadora garantiza el préstamo, de forma que el retraso o impago de alguna de las cuotas mensuales autoriza a la empresa a cargar su importe en el salario del mes siguiente, descontándolo de tal retribución.

Séptima

Como el préstamo pactado es a interés inferior al de mercado, tiene la consideración de retribución en especie, por lo que constará como rendimiento del trabajo del trabajador/la trabajadora a todos los efectos.

Octava

La empresa realizará el obligado ingreso a cuenta en Hacienda Pública de la cantidad de [IMPORTE] euros, resultante de aplicar el porcentaje de % a la cantidad resultante de aplicar el porcentaje de diferencia entre el interés legal y el aquí pactado sobre la cuantía total el préstamo, y lo comunicará en la liquidación [ELEGIR: trimestral / mensual] de retenciones e ingresos a cuenta y en la anual correspondiente a que está obligada.

La citada cantidad correrá a cargo del trabajador/la trabajadora.

Y en prueba de conformidad firman el presente documento por duplicado ejemplar y a un solo efecto en el lugar y fecha expresados en el encabezamiento.

Por la empresa

Trabajador/a

D./Dña. [NOMBRE Y APELLIDOS] 	D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
