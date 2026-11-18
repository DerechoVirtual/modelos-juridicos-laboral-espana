---
name: prorroga-contrato-trabajo-acogida-real-decreto-37
description: "Redacta el escrito «Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en catalán)» (formulario 37 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en catalán)

> Formulario 0037 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] NÚMERO
- [ ] Otros 41 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…IÓ DE PRÒRROGA DEL CONTRACTE DE TREBALL:»; «…DEL DE CONTRACTE OBJECTE DE LA PRÒRROGA:»; «…ACOLLIT AL REIAL DECRET:»; «…DADES DE L’EMPRESA CIF/NIF/NIE:»; «…SR./SRA. NIF/NIE:»; «… CONCEPTE NOM O RAÓ SOCIAL DE L’EMPRESA:»; «…DOMICILI SOCIAL:»; «…DOMICILI SOCIAL: [COMPLETAR] MUNICIPI:»; «…MUNICIPI: [COMPLETAR] CODI POSTAL»; «…CODI POSTAL [COMPLETAR] PAÍS:»; «…DADES DEL COMPTE DE COTITZACIÓ RÈGIM»; «…CODI (CCC):»; …

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

### Formulario 0037 · Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en catalán)

- Año del modelo: 2024
- Revisión 17-11-2026: 19 casillas del modelo oficial marcadas en blanco; 6 llamadas a nota sin texto retiradas; 22 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

COMUNICACIÓ DE PRÒRROGA DEL CONTRACTE DE TREBALL: [COMPLETAR]

DADES DEL CONTRACTE
MODEL DE CONTRACTE OBJECTE DE LA PRÒRROGA: [COMPLETAR]

ACOLLIT AL REIAL DECRET: [COMPLETAR]

DADES DE L’EMPRESA
CIF/NIF/NIE: [COMPLETAR]

SR./SRA. NIF/NIE: [COMPLETAR]

EN CONCEPTE

NOM O RAÓ SOCIAL DE L’EMPRESA: [COMPLETAR]

DOMICILI SOCIAL: [COMPLETAR]

MUNICIPI: [COMPLETAR]

CODI POSTAL [COMPLETAR] PAÍS: [COMPLETAR]

DADES DEL COMPTE DE COTITZACIÓ
RÈGIM [COMPLETAR] CODI (CCC): [COMPLETAR]

ACTIVITAT ECONÒMICA: [COMPLETAR]

DADES DEL CENTRE DE TREBALL
MUNICIPI: [COMPLETAR]

CODI POSTAL [COMPLETAR] PAÍS: [COMPLETAR]

DADES DE LA PERSONA TREBALLADORA
SR./SRA. NIF/NIE: [COMPLETAR]

DATA NAIXEMENT (dd/mm/aaaa) [COMPLETAR] Nº SEGURETAT SOCIAL [COMPLETAR] NACIONALITAT: [COMPLETAR]

NIVELL FORMATIU: [COMPLETAR]

MUNICIPI DEL DOMICILI: [COMPLETAR]

CODI POSTAL [COMPLETAR] PAÍS DOMICILI: [COMPLETAR]

DADES DE L’ASSISTÈNCIA LEGAL (SI ÉS EL CAS)
SR./SRA. NIF/NIE: [COMPLETAR]

EN QUALITAT

   Director/a, Gerent, etc.
   Pare, mare, tutor/a o persona o institució que li tingui al seu càrrec.

                                                                      COMUNIQUEN

Al Servei Públic d’Ocupació de [COMPLETAR]

que han acordat una [COMPLETAR] pròrroga de [COMPLETAR] mesos de durada,
des del [COMPLETAR] fins al [COMPLETAR] del contracte que amb data
i una durada inicial de [COMPLETAR] mesos, va ser celebrat per les parts anteriorment esmentades i registrat en el Servei Públic d’Ocupació de [COMPLETAR]

en data [COMPLETAR] amb el número [NÚMERO] sent el temps acumulat del contracte inicial més la(s) pròrroga(s)
d’

  A [COMPLETAR] el [COMPLETAR] de [COMPLETAR] de [COMPLETAR]

                     El/la treballador/a [COMPLETAR] El/la representant [COMPLETAR] El/la representant legal
                                                                          de l’empresa [COMPLETAR] del/la menor, si escau

PROTECCIÓ DE DADES. - Les dades consignades en el present model tindran la protecció derivada del Reglament (UE) 2016/679 del Parlament
Europeu, de 27 d’abril de 2016 i de la Llei orgànica 3/2018, de 5 de desembre.

 Primera, segona, tercera, etc.

                                               IMPORTANT: [COMPLETAR]

       El formulari original es genera protegit per a evitar modificacions durant el seu emplenament.
        Una vegada finalitzada aquesta, ha de generar-se un nou document, destinat exclusivament
a la signatura electrònica, mitjançant la impressió a PDF utilitzant la impressora “Microsoft Print to PDF”.

                     Aquest nou document no incorporarà restriccions de seguretat
                    i podrà ser signat electrònicament per les persones intervinents,
             sent la pròpia signatura electrònica la que garantirà la integritat del document.

                                       Generar PDF para firma

                    En cas que aquest document no se signi per mitjans electrònics,
totes les pàgines emplenades hauran d’anar signades en el marge esquerre per a major seguretat jurídica.

════════════════════════════════════════════════════════════════════════
