---
name: puesta-disposicion-contrato-385
description: "Redacta el escrito «Puesta a disposición: contrato» (formulario 385 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Puesta a disposición: contrato

> Formulario 0385 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- Los contratos de puesta a disposición solo caben en los supuestos del art. 15 ET (circunstancias de la producción o sustitución) y de contrato formativo; el art. 6.2 de la Ley 14/1994 consolidado aún habla de «prácticas» y «formación y aprendizaje», hoy contratos formativos del art. 11 ET.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] NOMBRE Y APELLIDOS (2 veces)
- [ ] DNI/NIE (2 veces)
- [ ] NIF (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] Otros 17 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…BOLETÍN OFICIAL DEL ESTADO Núm. 284»; «…Lunes 25 de noviembre de 2024»; «…DNI [DNI/NIE] En concepto de»; «…Nombre o razón social»; «…NIF [NIF] CCC Domicilio»; «…DNI [DNI/NIE] En concepto de»; «…Nombre o razón social»; «…NIF [NIF] CCC Domicilio»; «…Localidad»; «…a Domicilio del centro de trabajo»; «…Localidad»; «…datos de la persona tutora designada por»; …

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 6.2 de la Ley 14/1994
- artículo 2 del Real Decreto 216/1999

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

### Formulario 0385 · Puesta a disposición: contrato

- Año del modelo: 2015
- Revisión 17-11-2026: 16 llamadas a nota sin texto retiradas; 22 campos de relleno marcados en blanco; 4 huecos del original que se habían perdido sin marca, marcados (COMPLETAR, DÍA, LUGAR, MES)
- Avisos de la revisión: Los contratos de puesta a disposición solo caben en los supuestos del art. 15 ET (circunstancias de la producción o sustitución) y de contrato formativo; el art. 6.2 de la Ley 14/1994 consolidado aún habla de «prácticas» y «formación y aprendizaje», hoy contratos formativos del art. 11 ET.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

BOLETÍN OFICIAL DEL ESTADO
Núm. 284 [COMPLETAR] Lunes 25 de noviembre de 2024 [COMPLETAR] Sec. I. Pág. 158212

                                                                                        ANEXO II

                                                          Contrato de puesta a disposición (CPD)

                                                                    EMPRESA DE TRABAJO TEMPORAL
           Don/Doña [NOMBRE Y APELLIDOS] DNI [DNI/NIE] En concepto de [COMPLETAR]
           Nombre o razón social [COMPLETAR] NIF [NIF] CCC
           Domicilio [COMPLETAR] Localidad
           Número de autorización
                   Director/a, gerente, etc.

                                                                                EMPRESA USUARIA
           Don/Doña [NOMBRE Y APELLIDOS] DNI [DNI/NIE] En concepto de [COMPLETAR]
           Nombre o razón social [COMPLETAR] NIF [NIF] CCC
           Domicilio [COMPLETAR] Localidad [COMPLETAR] Provincia
           Domicilio del centro de trabajo [COMPLETAR] Localidad [COMPLETAR] Provincia
                   Director/a, gerente, etc.

                                                                     SUPUESTO DE CELEBRACIÓN

                  Deberá indicarse el supuesto de celebración del CPD con expresión concreta de la causa que lo justifica, según lo previsto en el
           artículo 6.2 de la Ley 14/1994, de 1 de junio.
                  En los supuestos de contrato formativo de formación en alternancia deben consignarse los datos de la persona tutora designada por [COMPLETAR]
           la empresa usuaria y ha de adjuntarse el plan formativo individual, según lo previsto en el acuerdo de cooperación concertado con el
           centro o entidad formativa.

                                                           CARACTERÍSTICAS DEL PUESTO DE TRABAJO
           Cualificación requerida
           Funciones
           Información sobre riesgos laborales del puesto de trabajo y medidas preventivas
           Lugar y horario de trabajo [COMPLETAR] Servicios comunes e instalaciones colectivas
           Retribución total
           Código del convenio colectivo aplicable
                  En el caso de contratos formativos se justificará: para los de formación en alternancia que la actividad desempeñada por la persona
           trabajadora en la empresa usuaria está directamente relacionada con las actividades formativas que justifican la contratación laboral; y
           para los de obtención de práctica profesional que el puesto de trabajo en la empresa usuaria permite la obtención de la práctica profesional
           adecuada al nivel de estudios o de formación objeto del contrato.
                  Informaciones previstas en el artículo 2 del Real Decreto 216/1999, de 5 de febrero, sobre disposiciones mínimas de seguridad y
           salud en el trabajo en el ámbito de las empresas de trabajo temporal.
                  Cuando la persona trabajadora preste servicios a bordo de una embarcación, deberá reflejarse el identificador de esta.

                                                                         DURACIÓN DEL CONTRATO
           Desde [COMPLETAR] Hasta
                   Deberá indicarse la duración prevista del contrato de puesta a disposición.

                                                                                PRECIO CONVENIDO

             Cláusulas adicionales:
                                                                                                                                                                  Verificable en https://www.boe.es

              (Será nula la cláusula del contrato que prohíba la contratación de la persona trabajadora por la empresa usuaria a la
           finalización del contrato de puesta a disposición).
                                                                                                                                                                  cve: BOE-A-2024-24517

             En [LUGAR], a [DÍA] de [MES] de 20 [COMPLETAR]

                             Por la empresa de trabajo temporal [COMPLETAR] Por la empresa usuaria

                                           (firma y sello) [COMPLETAR] (firma y sello)

════════════════════════════════════════════════════════════════════════
