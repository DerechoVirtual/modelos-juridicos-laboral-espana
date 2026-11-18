---
name: informacion-trabajador-sobre-elementos-esenciales-1
description: "Redacta el escrito «Información al trabajador sobre los elementos esenciales del contrato» (formulario 1 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información al trabajador sobre los elementos esenciales del contrato

> Formulario 0001 del plugin **Contratación laboral** · revisado el 17-11-2026.

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
- [ ] Otros 51 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…E Y APELLIDOS DE LA PERSONA TRABAJADORA:»; «…NIF/NIE DE LA PERSONA TRABAJADORA:»; «…NOMBRE O RAZÓN SOCIAL DE LA EMPRESA:»; «…CIF/NIF EMPRESA:»; «…DOMICILIO SOCIAL DE LA EMPRESA:»; «…JO HABITUAL DONDE SE PRESTA EL SERVICIO:»; «…SONA TRABAJADORA EN TRABAJO A DISTANCIA:»; «…DICAR SI CONCURREN ESTAS CIRCUNSTANCIAS:»; «…LACIÓN LABORAL TIPO DE RELACIÓN LABORAL:»; «…/aaaa) CONTENIDO DE LA RELACIÓN LABORAL:»; «…EN RELACIONES LABORALES TEMPORALES:»; «…DURACIÓN PREVISTA DEL CONTRATO»; …

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

### Formulario 0001 · Información al trabajador sobre los elementos esenciales del contrato

- Año del modelo: 2026
- Revisión 17-11-2026: 39 casillas del modelo oficial marcadas en blanco; 11 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Documento informativo del RD 723/2026 (BOE-A-2026-19200, en vigor el 5-10-2026, deroga el RD 1659/1998): comprobar que recoge todos los extremos del art. 3.2 a)-q), incluidos periodo de prueba, formación, ETT, sistemas algorítmicos, plan de igualdad y protocolo de acoso, medidas LGTBI, mejoras voluntarias y planes de pensiones y supuestos de modificación.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MODELO DE DOCUMENTO INFORMATIVO SOBRE LOS ELEMENTOS ESENCIALES DEL CONTRATO
DE TRABAJO APLICABLE A LAS RELACIONES LABORALES DE DURACIÓN SUPERIOR A CUATRO SEMANAS

1. INFORMACIÓN GENERAL

A) IDENTIDAD DE LAS PARTES QUE SUSCRIBEN EL CONTRATO DE TRABAJO
NOMBRE Y APELLIDOS DE LA PERSONA TRABAJADORA: [COMPLETAR]

NIF/NIE DE LA PERSONA TRABAJADORA: [COMPLETAR]

NOMBRE O RAZÓN SOCIAL DE LA EMPRESA: [COMPLETAR]

CIF/NIF EMPRESA: [COMPLETAR]

DOMICILIO SOCIAL DE LA EMPRESA: [COMPLETAR]

CENTRO DE TRABAJO HABITUAL DONDE SE PRESTA EL SERVICIO: [COMPLETAR]

CENTRO DE TRABAJO AL QUE ESTÁ ADSCRITA LA PERSONA TRABAJADORA EN TRABAJO A DISTANCIA: [COMPLETAR]

CENTROS ITINERANTES, DIFERENTES CENTROS DE TRABAJO O DETERMINACIÓN LIBRE DEL LUGAR DE PRESTACIÓN DEL SERVICIO.
INDICAR SI CONCURREN ESTAS CIRCUNSTANCIAS: [COMPLETAR]

B) RELACIÓN LABORAL
TIPO DE RELACIÓN LABORAL: [COMPLETAR]

FECHA INICIO RELACIÓN LABORAL (dd/mm/aaaa)

CONTENIDO DE LA RELACIÓN LABORAL: [COMPLETAR]

EN RELACIONES LABORALES TEMPORALES: [COMPLETAR]
DURACIÓN PREVISTA DEL CONTRATO [COMPLETAR] FECHA FIN RELACIÓN LABORAL (dd/mm/aaaa): [COMPLETAR]

CAUSA HABILITANTE DE LA CONTRATACIÓN: [COMPLETAR]

CIRCUNSTANCIAS CONCRETAS QUE JUSTIFICAN LA CONTRATACIÓN: [COMPLETAR]

CONEXIÓN CON LA DURACIÓN PREVISTA DEL CONTRATO: [COMPLETAR]

C) PUESTO DE TRABAJO
 CATEGORÍA O GRUPO PROFESIONAL: [COMPLETAR]

 CARACTERIZACIÓN O DESCRIPCIÓN RESUMIDA DEL PUESTO DE TRABAJO, EN TÉRMINOS QUE PERMITAN CONOCER CON SUFICIENTE PRECISIÓN
 EL CONTENIDO ESPECÍFICO DEL TRABAJO: [COMPLETAR]

D) SALARIO
 CUANTÍA DEL SALARIO BASE (*): [COMPLETAR]

 CUANTÍA DE LOS COMPLEMENTOS SALARIALES (*): [COMPLETAR]

 PERIODICIDAD (*): [COMPLETAR]

 MÉTODO PAGO (*): [COMPLETAR]

 MODO DE CÁLCULO DE LOS CONCEPTOS SALARIALES VARIABLES: [COMPLETAR]

 CRITERIOS QUE DETERMINAN LA PERCEPCIÓN DE LOS CONCEPTOS SALARIALES VARIABLES: [COMPLETAR]

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

E) TIEMPO DE TRABAJO
 DURACIÓN Y DISTRIBUCIÓN HORARIA DE LA JORNADA ORDINARIA DE TRABAJO (*): [COMPLETAR]

 TRABAJO NOCTURNO O A TURNOS (*): [COMPLETAR]

 PROCEDIMIENTO PARA LA MODIFICACIÓN DE LOS TURNOS Y LA DURACIÓN Y DISTRIBUCIÓN DE LA JORNADA (*): [COMPLETAR]

 ACUERDOS RELATIVOS A HORAS EXTRAS Y SU RETRIBUCIÓN (*): [COMPLETAR]

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

 DURACIÓN DE LAS VACACIONES Y PROCEDIMIENTOS PARA FIJAR EL PERIODO O PERIODOS DE SU DISFRUTE (*): [COMPLETAR]

 SISTEMA PARA LA DISTRIBUCIÓN IRREGULAR DE JORNADA: [COMPLETAR]

 PERIODOS DE PREAVISO PARA EL INICIO Y CANCELACIÓN DE TAREAS: [COMPLETAR]

 PERIODOS ESTIMADOS DE ACTIVIDAD E INACTIVIDAD EN CONTRATOS INDEFINIDOS FIJOS DISCONTINUOS: [COMPLETAR]

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

F) PERÍODO DE PRUEBA, CUANDO SE CONCIERTE
 DURACIÓN DEL PERÍODO DE PRUEBA (*): [COMPLETAR]

 INFORMACIÓN RELATIVA A LAS OBLIGACIONES RESPECTIVAS DE LA EMPRESA Y DE LA PERSONA TRABAJADORA A REALIZAR LAS EXPERIENCIAS QUE
 CONSTITUYAN EL OBJETO DE LA PRUEBA (*): [COMPLETAR]

G) FORMACIÓN
 FORMACIÓN A PROPORCIONAR POR LA EMPRESA, EN EL SUPUESTO DE QUE SEA OBLIGATORIA PARA EL DESEMPEÑO DEL PUESTO DE TRABAJO (*): [COMPLETAR]

H) EMPRESAS DE TRABAJO TEMPORAL, EN EL CASO DE PERSONAS TRABAJADORAS CEDIDAS POR
EMPRESAS DE TRABAJO TEMPORAL
 IDENTIDAD DE LA EMPRESA USUARIA Y LA CAUSA QUE HABILITA A LA CELEBRACIÓN DE CADA CONTRATO DE PUESTA A DISPOSICIÓN: [COMPLETAR]

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

I) EXISTENCIA DE SISTEMAS ALGORÍTMICOS O AUTOMATIZADOS DE TOMA DE DECISIONES RELACIONADOS
CON A FIJACIÓN, VARIACIÓN O MODIFICACIÓN DE CONDICIONES DE TRABAJO

J) IDENTIFICACIÓN, SI EXISTE, DEL PLAN DE IGUALDAD APLICABLE A LA EMPRESA, EN CASO DE QUE SE
DISPONGA, POLÍTICA EMPRESARIAL DE CONCILIACIÓN Y PROTOCOLO DE ACOSO SEXUAL Y POR RAZÓN DE [COMPLETAR]
SEXO EN LA EMPRESA: [COMPLETAR]

K) MEDIDAS Y RECURSOS PARA ALCANZAR LA IGUALDAD REAL Y EFECTIVA DE LAS PERSONAS LGTBI,
EN CASO DE QUE SE DISPONGA DE ELLOS

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

L) PROCEDIMIENTO DE EXTINCIÓN DEL CONTRATO, INCLUIDOS LOS REQUISITOS FORMALES
Y LA DURACIÓN DE LOS PLAZOS DE PREAVISO (*)

M) CONVENIO O CONVENIOS COLECTIVOS APLICABLES A LA RELACIÓN LABORAL

N) SISTEMA DE COLABORACIÓN EN LA GESTIÓN DE LA SEGURIDAD SOCIAL QUE OPERA EN LA EMPRESA (*)

O) SUPUESTOS Y PROCEDIMIENTO A SEGUIR PARA MODIFICAR EL CONTENIDO DE LA RELACIÓN LABORAL,
LA CATEGORÍA O GRUPO PROFESIONAL, EL SALARIO Y EL TIEMPO DE TRABAJO: [COMPLETAR]

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

 2. INFORMACIÓN ADICIONAL EN LOS SUPUESTOS DE PRESTACIÓN DE SERVICIOS EN EL EXTRANJERO.
 APLICABLE SOLO SI LA DURACIÓN DE CADA PERIODO DE TRABAJO EN EL EXTRANJERO REBASA
 LAS CUATRO SEMANAS CONSECUTIVAS

 A) EL PAÍS O PAÍSES EN LOS QUE DEBE LLEVARSE A CABO EL TRABAJO

 B) LA DURACIÓN DEL TRABAJO QUE VAYA A PRESTARSE EN EL EXTRANJERO

 C) LA MONEDA DE CURSO LEGAL EN LA QUE SE PAGARÁ EL SALARIO (*)

 D) LAS RETRIBUCIONES EN DINERO O EN ESPECIE, ASÍ COMO LAS COMPENSACIONES POR GASTOS, GASTOS DE VIAJE, DIETAS Y LAS VENTAJAS
 VINCULADAS A LA CIRCUNSTANCIA DE LA PRESTACIÓN DE SERVICIOS EN EL EXTRANJERO: [COMPLETAR]

 E) SI SE ENCUENTRA PREVISTA LA REPATRIACIÓN DE LA PERSONA TRABAJADORA Y SUS CONDICIONES

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
      extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

 3. EN EL CASO DE UNA PERSONA TRABAJADORA DESPLAZADA AL TERRITORIO DE ESTADOS MIEMBROS
 DE LA UNIÓN EUROPEA O DE ESTADOS SIGNATARIOS DEL ACUERDO SOBRE EL ESPACIO ECONÓMICO
 EUROPEO EN EL MARCO DE UNA PRESTACIÓN DE SERVICIOS TRANSNACIONAL

 A) RETRIBUCIONES A LAS QUE ESTA TIENE DERECHO CON ARREGLO A LA LEGISLACIÓN APLICABLE DEL ESTADO MIEMBRO DE ACOGIDA (*)

 B) DISPOSICIÓN RELATIVA AL REEMBOLSO DE LOS GASTOS DE VIAJE, ALOJAMIENTO, MANUTENCIÓN Y, DE EXISTIR, COMPLEMENTO ESPECÍFICO POR
 DESPLAZAMIENTO: [COMPLETAR]

 C) ENLACE AL PORTAL WEB OFICIAL ÚNICO A ESCALA NACIONAL EN MATERIA DE DESPLAZAMIENTO DESARROLLADO POR EL ESTADO
 O ESTADOS MIEMBROS DE ACOGIDA: [COMPLETAR]

  En [LUGAR], a [DÍA] de [MES] de [AÑO].

                                                                              El/la representante
                                                                                de la empresa

(*) [COMPLETAR] Esta información podrá derivarse de una referencia a las disposiciones legales o reglamentarias o a los convenios colectivos de aplicación que regulen dichos
       extremos, siempre que dicha referencia sea precisa y permita identificar claramente las disposiciones aplicables.

                                               IMPORTANTE: [COMPLETAR]

     El formulario original se genera protegido para evitar modificaciones durante su cumplimentación.
Una vez finalizada ésta, debe generarse un nuevo documento, destinado exclusivamente a la firma electrónica,
                 mediante la impresión a PDF utilizando la impresora “Microsoft Print to PDF”.

                     Este nuevo documento no incorporará restricciones de seguridad
                   y podrá ser firmado electrónicamente por las personas intervinientes,
              siendo la propia firma electrónica la que garantizará la integridad del documento.

                                       Generar PDF para firma

                    En caso de que este documento no se firme por medios electrónicos,
todas las páginas cumplimentadas deberán ir firmadas en el margen izquierdo para mayor seguridad jurídica.

            Una vez firmado este documento, se pondrá a disposición de la persona trabajadora
          mediante entrega en formato electrónico o en soporte papel, siempre que sea accesible,
   que se pueda almacenar e imprimir y que la empresa conserve la prueba de la transmisión o recepción.

════════════════════════════════════════════════════════════════════════
