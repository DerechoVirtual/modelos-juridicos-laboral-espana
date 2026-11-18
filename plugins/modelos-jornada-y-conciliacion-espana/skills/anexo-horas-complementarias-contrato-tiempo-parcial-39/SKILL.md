---
name: anexo-horas-complementarias-contrato-tiempo-parcial-39
description: "Redacta el escrito «Anexo de horas complementarias (contrato a tiempo parcial) (en euskera)» (formulario 39 de jornada, permisos y conciliación, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Anexo de horas complementarias (contrato a tiempo parcial) (en euskera)

> Formulario 0039 del plugin **Jornada, permisos y conciliación** · revisado el 17-11-2026.

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

- [ ] Otros 23 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…esaburuak hala eskatuta, urtean gehienez»; «…ordu osagarri egiteko, hau da,»; «…tratutako kontratuan itundutako orduen %»; «…tea erabaki daiteke. Ordu horien kopurua»; «…(e)n,»; «…(e)ko»; «…(e)ko [COMPLETAR] ren»; «…(e)(a)n Langilea»; «…Enpresaren ordezkaria»; «…ko orduak, honako arau hauen arabera: a)»; «…riaz adostu beharko du langilearekin. b)»; «…buruzko itun espezifikoa izango da. c)»; …

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

### Formulario 0039 · Anexo de horas complementarias (contrato a tiempo parcial) (en euskera)

- Año del modelo: 2024
- Revisión 17-11-2026: 8 llamadas a nota sin texto retiradas; 22 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

ORDU OSAGARRIEN ITUNARI BURUZKO LANALDI PARTZIALEKO ALDI BATERAKO LAN-KONTRATU
MUGAGABEAREN ERANSKINA

                                                                           KLAUSULAK

LEHENENGOA: kontratatutako langileak konpromisoa hartzen du, enpresaburuak hala eskatuta, urtean gehienez [COMPLETAR] ordu osagarri egiteko,
hau da, [COMPLETAR] egindako eta
Enplegu Zerbitzu Publikoan jakinarazitako edo erregistratutako kontratuan itundutako orduen % [COMPLETAR],
zenbakiarekin.

BIGARRENA: itundutako ordu osagarrien banaketak eta egiteko moduak aplikatu beharreko hitzarmen kolektiboan eta ordu osagarrien itunean horri
buruz ezarritakoa bete beharko dute.

HIRUGARRENA: langileak ordu osagarriak zein egun eta ordutan egin behar dituen jakinarazi beharko du enpresaburuak, gutxienez
eguneko aurrerapenarekin, aurreko ataletan ezarritako gehieneko mugen barruan.

LAUGARRENA: ordu osagarriak egiteko, beti errespetatu beharko dira Langileen Estatutuaren 34. artikuluko 1. paragrafoan eta 37. artikuluko 1.
paragrafoan ezarritako lanaldi- eta atseden-mugak.

BOSGARRENA: benetan egindako ordu osagarriak ohiko gisa ordainduko dira, eta Gizarte Segurantzako kotizazio-oinarriaren, gabealdien eta
prestazioen oinarri arautzaileen ondorioetarako zenbatuko dira.

SEIGARRENA: ordu osagarrien ituna indarrik gabe geratu ahal izango da langileak hamabost egun lehenago jakinaraziz gero, Langileen Estatutuaren
12. artikuluko 5.e) idatz-zatian araututako inguruabarrak gertatzen direnean.

ZAZPIGARRENA: enpresaburuak ez badu betetzen ERANSKIN honetan adierazitako edozein klausula, eta Langileen Estatutuaren 12.5 artikuluan
ordu osagarrietarako ezarritako betebeharrak betetzen ez baditu, langileak ordu horiek egiteari uko egitea, nahiz eta hitzartuta egon, ez da zehatzeko
moduko jokabidea izango.

ZORTZIGARRENA: BORONDATEZKO ordu osagarriak egitea erabaki daiteke. Ordu horien kopurua [COMPLETAR] izango da, eta
LEHENENGO klausulan jasotako datuak dituen kontratu mugagabeari lotuta egongo da.

Eta horrela jasota gera dadin, eranskin hau sinatu da, hiru aletan, jarraian adierazten den lekuan eta egunean, alderdi interesdunek sinatuta.

                                                                                         (e)n, [COMPLETAR] (e)ko [COMPLETAR] ren [COMPLETAR] (e)(a)n

                        Langilea [COMPLETAR] Enpresaren ordezkaria [COMPLETAR] Adingabearen legezko ordezkaria,
                                                                                                                                     hala badagokio

   Ordu osagarriak ezin izango dira izan kontratuko ohiko lan-orduen % 30 baino gehiago, salbu eta sektoreko hitzarmen kolektiboak, edo, halakorik ezean, gutxiago,
      beste ehuneko bat ezartzen badu; ehuneko horrek ez du inola ere gaindituko itundutako ordu arrunten % 60. Ohiko orduen eta ordu osagarrien baturak ezin izango du
      lanaldi partzialeko lanaren legezko muga gainditu.
   Hitzarmen kolektiboetan aurreikusitako epea ezarriko da, eta, halakorik ezean, 3 egun.
   Ezin izango dute % 15 gainditu, eta hitzarmen kolektibo bidez % 30era zabaldu ahal izango dira. Langileak ordu horiek egiteari uko egitea ez da zehatzeko moduko
      jokabidea Langileen Estatutuaren 12.5 g) artikulua.
   DATUEN BABESA. Kontratu honetan jasotako datuek Europako Parlamentuaren eta Kontseiluaren 2016ko apirilaren 27ko 2016/679 (EB) ERREGELAMENDUA,
      datu pertsonalen tratamenduari eta datu horien zirkulazio askeari dagokienez pertsona fisikoak babesteari buruzkoa eta 95/46/EE Zuzentaraua (Datuak Babesteko
      Erregelamendu Orokorra) indargabetzen duena, eta abenduaren 5eko 3/2018 Lege Organikoa, Datu Pertsonalak Babesteari eta Eskubide Digitalak Bermatzeari
      buruzkoa, izango dute babesa.

ORDU OSAGARRIEN ITUNA

Ordu osagarritzat hartuko dira lanaldi partzialeko kontratuan itundutako ordu arruntei gehitutako orduak, honako arau hauen arabera:

a) [COMPLETAR] Ordu osagarriak egiteko eskatu ahal izateko, enpresaburuak berariaz adostu beharko du langilearekin.

b) [COMPLETAR] Ordu osagarriei buruzko ituna lanaldi partzialeko kontratua egiten den unean edo ondoren adostu ahal izango da, baina, nolanahi ere, kontratuari buruzko itun
     espezifikoa izango da.

c) [COMPLETAR] Ituna idatziz formalizatuko da nahitaez.

d) [COMPLETAR] Ordu osagarriei buruzko itun bat egin ahal izango da soilik lanaldi partzialeko kontratuen kasuan, baldin eta urteko zenbaketan astean gutxienez hamar orduko
     lanaldia badute.

e) [COMPLETAR] Ordu osagarrien itunak enpresaburuak egin beharreko ordu osagarrien kopurua jaso beharko du.

f) [COMPLETAR] Hitzartutako ordu osagarrien kopurua ezin izango da kontratuaren xede diren ohiko lanorduen % 30 baino handiagoa izan.

g) [COMPLETAR] Hitzarmen kolektiboek gehieneko beste ehuneko bat ezarri ahal izango dute. Ehuneko hori ezin izango da, inola ere, kontratatutako ordu arrunten % 30 baino
     txikiagoa izan, ezta % 60 baino handiagoa ere.

h) [COMPLETAR] Langileak itundutako ordu osagarriak egiteko eguna eta ordua jakin beharko ditu, gutxienez hiru egun lehenago jakinarazita, salbu eta hitzarmenak aurreabisu-epe
     laburragoa ezartzen badu.

i) [COMPLETAR] Ordu osagarrien ituna indarrik gabe geratu ahal izango da langileak uko egiten badio, hamabost egun lehenago jakinaraziz, hitzarmena egin zenetik urtebete igaro
     ondoren, honako egoera hauetakoren bat gertatzen denean:

     - Langileen Estatutuaren Legearen testu bategina onartzen duen urriaren 23ko 2/2015 Legegintzako Errege Dekretuaren 37.6 artikuluan (legezko zaintzagatiko
     lanaldi-murrizketa) adierazitako familia-erantzukizunei erantzutea.

     - Prestakuntza-beharrengatik, betiere ordutegi-bateraezintasuna egiaztatzen bada.

     - Lanaldi partzialeko beste kontratu batekin bateraezintasuna.

j) [COMPLETAR] Ordu osagarrien ituna eta ordu horiek egiteko baldintzak aurreko letretan aurreikusitako arauen mende egongo dira. Arau horiek betetzen ez badira, langileak ordu
     osagarriak egiteari uko egitea, nahiz eta ordu horiek itundu, ez da laneko jokabide zehagarria izango.

k) [COMPLETAR] Ordu osagarrien itunari kalterik egin gabe, iraupen mugagabeko lanaldi partzialeko kontratuetan, urteko zenbaketan astean gutxienez hamar orduko lanaldia
     badute, enpresaburuak edozein unetan eskaini ahal izango dio langileari borondatez onartutako ordu osagarriak egiteko. Ordu osagarri horien kopurua ezin izango
     da izan kontratuaren xede diren ordu arrunten % 15 baino handiagoa, eta hitzarmen kolektibo bidez % 30era luza daiteke. Langileak ordu horiek egiteari uko
     egitea ez da laneko jokabide zehagarria izango.

     Ordu osagarri horiek ez dira zenbatuko e) letran ezarritako itundutako ordu osagarrien ehunekoen ondorioetarako.

l) [COMPLETAR] Lanaldi partzialeko langileen lanaldia egunez egun erregistratuko da, eta hilero zenbatuko da. Horretarako, hilabete bakoitzean egindako ordu guztien
     laburpenaren kopia emango zaio langileari, soldaten ordainagiriarekin batera, ordu arruntak zein osagarriak.

     Enpresaburuak gutxienez lau urtez gorde beharko ditu lanaldi-erregistroen hileko laburpenak.

     Erregistratzeko betebehar horiek betetzen ez badira, kontratua lanaldi osokoa dela ulertuko da, salbu eta zerbitzuak partzialak direla egiaztatzen duen kontrako
     frogarik badago.

m) [COMPLETAR] Ordu osagarriak egiteko, beti errespetatu beharko dira Langileen Estatutuaren Legearen teX1 Bategina onartzen duen urriaren 23ko 2/2015 Legegintzako Errege
     Dekretuan, 34. artikuluan, lanaldiari eta atsedenaldiei dagokienez ezarritako mugak.

                                        GARRANTZITSUA: [COMPLETAR]

Jatorrizko formularioa babestuta sortzen da, betetzen den bitartean aldaketarik gerta ez dadin.

Hori
        amaitutakoan, dokumentu berri bat sortu behar da, sinadura elektronikorako soilik,
         PDF inprimagailuan inprimatuta, “Microsoft Print to PDF” inprimagailua erabilita.

                  Dokumentu berri horrek ez du segurtasun-murrizketarik izango,
              eta esku hartzen duten pertsonek elektronikoki sinatu ahal izango dute;
              sinadura elektronikoak berak bermatuko du dokumentuaren osotasuna.

                                   Generar PDF para firma

                   Dokumentu hau bitarteko elektronikoen bidez sinatzen ez bada
betetako orri guztiak ezkerreko marjinan sinatu beharko dira, segurtasun juridiko handiagoa izateko.

════════════════════════════════════════════════════════════════════════
