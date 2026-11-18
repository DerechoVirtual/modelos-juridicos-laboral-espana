---
name: anexo-horas-complementarias-contrato-tiempo-parcial-38
description: "Redacta el escrito «Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano)» (formulario 38 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano)

> Formulario 0038 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- [ ] Otros 29 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…a persona empresària, fins a un màxim de»; «…s complementàries anuals, que suposen un»; «…istrat en el Servei Públic d’Ocupació de»; «…amb data»; «…na empresària preavisarà amb un mínim de»; «…VOLUNTÀRIES, el número de les quals serà»; «…diquem, signant les parts interessades A»; «…el»; «…el [COMPLETAR] de»; «…el [COMPLETAR] de [COMPLETAR] de»; «…El/la treballador/a»; «…El/la representant»; …

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

### Formulario 0038 · Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano)

- Año del modelo: 2024
- Revisión 17-11-2026: 8 llamadas a nota sin texto retiradas; 28 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

ANNEX AL CONTRACTE DE TREBALL TEMPORAL I INDEFINIT A TEMPS PARCIAL SOBRE PACTE D’HORES
COMPLEMENTÀRIES

                                                                              CLÀUSULES

PRIMERA: la persona treballadora contractada es compromet a realitzar, a petició de la persona empresària, fins a un màxim de [COMPLETAR]
hores complementàries anuals, que suposen un [COMPLETAR] % respecte a les hores pactades en el contracte subscrit el dia
i comunicat o registrat en el Servei Públic d’Ocupació de [COMPLETAR]
amb data [COMPLETAR] amb el número

SEGONA: la distribució i forma de realització de les hores complementàries pactada haurà d’atenir-se al que s’estableix al respecte en el conveni
col·lectiu d’aplicació i en el pacte d’hores complementàries.

TERCERA: la persona empresària preavisarà amb un mínim de [COMPLETAR] dies d’antelació a la seva realització el dia i l’hora en què la persona
treballadora haurà de realitzar les hores complementàries, dins dels màxims establerts en els apartats anteriors.

QUARTA: la realització d’hores complementàries haurà de respectar en tot cas els limitis en matèria de jornada i descansos establerts en els apartats 1
i 4 de l’article 34, apartat 1 de l’article 36 i apartat 1 de l’article 37 de l’Estatut dels Treballadors.

QUINTA: les hores complementàries efectivament realitzades es retribuiran com a ordinàries, computant-se a l’efecte de base de cotització a la
Seguretat Social i períodes de manca i bases reguladores de les prestacions.

SISENA: el pacte d’hores complementàries podrà quedar sense efecte per renúncia de la persona treballadora mitjançant un preavís de quinze dies,
quan concorrin les circumstàncies regulades en l’apartat 5.e) de l’articulo 12 de l’Estatut dels Treballadors.

SETENA: en cas que la persona empresària incomplís qualsevol de les estipulacions referides en aquest ANNEX, així com les obligacions establertes
en l’articulo 12.5 de l’Estatut dels Treballadors per a les hores complementàries, la negativa de la persona treballadora a la realització d’aquestes,
malgrat haver-se pactat, no constituirà conducta sancionable.

OCTAVA: es poden recordar la realització d’hores complementàries VOLUNTÀRIES, el número de les quals serà [COMPLETAR],
vinculades al contracte indefinit les dades del qual es contemplen en la clàusula PRIMERA.

I per deixar-ne constància, se signa el present annex per triplicat exemplar, en el lloc i data que a continuació indiquem, signant les parts interessades

  A [COMPLETAR] el [COMPLETAR] de [COMPLETAR] de [COMPLETAR]

                     El/la treballador/a [COMPLETAR] El/la representant [COMPLETAR] El/la representant legal
                                                                                 de l’empresa [COMPLETAR] del/la menor, si escau

   Les hores complementàries no podran ser superiors al 30% de les hores ordinàries de treball del contracte, tret que el conveni col·lectiu d’àmbit sectorial, o en defecte
      d’això inferior, estableixi un altre percentatge, que en cap cas excedirà del 60% de les hores ordinàries pactades. La suma de les hores ordinàries i complementàries no
      podrà excedir del límit legal del treball a temps parcial
   S’establirà el termini previst en els convenis col·lectius i, en defecte d’això, 3 dies.
   No podran superar el 15%, ampliables al 30% per conveni col·lectiu La negativa del treballador a la realització d’aquestes hores no és conducta sancionable Article
      12.5 g) de l’Estatut dels Treballadors.
   PROTECCIÓ DE DADES. Les dades consignades en el contracte actual tindran la protecció derivada del REGLAMENT (UE) 2016/679 del Parlament Europeu i del [COMPLETAR]
      Consell, de 27 d’abril de 2016 relatiu a la protecció de les persones físiques pel que fa al tractament de dades personals i a la lliure circulació d’aquestes dades i pel
      qual es deroga la Directiva 95/46/CE (Reglament general de protecció de dades) i de la Llei orgànica 3/2018, de 5 de desembre, de Protecció de Dades Personals i
      garantia dels drets digitals.

PACTE D’HORES COMPLEMENTÀRIES

Es consideren hores complementàries les realitzades com a addició a les hores ordinàries pactades en el contracte a temps parcial, conforme a les següents regles:

a) [COMPLETAR] L’empresari només podrà exigir la realització d’hores complementàries quan així ho hagués pactat expressament amb el treballador.

b) [COMPLETAR] El pacte sobre hores complementàries podrà acordar-se en el moment de la celebració del contracte a temps parcial o amb posterioritat a aquest, però constituirà,
     en tot cas, un pacte especifico respecte al contracte.

c) [COMPLETAR] El pacte es formalitzarà necessàriament per escrit.

d) [COMPLETAR] Només es podrà formalitzar un pacte d’hores complementàries en el cas de contractes a temps parcial amb una jornada de treball no inferior a deu hores
     setmanals en còmput anual.

e) [COMPLETAR] El pacte d’hores complementàries haurà de recollir el nombre d’hores complementàries la realització de les quals podrà ser requerida per l’empresari.

f) [COMPLETAR] El nombre d’hores complementàries pactades no podrà excedir del 30% de les hores ordinàries de treball objecte del contracte.

g) [COMPLETAR] Els convenis col·lectius podran establir un altre percentatge màxim, que, en cap cas, podrà ser inferior al citat 30% ni excedir del 60% de les hores ordinàries
     contractades.

h) [COMPLETAR] El treballador haurà de conèixer el dia i l’hora de realització de les hores complementàries pactades amb un preavís mínim de tres dies, tret que el conveni
     estableixi un termini de preavís inferior.

i) [COMPLETAR] El pacte d’hores complementàries podrà quedar sense efecte per renúncia del treballador, mitjançant un preavís de quinze dies, una vegada complert un any des
     de la seva celebració, quan concorri alguna de les següents circumstàncies:

     - L’atenció de les responsabilitats familiars enunciades en l’article 37.6 (reducció de jornada per guarda legal del reial decret legislatiu 2/2015, de 23 d’octubre, pel
     qual s’aprova el text refós de la Llei de l’Estatut dels Treballadors.

     - Per necessitats formatives, sempre que s’acrediti la incompatibilitat horària.

     - Per incompatibilitat amb un altre contracte a temps parcial.

j) [COMPLETAR] El pacte d’hores complementàries i les condicions de realització de les mateixes estaran subjectes a les regles previstes en les lletres anteriors. En cas
     d’incompliment de tals regles, la negativa del treballador a la realització de les hores complementàries, malgrat haver estat pactades, no constituirà conducta
     laboral sancionable.

k) [COMPLETAR] Sense perjudici del pacte d’hores complementaries, en els contractes a temps parcial de durada indefinida amb una jornada de treball no inferior a deu hores
     setmanals en còmput anual, l’empresari podrà, en qualsevol moment, oferir al treballador la realització d’hores complementaries d’acceptació voluntària, el
     número de la qual no podrà superar el 15%, ampliables al 30% per conveni col·lectiu, de les hores ordinàries objecte del contracte. La negativa del treballador a la
     realització d’aquestes hores no constituirà conducta laboral sancionable.

     Aquestes hores complementàries no es computaran a l’efecte dels percentatges d’hores complementàries pactades que s’estableixen en la lletra e).

l) [COMPLETAR] La jornada dels treballadors a temps parcial es registrarà dia a dia i es totalitzarà mensualment, lliurant còpia al treballador, juntament amb el rebut de salaris, del
     resum de totes les hores realitzades en cada mes, tant les ordinàries com les complementàries.

     L’empresari haurà de conservar els resums mensuals dels registres de jornada durant un període mínim de quatre anys.

     En cas d’incompliment de les referides obligacions de registre, el contracte es presumirà celebrat a jornada completa, excepte prova en contra que acrediti el
     caràcter parcial dels serveis.

m) [COMPLETAR] La realització d’hores complementaries haurà de respectar, en tot cas, els limitis en matèria de jornada i descansos establerts en el reial decret legislatiu 2/2015,
     de 23 d’octubre, pel qual s’aprova el *teX1o refós de la Llei de l’Estatut dels Treballadors, en els articles 34, apartats 3 i 4 (descansos); 36.1 (treball nocturn) i 37.1
     (descans setmanal acumulable).

n) [COMPLETAR] Les hores complementàries efectivament realitzades es retribuiran com a ordinàries, computant-se a l’efecte de bases de cotització a la Seguretat Social i
     períodes de manca i bases reguladores de les prestacions. A aquest efecte, el número i retribució de les hores complementaries realitzades s’haurà de recollir en
     el rebut individual de salaris i en els documents de cotització a la Seguretat Social.

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
