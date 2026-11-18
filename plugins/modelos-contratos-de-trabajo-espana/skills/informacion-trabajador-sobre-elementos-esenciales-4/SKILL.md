---
name: informacion-trabajador-sobre-elementos-esenciales-4
description: "Redacta el escrito «Información al trabajador sobre los elementos esenciales del contrato (en gallego)» (formulario 4 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información al trabajador sobre los elementos esenciales del contrato (en gallego)

> Formulario 0004 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- Documento informativo del RD 723/2026 (BOE-A-2026-19200, en vigor el 5-10-2026, deroga el RD 1659/1998): comprobar que recoge todos los extremos del art. 3.2 a)-q), incluidos periodo de prueba, formación, ETT, sistemas algorítmicos, plan de igualdad y protocolo de acoso, medidas LGTBI, mejoras voluntarias y planes de pensiones y supuestos de modificación.

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] Otros 53 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…IS DE DURACIÓN SUPERIOR A CATRO SEMANAS:»; «… NOME E APELIDOS DA PERSOA TRABALLADORA:»; «…NIF/NIE DA PERSOA TRABALLADORA:»; «…NOME OU RAZÓN SOCIAL DA EMPRESA:»; «…CIF/NIF EMPRESA:»; «…DOMICILIO SOCIAL DA EMPRESA:»; «…BALLO HABITUAL ONDE SE PRESTA O SERVIZO:»; «…OA TRABALLADORA EN TRABALLO A DISTANCIA:»; «…CAR SE CONCO- RREN ESTAS CIRCUNSTANCIAS:»; «…LACIÓN LABORAL TIPO DE RELACIÓN LABORAL:»; «…dd/mm/aaaa) CONTIDO DA RELACIÓN LABORAL:»; «…EN RELACIÓNS LABORAIS TEMPORAIS:»; …

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

### Formulario 0004 · Información al trabajador sobre los elementos esenciales del contrato (en gallego)

- Año del modelo: 2026
- Revisión 17-11-2026: 41 casillas del modelo oficial marcadas en blanco; 11 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Documento informativo del RD 723/2026 (BOE-A-2026-19200, en vigor el 5-10-2026, deroga el RD 1659/1998): comprobar que recoge todos los extremos del art. 3.2 a)-q), incluidos periodo de prueba, formación, ETT, sistemas algorítmicos, plan de igualdad y protocolo de acoso, medidas LGTBI, mejoras voluntarias y planes de pensiones y supuestos de modificación.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MODELO DE DOCUMENTO INFORMATIVO SOBRE OS ELEMENTOS ESENCIAIS DO CONTRATO DE TRABALLO
APLICABLE ÁS RELACIÓNS LABORAIS DE DURACIÓN SUPERIOR A CATRO SEMANAS: [COMPLETAR]

1. INFORMACIÓN XERAL

A) IDENTIDADE DAS PARTES QUE SUBSCRIBEN O CONTRATO DE TRABALLO
NOME E APELIDOS DA PERSOA TRABALLADORA: [COMPLETAR]

NIF/NIE DA PERSOA TRABALLADORA: [COMPLETAR]

NOME OU RAZÓN SOCIAL DA EMPRESA: [COMPLETAR]

CIF/NIF EMPRESA: [COMPLETAR]

DOMICILIO SOCIAL DA EMPRESA: [COMPLETAR]

CENTRO DE TRABALLO HABITUAL ONDE SE PRESTA O SERVIZO: [COMPLETAR]

CENTRO DE TRABALLO AO QUE ESTÁ ADSCRITA A PERSOA TRABALLADORA EN TRABALLO A DISTANCIA: [COMPLETAR]

CENTROS ITINERANTES, DIFERENTES CENTROS DE TRABALLO OU DETERMINACIÓN LIBRE DO LUGAR DE PRESTACIÓN DO SERVIZO. INDICAR SE CONCO-
RREN ESTAS CIRCUNSTANCIAS: [COMPLETAR]

B) RELACIÓN LABORAL
TIPO DE RELACIÓN LABORAL: [COMPLETAR]

DATA INICIO RELACIÓN LABORAL (dd/mm/aaaa)

CONTIDO DA RELACIÓN LABORAL: [COMPLETAR]

EN RELACIÓNS LABORAIS TEMPORAIS: [COMPLETAR]
DURACIÓN PREVISTA DO CONTRATO [COMPLETAR] DATA FIN RELACIÓN LABORAL (dd/mm/aaaa): [COMPLETAR]

CAUSA HABILITANTE DA CONTRATACIÓN: [COMPLETAR]

CIRCUNSTANCIAS CONCRETAS QUE XUSTIFICAN A CONTRATACIÓN: [COMPLETAR]

CONEXIÓN COA DURACIÓN PREVISTA DO CONTRATO: [COMPLETAR]

C) POSTO DE TRABALLO
 CATEGORÍA OU GRUPO PROFESIONAL: [COMPLETAR]

 CARACTERIZACIÓN OU DESCRICIÓN RESUMIDA DO POSTO DE TRABALLO, EN TERMOS QUE PERMITAN COÑECER CON SUFICIENTE PRECISIÓN O CONTIDO
 ESPECÍFICO DO TRABALLO: [COMPLETAR]

D) SALARIO
 CONTÍA DO SALARIO BASE (*): [COMPLETAR]

 CONTÍA DOS COMPLEMENTOS SALARIAIS (*): [COMPLETAR]

 PERIODICIDADE (*): [COMPLETAR]

 MÉTODO PAGO (*): [COMPLETAR]

 MODO DE CÁLCULO DOS CONCEPTOS SALARIAIS VARIABLES: [COMPLETAR]

 CRITERIOS QUE DETERMINAN A PERCEPCIÓN DOS CONCEPTOS SALARIAIS VARIABLES: [COMPLETAR]

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

E) TEMPO DE TRABALLO
 DURACIÓN E DISTRIBUCIÓN HORARIA DA XORNADA ORDINARIA DE TRABALLO (*): [COMPLETAR]

 TRABALLO NOCTURNO OU A QUENDAS (*): [COMPLETAR]

 PROCEDEMENTO PARA A MODIFICACIÓN DAS QUENDAS E A DURACIÓN E DISTRIBUCIÓN DA XORNADA (*): [COMPLETAR]

 ACORDOS RELATIVOS A HORAS EXTRAS E A súa RETRIBUCIÓN (*): [COMPLETAR]

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

 DURACIÓN DAS VACACIÓNS E PROCEDEMENTOS PARA FIXAR O PERÍODO Ou PERÍODOS DO seu DESFRUTE (*): [COMPLETAR]

 SISTEMA PARA A DISTRIBUCIÓN IRREGULAR DE XORNADA: [COMPLETAR]

 PERÍODOS DE AVISO PREVIO PARA O INICIO E CANCELACIÓN DE TAREFAS: [COMPLETAR]

 PERÍODOS ESTIMADOS DE ACTIVIDADE E INACTIVIDADE EN CONTRATOS INDEFINIDOS FIXOS DESCONTINUOS: [COMPLETAR]

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

F) PERÍODO DE PROBA, CANDO SE CONCERTE
F) PERÍODO DE PROBA, CANDO SE CONCERTE

 INFORMACIÓN RELATIVA Ás OBRIGACIÓNS RESPECTIVAS DA EMPRESA E DA persoa TRABALLADORA A REALIZAR As EXPERIENCIAS QUE CONSTITÚAN O
 OBXECTO DA PROBA (*): [COMPLETAR]

G) FORMACIÓN
 FORMACIÓN A PROPORCIONAR POLA EMPRESA, NO CASO DE QUE SEXA OBRIGATORIA PARA O DESEMPEÑO DO POSTO DE TRABALLO (*): [COMPLETAR]

H) EMPRESAS DE TRABALLO TEMPORAL, NO CASO DE PERSOAS TRABALLADORAS CEDIDAS PO
EMPRESAS DE TRABALLO TEMPORAL
 IDENTIDADE DA EMPRESA USUARIA E A CAUSA QUE HABILITA Á CELEBRACIÓN DE CADA CONTRATO DE POSTA AO DISPOR: [COMPLETAR]

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

I) EXISTENCIA DE SISTEMAS ALGORÍTMICOS Ou AUTOMATIZADOS DE TOMA DE DECISIÓNS RELACIONADOS
COA FIXACIÓN, VARIACIÓN Ou MODIFICACIÓN DE CONDICIÓNS DE TRABALLO: [COMPLETAR]

J) IDENTIFICACIÓN, SE EXISTE, DO PLAN DE IGUALDADE APLICABLE Á EMPRESA, NO CASO DE QUE SE
DISPOÑA, POLÍTICA EMPRESARIAL DE CONCILIACIÓN E PROTOCOLO DE ACOSO SEXUAL E POR RAZÓN DE [COMPLETAR]
SEXO NA EMPRESA: [COMPLETAR]

K) MEDIDAS E RECURSOS PARA ALCANZAR A IGUALDADE REAL E EFECTIVA DAS PERSOAS LGTBI, NO CASO
DE QUE SE DISPOÑA DELES

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

L) PROCEDEMENTO DE EXTINCIÓN DO CONTRATO, INCLUÍDOS OS REQUISITOS FORMAIS E A DURACIÓN DOS
PRAZOS DE AVISO PREVIO (*): [COMPLETAR]

M) CONVENIO OU CONVENIOS COLECTIVOS APLICABLES Á RELACIÓN LABORAL

N) SISTEMA DE COLABORACIÓN NA XESTIÓN DA SEGURIDADE SOCIAL QUE OPERA NA EMPRESA (*)

O) SUPOSTOS E PROCEDEMENTO A SEGUIR PARA MODIFICAR O CONTIDO DA RELACIÓN LABORAL,
A CATEGORÍA OU GRUPO PROFESIONAL, O SALARIO E O TEMPO DE TRABALLO: [COMPLETAR]

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

 2. INFORMACIÓN ADICIONAL NOS SUPOSTOS DE PRESTACIÓN DE SERVIZOS NO ESTRANXEIRO.
 APLICABLE SÓ SE A DURACIÓN DE CADA PERÍODO DE TRABALLO NO ESTRANXEIRO PASA AS CATRO
 SEMANAS CONSECUTIVAS

 A) O PAÍS OU PAÍSES NOS QUE DEBE LEVARSE A CABO O TRABALLO

 B) A DURACIÓN DO TRABALLO QUE VAIA A PRESTARSE NO ESTRANXEIRO

 C) A MOEDA DE CURSO LEGAL NA QUE SE PAGARÁ O SALARIO (*)

 D) AS RETRIBUCIÓNS EN DIÑEIRO OU EN ESPECIE, ASÍ COMO AS COMPENSACIÓNS POR GASTOS, GASTOS DE VIAXE, DIETAS E AS VANTAXES VINCULADAS
 Á CIRCUNSTANCIA DA PRESTACIÓN DE SERVIZOS NO ESTRANXEIRO: [COMPLETAR]

 E) SE SE ATOPA PREVISTA A REPATRIACIÓN DA PERSOA TRABALLADORA E AS SÚAS CONDICIÓNS

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
      extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

 3. NO CASO DUNHA PERSOA TRABALLADORA DESPRAZADA AO TERRITORIO DE ESTADOS MEMBRO DA
 UNIÓN EUROPEA OU DE ESTADOS SIGNATARIOS DO ACORDO SOBRE O ESPAZO ECONÓMICO EUROPEO NO
 MARCO DUNHA PRESTACIÓN DE SERVIZOS TRANSNACIONAL

 A) RETRIBUCIÓNS ÁS QUE ESTA TEN DEREITO CONFORME Á LEXISLACIÓN APLICABLE DO ESTADO MEMBRO DE ACOLLIDA (*)

 B) DISPOSICIÓN RELATIVA AO REEMBOLSO DOS GASTOS DE VIAXE, ALOXAMENTO, MANUTENCIÓN E, DE EXISTIR, COMPLEMENTO ESPECÍFICO POR DES-
 PRAZAMENTO: [COMPLETAR]

 C) LIGAZÓN AO PORTAL WEB OFICIAL ÚNICO A ESCALA NACIONAL EN MATERIA DE DESPRAZAMENTO DESENVOLVIDO POLO ESTADO OU ESTADOS MEM-
 BRO DE ACOLLIDA: [COMPLETAR]

  En [LUGAR], a [DÍA] de [MES] de [AÑO].

                                                                             O/a representante
                                                                                da empresa

(*) [COMPLETAR] Esta información poderá derivarse dunha referencia ás disposicións legais ou regulamentarias ou aos convenios colectivos de aplicación que regulen devanditos
       extremos, sempre que devandita referencia sexa precisa e permita identificar claramente as disposicións aplicables.

                                            IMPORTANTE: [COMPLETAR]

  O formulario orixinal xérase protexido para evitar modificacións durante o seu enchemento. Unha vez
   finalizada esta, debe xerarse un novo documento, destinado exclusivamente á sinatura electrónica,
           mediante a impresión a PDF/PDF utilizando a impresora “Microsoft Print to PDF/PDF”.

                   Este novo documento non incorporará restricións de seguridade
                 e poderá ser asinado electronicamente polas persoas intervenientes,
            sendo a propia sinatura electrónica a que garantirá a integridade do documento.

                                    Xerar PDF/PDF para firma

                 No caso de que este documento non se asine por medios electrónicos,
todas as páxinas cumprimentadas deberán ir asinadas na marxe esquerda para maior seguridade xurídica.

             Unha vez asinado este documento, poñerase ao dispor da persoa traballadora
       mediante entrega en formato electrónico ou en soporte papel, sempre que sexa accesible,
   que se poida almacenar e imprimir e que a empresa conserve a proba da transmisión ou recepción.

════════════════════════════════════════════════════════════════════════
