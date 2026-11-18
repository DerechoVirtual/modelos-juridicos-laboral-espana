---
name: reduccion-jornada-suspension-contratos-sin-421
description: "Redacta el escrito «Reducción de jornada o suspensión de contratos sin representantes: aviso a todos los trabajadores» (formulario 421 de despido colectivo y erte, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Reducción de jornada o suspensión de contratos sin representantes: aviso a todos los trabajadores

> Formulario 0421 del plugin **Despido colectivo y ERTE** · revisado el 17-11-2026.

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
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] NOMBRE Y APELLIDOS
- [ ] DNI/NIE
- [ ] NIF
- [ ] LOCALIDAD
- [ ] Nº (3 veces)
- [ ] FECHA
- [ ] Otros 66 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…en nombre y representación de la empresa»; «… inexistencia de representación legal en»; «…e afectando a la misma. Dado que en esta»; «…da por las personas trabajadoras de esta»; «…ntativos y representativos del sector de»; «…ón negociadora del convenio colectivo de»; «…rocedimiento de mediación o arbitraje de»; «…s contratos de trabajo se basa en causas»; «…e centros de trabajo de la empresa es de»; «…de los que»; «…e los que [COMPLETAR] están radicados en»; «…que se ubican las siguientes: Dirección:»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 17 del RD 1483/2012
- artículo 47 del ET

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

### Formulario 0421 · Reducción de jornada o suspensión de contratos sin representantes: aviso a todos los trabajadores

- Año del modelo: 2014
- Revisión 17-11-2026: 27 campos de relleno marcados en blanco; 48 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

COMUNICACIÓN A TODAS LAS PERSONAS TRABAJADORAS DE LA EMPRESA

En [LUGAR], a [DÍA] de [MES] de [AÑO].

Don/Doña [NOMBRE Y APELLIDOS], titular del DNI [DNI/NIE], actuando en nombre y representación de la empresa [COMPLETAR], con CIF [NIF], sita en [LOCALIDAD], mediante la presente carta, ante la inexistencia de representación legal en [COMPLETAR], comunico a todas las personas trabajadoras la firme decisión de la Dirección de la Empresa de iniciar el procedimiento para proceder a la reducción temporal de jornada/suspensión de contratos a causa de la grave situación que viene afectando a la misma.

Dado que en esta [COMPLETAR] no existe representación legal, se informa a todas las personas trabajadoras de la misma que podrán optar por atribuir su representación para la negociación del acuerdo, a su elección, a una comisión de un máximo de tres miembros integrada por las personas trabajadoras de esta [COMPLETAR] y elegida por todas las personas trabajadoras democráticamente o a una comisión de igual número de componentes designados, según su representatividad, por los sindicatos más representativos y representativos del sector de [COMPLETAR], al que pertenece la empresa, que estén legitimados para formar parte de la comisión negociadora del convenio colectivo de [COMPLETAR], convenio de aplicación a la misma.

Para la designación de la comisión a la que las personas trabajadoras vayan a atribuir su representación para el periodo de consultas, éstos tendrán un plazo máximo de [Nº] días, a contar desde el día [FECHA], sin que la falta de designación pueda suponer la paralización del procedimiento.

Asimismo se informa a las personas trabajadoras que en cualquier momento, previo acuerdo entre empresa y la comisión designada para su representación, se podrá sustituir el período de consultas por el procedimiento de mediación o arbitraje de [COMPLETAR], que deberá desarrollarse dentro del plazo máximo señalado para dicho período.

Sin perjuicio del contenido que a efectos de lo prevenido en el artículo 17 del RD 1483/2012, de 29 octubre se aportará en la comunicación sobre el inicio del período de consultas, se les informa que

INFORMES

La solicitud de suspensión de los contratos de trabajo se basa en causas [COMPLETAR], ya que:

El número de centros de trabajo de la empresa es de [COMPLETAR] de los que [COMPLETAR] están radicados en [COMPLETAR] siendo la relación de centros afectados y provincias en las que se ubican las siguientes:

Dirección: [COMPLETAR]

Localidad: [COMPLETAR]

Provincia: [COMPLETAR]

Comunidad Autónoma: [COMPLETAR]

Dirección: [COMPLETAR]

Localidad: [COMPLETAR]

Provincia: [COMPLETAR]

Comunidad Autónoma: [COMPLETAR]

El número de afectadas por [COMPLETAR] es de [COMPLETAR] y pertenecen al grupo profesional que se indica a continuación, desglosado por centros de trabajo:

Dirección: [COMPLETAR]

Provincia: [COMPLETAR]

CC.AA.: [COMPLETAR]

Nombre y apellidos: [COMPLETAR]

Grupo profesional: [COMPLETAR]

Fecha de ingreso: [COMPLETAR]

Dirección: [COMPLETAR]

Provincia: [COMPLETAR]

CC.AA.: [COMPLETAR]

Nombre y apellidos: [COMPLETAR]

Grupo profesional: [COMPLETAR]

Fecha de ingreso: [COMPLETAR]

El número de personas trabajadoras en la empresa el último año ha sido de [COMPLETAR] y han ostentado [COMPLETAR], desglosado por centros de trabajo:

Dirección: [COMPLETAR]

Provincia: [COMPLETAR]

CC.AA.: [COMPLETAR]

Nombre y apellidos: [COMPLETAR]

Grupo profesional: [COMPLETAR]

Fecha de ingreso: [COMPLETAR]

Dirección: [COMPLETAR]

Provincia: [COMPLETAR]

CC.AA.: [COMPLETAR]

Nombre y apellidos: [COMPLETAR]

Grupo profesional: [COMPLETAR]

Fecha de ingreso: [COMPLETAR]

La duración prevista para la suspensión de los contratos de trabajo es de [COMPLETAR], y se llevará a cabo durante el período de [Nº] meses.

El calendario con los días concretos de suspensión para cada una de las personas trabajadoras es el que se determina a continuación:

Persona trabajadora: [COMPLETAR]

Mes: [COMPLETAR]

Días: [COMPLETAR]

Persona trabajadora: [COMPLETAR]

Mes: [COMPLETAR]

Días: [COMPLETAR]

La duración prevista para la reducción de la jornada de trabajo es de [COMPLETAR], y se llevará a cabo durante el período de [Nº] meses.

El porcentaje de reducción de jornada previsto así como el horario afectado para cada una de las personas trabajadoras es el que se indica a continuación:

Persona trabajadora: [COMPLETAR]

Porcentaje reducción: [COMPLETAR]

Horario afectado: [COMPLETAR]

Días: [COMPLETAR]

Mes: [COMPLETAR]

Persona trabajadora: [COMPLETAR]

Porcentaje reducción: [COMPLETAR]

Horario afectado: [COMPLETAR]

Días: [COMPLETAR]

Mes: [COMPLETAR]

Una vez que las personas trabajadoras del centro/s de trabajo afectado/s hayan designado la comisión a la que se hace referencia en el encabezamiento de este escrito, deberán poner en conocimiento de esta Dirección los datos personales de las componentes de la misma. Al recibo de dicha comunicación o, en su defecto, transcurrido el plazo anteriormente señalado, procederemos a iniciar por escrito el procedimiento mediante la comunicación de la apertura del período de consultas conforme a los trámites previstos en el artículo 47 del ET y 17 y siguientes del RD 1483/2012.

Sin otro particular, le saluda atentamente.

Recibí el original

 Representante legal de la empresa [COMPLETAR]

Fdo: Fdo:
