---
name: sucesion-contrata-aviso-empresa-representacion-356
description: "Redacta el escrito «Sucesión en la contrata: aviso de la empresa a la representación de los trabajadores» (formulario 356 de condiciones de trabajo y salario, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Sucesión en la contrata: aviso de la empresa a la representación de los trabajadores

> Formulario 0356 del plugin **Condiciones de trabajo y salario** · revisado el 17-11-2026.

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
- [ ] FECHA (3 veces)
- [ ] Otros 15 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…egados de Personal Muy señores nuestros:»; «…Estatuto de los Trabajadores, y artículo»; «…del convenio colectivo»; «…tularidad en la contrata del servicio de»; «…siguientes: Razón social o denominación:»; «…NIF:»; «…a la Seguridad Social: Domicilio social:»; «…cesión, que se incorporan con efectos de»; «…los siguientes: a) Persona trabajadora 1»; «…b) Persona trabajadora 2»; «…c) Persona trabajadora 3»; «…efecto en el convenio colectivo. 5.º Que»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 44 del Estatuto de los Trabajadores

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

### Formulario 0356 · Sucesión en la contrata: aviso de la empresa a la representación de los trabajadores

- Año del modelo: 2013
- Revisión 17-11-2026: 14 campos de relleno marcados en blanco; 4 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Lugar, fecha y encabezamiento
Comunicación
Firmas
En [LUGAR], a [FECHA].

Al Comité de Empresa/Delegados de Personal

Muy señores nuestros: [COMPLETAR]

Mediante el presente escrito y al amparo de lo prescrito en el artículo 44 del Estatuto de los Trabajadores, y artículo [COMPLETAR] del convenio colectivo [COMPLETAR], procedemos a comunicarles los siguientes hechos:

1.º Que con fecha [FECHA] se producirá el cambio de titularidad en la contrata del servicio de [COMPLETAR], por haberse adjudicado el mismo a una nueva empresa adjudicataria.

2.º Que los datos identificativos de la nueva empresa adjudicataria de la contrata son los siguientes:

Razón social o denominación: [COMPLETAR]

NIF: [COMPLETAR]

Código de cuenta de cotización a la Seguridad Social:

Domicilio social: [COMPLETAR]

3.º Que los trabajadores adscritos a los servicios de la contrata objeto de nueva concesión, que se incorporan con efectos de [COMPLETAR] a la nueva empresa adjudicataria, subrogándose ésta en las relaciones laborales y de Seguridad Social de los mismos, son los siguientes:

a) Persona trabajadora 1 [COMPLETAR]

b) Persona trabajadora 2 [COMPLETAR]

c) Persona trabajadora 3 [COMPLETAR]

4.º Que se ha procedido a comunicar por esta empresa saliente, con fecha [FECHA], a la nueva empresa adjudicataria la relación de trabajadores adscritos a la contrata, con mención expresa de sus condiciones laborales, que han de ser respetadas por sucesión empresarial. Con esa comunicación se remitió copia de la documentación laboral y de Seguridad Social establecida al efecto en el convenio colectivo.

5.º Que [COMPLETAR] mantiene su autonomía la contrata, por lo que [COMPLETAR] se extingue el mandato representativo de los representantes legales de los trabajadores.

6.º Que, salvo pacto en contra con la nueva empresa cesionaria, las relaciones laborales de las personas trabajadoras afectadas se seguirá rigiendo por el convenio colectivo [COMPLETAR] actualmente vigente, hasta la expiración de su vigencia o hasta que entre en vigor un nuevo convenio colectivo en la entidad económica transmitida.

Con el ruego de que acusen de esta comunicación, les saluda atentamente

Recibí el [COMPLETAR].

Representante de los trabajadores	La empresa
Fdo.: 	Fdo.:

════════════════════════════════════════════════════════════════════════
