---
name: prorroga-contrato-trabajo-acogida-real-decreto-36
description: "Redacta el escrito «Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en gallego)» (formulario 36 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en gallego)

> Formulario 0036 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] C.P. (3 veces)
- [ ] Nº (2 veces)
- [ ] NÚMERO
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] ÓRGANO
- [ ] Otros 33 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…IÓN DE PRÓRROGA DO CONTRATO DE TRABALLO:»; «…TO DA PRÓRROGA ACOLLIDO AO REAL DECRETO:»; «…DATOS DA EMPRESA CIF/NIF/NIE:»; «…D./DNA. NIF/NIE:»; «…ONCEPTO NOME OU RAZÓN SOCIAL DA EMPRESA:»; «…DOMICILIO SOCIAL:»; «…DOMICILIO SOCIAL: [COMPLETAR] CONCELLO:»; «…CÓDIGO POSTAL [C.P.] PAÍS:»; «…DATOS DA CONTA DE COTIZACIÓN RÉXIME»; «…CÓDIGO CONTA DE COTIZACIÓN:»; «…ACTIVIDADE ECONÓMICA:»; «…DATOS DO CENTRO DE TRABALLO CONCELLO:»; …

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

### Formulario 0036 · Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en gallego)

- Año del modelo: 2024
- Revisión 17-11-2026: 18 casillas del modelo oficial marcadas en blanco; 6 llamadas a nota sin texto retiradas; 22 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

COMUNICACIÓN DE PRÓRROGA DO CONTRATO DE TRABALLO: [COMPLETAR]

DATOS DO CONTRATO
MODELO DE CONTRATO OBXECTO DA PRÓRROGA

ACOLLIDO AO REAL DECRETO: [COMPLETAR]

DATOS DA EMPRESA
CIF/NIF/NIE: [COMPLETAR]

D./DNA. NIF/NIE: [COMPLETAR]

EN CONCEPTO

NOME OU RAZÓN SOCIAL DA EMPRESA: [COMPLETAR]

DOMICILIO SOCIAL: [COMPLETAR]

CONCELLO: [COMPLETAR]

CÓDIGO POSTAL [C.P.] PAÍS: [COMPLETAR]

DATOS DA CONTA DE COTIZACIÓN
RÉXIME [COMPLETAR] CÓDIGO CONTA DE COTIZACIÓN: [COMPLETAR]

ACTIVIDADE ECONÓMICA: [COMPLETAR]

DATOS DO CENTRO DE TRABALLO
CONCELLO: [COMPLETAR]

CÓDIGO POSTAL [C.P.] PAÍS: [COMPLETAR]

DATOS DA PERSOA TRABALLADORA
D./DNA. NIF/NIE: [COMPLETAR]

DATA NACEMENTO (dd/mm/aaaa) [COMPLETAR] Nº SEGURIDADE SOCIAL [COMPLETAR] NACIONALIDADE: [COMPLETAR]

NIVEL FORMATIVO: [COMPLETAR]

CONCELLO DO DOMICILIO: [COMPLETAR]

CÓDIGO POSTAL [C.P.] PAÍS DOMICILIO: [COMPLETAR]

DATOS DA ASISTENCIA LEGAL (NO SEU CASO)
D./DNA. NIF/NIE: [COMPLETAR]

EN CALIDADE DE [COMPLETAR]

   Director/a, Xerente, etc.
   Pai, nai, titor/a ou persoa ou institución que lle teña ao seu cargo.

                                                                      COMUNICAN

Ao Servizo Público de Emprego de [COMPLETAR]

que acordaron unha [COMPLETAR] prórroga de [Nº] meses de duración,
desde o [COMPLETAR] ata o [COMPLETAR] do contrato que con data [COMPLETAR] e unha duración
inicial de [Nº] meses, foi celebrado polas partes anteriormente mencionadas e rexistrado no Servizo Público de Emprego de [COMPLETAR]

en data [COMPLETAR] co número [NÚMERO] sendo o tempo acumulado do contrato inicial máis la(s) prórroga(s) de [COMPLETAR]

 En [LUGAR], a [DÍA] de [MES] de [AÑO].

                     O/o traballador/a [COMPLETAR] O/a representante [ÓRGANO] O/a representante legal
                                                                         da empresa [COMPLETAR] do/a menor, se procede

PROTECCIÓN DE DATOS. - Os datos consignados no presente modelo terán a protección derivada do Regulamento (UE) 2016/679 do Parlamento
Europeo, do 27 de abril de 2016 e da Lei Orgánica 3/2018, do 5 de decembro.

   Primeira, segunda, terceira, etc.

                                            IMPORTANTE: [COMPLETAR]

  O formulario orixinal xérase protexido para evitar modificacións durante o seu enchemento. Unha vez
   finalizada esta, debe xerarse un novo documento, destinado exclusivamente á sinatura electrónica,
           mediante a impresión a PDF/PDF utilizando a impresora “Microsoft Print to PDF/PDF”.

                   Este novo documento non incorporará restricións de seguridade
                 e poderá ser asinado electronicamente polas persoas intervenientes,
            sendo a propia sinatura electrónica a que garantirá a integridade do documento.

                                     Generar PDF para firma

                 No caso de que este documento non se asine por medios electrónicos,
todas as páxinas cumprimentadas deberán ir asinadas na marxe esquerda para maior seguridade xurídica.

════════════════════════════════════════════════════════════════════════
