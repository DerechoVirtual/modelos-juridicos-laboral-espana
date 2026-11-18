---
name: anexo-horas-complementarias-contrato-tiempo-parcial-41
description: "Redacta el escrito «Anexo de horas complementarias (contrato a tiempo parcial) (en gallego)» (formulario 41 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Anexo de horas complementarias (contrato a tiempo parcial) (en gallego)

> Formulario 0041 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- [ ] Nº (2 veces)
- [ ] LUGAR
- [ ] DÍA
- [ ] MES
- [ ] AÑO
- [ ] ÓRGANO
- [ ] Otros 23 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…s complementarias anuais, que supoñen un»; «…istrado no Servizo Público de Emprego de»; «…con data»; «…ora á realización das mesmas, a pesar de»; «…ementarias VOLUNTARIAS, cuxo número será»; «…. O/o traballador/a»; «…da empresa»; «…arcial, conforme ás seguintes regras: a)»; «… pactase expresamente co traballador. b)»; «…acto especifico respecto ao contrato. c)»; «…alizarase necesariamente por escrito. d)»; «…ez horas semanais en cómputo anual. e)»; …

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

### Formulario 0041 · Anexo de horas complementarias (contrato a tiempo parcial) (en gallego)

- Año del modelo: 2024
- Revisión 17-11-2026: 8 llamadas a nota sin texto retiradas; 26 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

ANEXO AO CONTRATO DE TRABALLO TEMPORAL E INDEFINIDO A TEMPO PARCIAL SOBRE PACTO DE HORAS
COMPLEMENTARIAS

                                                                             CLÁUSULAS

PRIMEIRA: a persoa traballadora contratada comprométese a realizar, a pedimento da persoa empresaria, ata un máximo de [Nº] horas
complementarias anuais, que supoñen un [COMPLETAR] % respecto ás horas pactadas no contrato celebrado o día
e comunicado ou rexistrado no Servizo Público de Emprego de [COMPLETAR]
con data [COMPLETAR] co número

SEGUNDA: a distribución e forma de realización das horas complementarias pactada deberá aterse ao establecido ao respecto no convenio colectivo
de aplicación e no pacto de horas complementarias.

TERCEIRA: a persoa empresaria preavisará cun mínimo de [Nº] días de antelación á súa realización o día e a hora en que a persoa
traballadora deberá realizar as horas complementarias, dentro dos máximos establecidos nos apartados anteriores.

CUARTA: a realización de horas complementarias haberá de respectar en todo caso limítelos en materia de xornada e descansos establecidos nos
apartados 1 e 4 do artigo 34, apartado 1 do artigo 36 e apartado 1 do artigo 37 do Estatuto dos Traballadores.

QUINTA: as horas complementarias efectivamente realizadas retribuiranse como ordinarias, computándose a efectos de base de cotización á
Seguridade Social e períodos de carencia e bases reguladoras das prestacións.

SEXTA: o pacto de horas complementarias poderá quedar sen efecto por renuncia da persoa traballadora mediante un aviso previo de quince días,
cando concorran as circunstancias reguladas no apartado 5.e) do articulo 12 do Estatuto dos Traballadores.

SÉTIMA: no caso de que a persoa empresaria incumprise calquera das estipulacións referidas neste ANEXO, así como as obrigacións establecidas no
articulo 12.5 do Estatuto dos Traballadores para as horas complementarias, a negativa da persoa traballadora á realización das mesmas, a pesar de [COMPLETAR]
pactarse, non constituirá conduta sancionable.

OITAVA: pódense acordar a realización de horas complementarias VOLUNTARIAS, cuxo número será [COMPLETAR], vinculadas o
contrato indefinido cuxos datos se contemplan na cláusula PRIMEIRA.

E para que conste, asínase o presente anexo por triplicado exemplar, no lugar e data que a continuación indicamos, asinando as partes interesadas

 En [LUGAR], a [DÍA] de [MES] de [AÑO].

                     O/o traballador/a [COMPLETAR] O/a representante [ÓRGANO] O/a representante legal
                                                                                 da empresa [COMPLETAR] do/a menor, se procede

   As horas complementarias non poderán ser superiores ao 30% das horas ordinarias de traballo do contrato, salvo que o convenio colectivo de ámbito sectorial, ou na
      súa falta inferior, estableza outra porcentaxe, que en ningún caso excederá do 60% das horas ordinarias pactadas. A suma das horas ordinarias e complementarias
      non poderá exceder do límite legal do traballo a tempo parcial
   Establecerase o prazo previsto nos convenios colectivos e, na súa falta, 3 días.
   Non poderán superar o 15%, ampliables ao 30% por convenio colectivo A negativa do traballador á realización destas horas non é conduta sancionable Artigo 12.5 g)
      do Estatuto dos Traballadores.
   PROTECCIÓN DE DATOS. Os datos consignados no presente contrato terán a protección derivada do REGULAMENTO (UE) 2016/679 do Parlamento Europeo e do
      Consello, do 27 de abril de 2016 relativo á protección das persoas físicas no que respecta ao tratamento de datos privados e á libre circulación destes datos e polo que
      se derroga a Directiva 95/46/CE (Regulamento xeral de protección de datos) e da Lei Orgánica 3/2018, do 5 de decembro, de Protección de Datos Privados e garantía
      dos dereitos dixitais..

PACTO DE HORAS COMPLEMENTARIAS

Considéranse horas complementarias as realizadas como adición ás horas ordinarias pactadas no contrato a tempo parcial, conforme ás seguintes regras:

a) [COMPLETAR] O empresario só poderá esixir a realización de horas complementarias cando así o pactase expresamente co traballador.

b) [COMPLETAR] O pacto sobre horas complementarias poderá acordarse no momento da celebración do contrato a tempo parcial ou con posterioridade ao mesmo, pero
     constituirá, en todo caso, un pacto especifico respecto ao contrato.

c) [COMPLETAR] O pacto formalizarase necesariamente por escrito.

d) [COMPLETAR] Só se poderá formalizar un pacto de horas complementarias no caso de contratos a tempo parcial cunha xornada de traballo non inferior a dez horas semanais en
     cómputo anual.

e) [COMPLETAR] O pacto de horas complementarias deberá recoller o número de horas complementarias cuxa realización poderá ser requirida polo empresario.

f) [COMPLETAR] O número de horas complementarias pactadas non poderá exceder do 30% das horas ordinarias de traballo obxecto do contrato.

g) [COMPLETAR] Os convenios colectivos poderán establecer outra porcentaxe máxima, que, en ningún caso, poderá ser inferior ao citado 30% nin exceder do 60% das horas
     ordinarias contratadas.

h) [COMPLETAR] O traballador deberá coñecer o día e a hora de realización das horas complementarias pactadas cun aviso previo mínimo de tres días, salvo que o convenio
     estableza un prazo de aviso previo inferior.

i) [COMPLETAR] O pacto de horas complementarias poderá quedar sen efecto por renuncia do traballador, mediante un aviso previo de quince días, unha vez cumprido un ano
     desde a súa celebración, cando concorra algunha das seguintes circunstancias:

     - A atención das responsabilidades familiares enunciadas no artigo 37.6 (redución de xornada por garda legal do Real Decreto Lexislativo 2/2015, do 23 de [COMPLETAR]
     outubro, polo que se aproba o texto refundido da Lei do Estatuto dos Traballadores.

     - Por necesidades formativas, sempre que se acredite a incompatibilidade horaria.

     - Por incompatibilidade con outro contrato a tempo parcial.

j) [COMPLETAR] O pacto de horas complementarias e as condicións de realización das mesmas estarán suxeitos ás regras previstas nas letras anteriores. En caso de
     incumprimento de tales regras, a negativa do traballador á realización das horas complementarias, a pesar de ser pactadas, non constituirá conduta laboral
     sancionable.

k) [COMPLETAR] Sen prexuízo do pacto de horas complementarías, nos contratos a tempo parcial de duración indefinida cunha xornada de traballo non inferior a dez horas
     semanais en cómputo anual, o empresario poderá, en calquera momento, ofrecer ao traballador a realización de horas complementarías de aceptación voluntaria,
     cuxo número non poderá superar o 15%, ampliables ao 30% por convenio colectivo, das horas ordinarias obxecto do contrato. A negativa do traballador á
     realización destas horas non constituirá conduta laboral sancionable.

     Estas horas complementarias non se computarán a efectos das porcentaxes de horas complementarias pactadas que se establecen na letra e).

l) [COMPLETAR] A xornada dos traballadores a tempo parcial rexistrarase día a día e totalizarase mensualmente, entregando copia ao traballador, xunto co recibo de salarios, do
     resumo de todas as horas realizadas en cada mes, tanto as ordinarias como as complementarias.

     O empresario deberá conservar os resumos mensuais dos rexistros de xornada durante un período mínimo de catro anos.

     En caso de incumprimento das referidas obrigacións de rexistro, o contrato presumirase celebrado a xornada completa, salvo proba en contrario que acredite o
     carácter parcial dos servizos.

m) [COMPLETAR] A realización de horas complementarías haberá de respectar, en todo caso, limítelos en materia de xornada e descansos establecidos no Real Decreto Lexislativo
     2/2015, do 23 de outubro, polo que se aproba o teX1o refundido da Lei do Estatuto dos Traballadores, nos artigos 34, apartados 3 e 4 (descansos); 36.1 (traballo
     nocturno) e 37.1 (descanso semanal acumulable).

n) [COMPLETAR] As horas complementarias efectivamente realizadas retribuiranse como ordinarias, computándose a efectos de bases de cotización á Seguridade Social e
     períodos de carencia e bases reguladoras das prestacións. Para ese efecto, o número e retribución das horas complementarías realizadas deberase recoller no
     recibo individual de salarios e nos documentos de cotización á Seguridade Social.

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
