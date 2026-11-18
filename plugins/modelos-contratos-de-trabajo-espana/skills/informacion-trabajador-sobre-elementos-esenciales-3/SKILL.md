---
name: informacion-trabajador-sobre-elementos-esenciales-3
description: "Redacta el escrito «Información al trabajador sobre los elementos esenciales del contrato (en euskera)» (formulario 3 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información al trabajador sobre los elementos esenciales del contrato (en euskera)

> Formulario 0003 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] Otros 56 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…UEI BURUZKO INFORMAZIO-AGIRIAREN EREDUA:»; «…N IDENTITATEA LANGILEAREN IZEN-ABIZENAK:»; «…LANGILEAREN IFZ/AIZ:»; «…ENPRESAREN IZENA EDO IZEN SOZIALA:»; «…ENPRESAREN IFK/IFZ:»; «…ENPRESAREN HELBIDE SOZIALA:»; «…ZERBITZUA EMATEN DEN OHIKO LANTOKIA:»; «…ANEKO LANGILEA ATXIKITA DAGOEN LANTOKIA:»; «…I ZIRKUNSTANTZIA HORIEK GERTATZEN DIREN:»; «…B) LAN-HARREMANA LAN-HARREMAN MOTA:»; «…TA (ee/hh/uuuu) LAN-HARREMANAREN EDUKIA:»; «…ALDI BATERAKO LAN-HARREMANETAN:»; …

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

### Formulario 0003 · Información al trabajador sobre los elementos esenciales del contrato (en euskera)

- Año del modelo: 2026
- Revisión 17-11-2026: 42 casillas del modelo oficial marcadas en blanco; 12 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Documento informativo del RD 723/2026 (BOE-A-2026-19200, en vigor el 5-10-2026, deroga el RD 1659/1998): comprobar que recoge todos los extremos del art. 3.2 a)-q), incluidos periodo de prueba, formación, ETT, sistemas algorítmicos, plan de igualdad y protocolo de acoso, medidas LGTBI, mejoras voluntarias y planes de pensiones y supuestos de modificación.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

LAU ASTETIK GORAKO LAN-HARREMANEI APLIKA DAKIEKEEN LAN-KONTRATUAREN FUNTSEZKO
ELEMENTUEI BURUZKO INFORMAZIO-AGIRIAREN EREDUA: [COMPLETAR]

1. INFORMAZIO OROKORRAL

A) LAN-KONTRATUA SINATZEN DUTEN ALDERDIEN IDENTITATEA
LANGILEAREN IZEN-ABIZENAK: [COMPLETAR]

LANGILEAREN IFZ/AIZ: [COMPLETAR]

ENPRESAREN IZENA EDO IZEN SOZIALA: [COMPLETAR]

ENPRESAREN IFK/IFZ: [COMPLETAR]

ENPRESAREN HELBIDE SOZIALA: [COMPLETAR]

ZERBITZUA EMATEN DEN OHIKO LANTOKIA: [COMPLETAR]

URRUTIKO LANEKO LANGILEA ATXIKITA DAGOEN LANTOKIA: [COMPLETAR]

ZENTRO IBILTARIAK, HAINBAT LANTOKI EDO ZERBITZUA EMATEKO LEKUA LIBREKI ZEHAZTEA. ADIERAZI ZIRKUNSTANTZIA HORIEK GERTATZEN DIREN: [COMPLETAR]

B) LAN-HARREMANA
LAN-HARREMAN MOTA: [COMPLETAR]

LAN-HARREMANAREN HASIERA-DATA (ee/hh/uuuu)

LAN-HARREMANAREN EDUKIA: [COMPLETAR]

ALDI BATERAKO LAN-HARREMANETAN: [COMPLETAR]
KONTRATUAREN AURREIKUSITAKO IRAUPENA [COMPLETAR] LAN-HARREMANAREN AMAIERA-DATA (ee/hh/uuuu): [COMPLETAR]

KONTRATAZIOA GAITZEKO ARRAZOIA: [COMPLETAR]

KONTRATAZIOA JUSTIFIKATZEN DUTEN INGURUABAR ZEHATZAK: [COMPLETAR]

KONTRATUAREN AURREIKUSITAKO IRAUPENAREKIKO LOTURA: [COMPLETAR]

C) LANPOSTUA
 KATEGORIA EDO LANBIDE-TALDEA: [COMPLETAR]

 LANPOSTUAREN KARAKTERIZAZIOA EDO DESKRIBAPEN LABURRA, LANAREN EDUKI ESPEZIFIKOA BEHAR BEZAIN ZEHATZ EZAGUTZEKO MODUAN: [COMPLETAR]

D) SOLDATA
 OINARRIZKO SOLDATAREN ZENBATEKOA (*): [COMPLETAR]

 SOLDATA-OSAGARRIEN ZENBATEKOA (*): [COMPLETAR]

 ALDIZKAKOTASUNA (*): [COMPLETAR]

 ORDAINTZEKO MODUA (*): [COMPLETAR]

 SOLDATA-KONTZEPTU ALDAKORRAK KALKULATZEKO MODUA: [COMPLETAR]

 SOLDATA-KONTZEPTU ALDAKORRAK JASOTZEKO IRIZPIDEAK: [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

E) LAN-DENBORA
 LANALDI ARRUNTAREN IRAUPENA ETA ORDU-BANAKETA (*): [COMPLETAR]

 GAUEKO EDO TXANDAKAKO LANA (*): [COMPLETAR]

 TXANDAK ETA LANALDIAREN IRAUPENA ETA BANAKETA ALDATZEKO PROZEDURA (*): [COMPLETAR]

 APARTEKO ORDUEI ETA HORIEN ORDAINKETARI BURUZKO AKORDIOAK (*): [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

 OPORREN IRAUPENA ETA OPORRAK HARTZEKO ALDIA EDO ALDIAK FINKATZEKO PROZEDURAK (*): [COMPLETAR]

 LANALDIAREN BANAKETA IRREGULARRERAKO SISTEMA: [COMPLETAR]

 ATAZAK HASTEKO ETA BERTAN BEHERA UZTEKO AURREABISU-ALDIAK: [COMPLETAR]

 ALDIZKAKO KONTRATU MUGAGABE FINKOETAN AURREIKUSITAKO JARDUERA-ALDIAK ETA JARDUERARIK EZA: [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

F) PROBALDIA, HITZARTZEN DENEAN
 PROBALDIAREN IRAUPENA (*): [COMPLETAR]

 PROBAREN XEDE DIREN ESPERIENTZIAK EGITEKO ENPRESAK ETA LANGILEAK DITUZTEN BETEBEHARREI BURUZKO INFORMAZIOA (*): [COMPLETAR]

G) PRESTAKUNTZA
 ENPRESAK EMAN BEHARREKO PRESTAKUNTZA, LANPOSTUA BETETZEKO NAHITAEZKOA BADA (*): [COMPLETAR]

H) ALDI BATERAKO LANEKO ENPRESAK, ALDI BATERAKO LANEKO ENPRESEK LAGATAKO LANGILEEN
KASUAN
 ENPRESA ERABILTZAILEAREN NORTASUNA ETA LANGILEAK LAGATZEKO KONTRATU BAKOITZA EGITEKO GAITZEN DUEN ARRAZOIA: [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

I) LAN-BALDINTZAK FINKATZEAREKIN, ALDATZEAREKIN EDO ALDATZEAREKIN LOTUTAKO ERABAKIAK
HARTZEKO SISTEMA ALGORITMIKOAK EDO AUTOMATIZATUAK EGOTEA: [COMPLETAR]

J) ENPRESARI APLIKA DAKIOKEEN BERDINTASUN-PLANA IDENTIFIKATZEA, HALAKORIK BADAGO, ETA
ENPRESAN SEXU-JAZARPENA ETA SEXUAN OINARRITUTAKO JAZARPENA EGITEKO ENPRESA-POLITIKA ETA
PROTOKOLOA EZARTZEA: [COMPLETAR]

K) LGTBI PERTSONEN BENETAKO BERDINTASUN ERAGINKORRA LORTZEKO NEURRIAK ETA BALIABIDEAK,
HALAKORIK IZANEZ GERO: [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

L) KONTRATUA AMAITZEKO PROZEDURA, BALDINTZA FORMALAK ETA AURREABISU-EPEEN IRAUPENA
BARNE (*): [COMPLETAR]

M) LAN-HARREMANARI APLIKATU BEHARREKO HITZARMENA EDO HITZARMEN KOLEKTIBOAK

N) ENPRESAN JARDUTEN DUEN GIZARTE SEGURANTZAREN KUDEAKETAN LANKIDETZAN ARITZEKO
SISTEMA (*): [COMPLETAR]

O) LAN-HARREMANAREN EDUKIA, LANBIDE-KATEGORIA EDO -TALDEA, SOLDATA ETA LAN-DENBORA ALDAT-
ZEKO JARRAITU BEHARREKO KASUAK ETA PROZEDURA: [COMPLETAR]

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

 2. ATZERRIAN ZERBITZUAK EMATEN DIREN KASUETARAKO INFORMAZIO GEHIGARRIA. ATZERRIKO
 LAN-ALDI BAKOITZAREN IRAUPENA ONDOZ ONDOKO LAU ASTETIK GORAKOA DENEAN BAKARRIK
 APLIKA DAITEKE

 A) LANA EGIN BEHAR DEN HERRIALDEA EDO HERRIALDEAK

 B) ATZERRIAN EGINGO DEN LANAREN IRAUPENA

 C) SOLDATA LEGEZ ORDAINDUKO DEN DIRUA (*)

 D) DIRUZKO EDO GAUZAZKO ORDAINSARIAK, BAI ETA GASTUAK, BIDAIA-GASTUAK, DIETAK ETA ATZERRIAN ZERBITZUAK EMATEAREN ONDORIOZKO
 ABANTAILAK ERE: [COMPLETAR]

 E) LANGILEAREN ABERRIRATZEA ETA BALDINTZAK AURREIKUSITA BADAUDE

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

 3. EUROPAR BATASUNEKO ESTATU KIDEETAKO LURRALDERA EDO NAZIOZ GAINDIKO ZERBITZUAK
 EMATEAREN ESPARRUAN EUROPAKO ESPARRU EKONOMIKOARI BURUZKO AKORDIOA SINATU DUTEN
 ESTATUETAKO LURRALDERA LEKUALDATUTAKO LANGILE BATEN KASUAN

 A) HARRERAKO ESTATU KIDEKO LEGEDI APLIKAGARRIAREN ARABERA ESKUBIDEAK DITUEN ORDAINSARIAK (*)

 B) BIDAIA-, OSTATU-, MANTENU- ETA, EGOTEKOTAN, BIDAIA-GASTUAK ITZULTZEARI BURUZKO XEDAPENA

 C) HARRERAKO ESTATU KIDEAK EDO KIDEEK EGINDAKO LEKUALDATZEARI BURUZKO ESTATU MAILAKO WEB ATARI OFIZIAL BAKARRERAKO ESTEKA

                                                                                      (e)n, [COMPLETAR] (e)ko [COMPLETAR] ren [COMPLETAR] (e)(a)n

                                                                      Enpresaren ordezkaria

(*) [COMPLETAR] Informazio hori legezko edo erregelamenduzko xedapenei edo xedapen horiek arautzen dituzten hitzarmen kolektiboei egindako erreferentzia batetik erator daiteke
      erreferentzia hori beharrezkoa bada eta aplikatu beharreko xedapenak argi eta garbi identifikatzeko aukera ematen badu.

                                        GARRANTZITSUA: [COMPLETAR]

Jatorrizko formularioa babestuta sortzen da, betetzen den bitartean aldaketarik gerta ez dadin.

Hori
        amaitutakoan, dokumentu berri bat sortu behar da, sinadura elektronikorako soilik,
         PDF inprimagailuan inprimatuta, “Microsoft Print to PDF” inprimagailua erabilita.

                  Dokumentu berri horrek ez du segurtasun-murrizketarik izango,
              eta esku hartzen duten pertsonek elektronikoki sinatu ahal izango dute;
              sinadura elektronikoak berak bermatuko du dokumentuaren osotasuna.

                                 Sortu sinadurarako PDFa

                   Dokumentu hau bitarteko elektronikoen bidez sinatzen ez bada
betetako orri guztiak ezkerreko marjinan sinatu beharko dira, segurtasun juridiko handiagoa izateko.

       Dokumentu hori sinatu ondoren, langilearen eskura jarriko da, formatu elektronikoan
                     edo paperean entregatuz, baldin eta eskuragarri badago,
 gorde eta inprimatu badaiteke eta enpresak transmisioaren edo harreraren froga gordetzen badu.

════════════════════════════════════════════════════════════════════════
