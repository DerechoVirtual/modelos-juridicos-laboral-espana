---
name: prorroga-contrato-trabajo-acogida-real-decreto-35
description: "Redacta el escrito «Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en euskera)» (formulario 35 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en euskera)

> Formulario 0035 del plugin **Contratación laboral** · revisado el 17-11-2026.

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

- [ ] Otros 41 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…-KONTRATUAREN LUZAPENAREN JAKINARAZPENA:»; «…AK LUZAPENAREN XEDE DEN KONTRATU-EREDUA:»; «…ERREGE DEKRETUARI ATXIKIA:»; «…ENPRESAREN DATUAK IFK/IFZ/AIZ:»; «…JAUNA/ANDREA»; «…JAUNA/ANDREA [COMPLETAR] IFZ/AIZ:»; «…IFZ/AIZ: [COMPLETAR] KONTZEPTUA:»; «…ENPRESAREN EDO SOZIETATEAREN IZENA:»; «…EGOITZA SOZIALA:»; «…EGOITZA SOZIALA: [COMPLETAR] UDALERRIA:»; «…UDALERRIA: [COMPLETAR] POSTA-KODE»; «…POSTA-KODE [COMPLETAR] HERRIALDEA:»; …

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

### Formulario 0035 · Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en euskera)

- Año del modelo: 2024
- Revisión 17-11-2026: 21 casillas del modelo oficial marcadas en blanco; 6 llamadas a nota sin texto retiradas; 19 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

LAN-KONTRATUAREN LUZAPENAREN JAKINARAZPENA: [COMPLETAR]

KONTRATUAREN DATUAK
LUZAPENAREN XEDE DEN KONTRATU-EREDUA: [COMPLETAR]

ERREGE DEKRETUARI ATXIKIA: [COMPLETAR]

ENPRESAREN DATUAK
IFK/IFZ/AIZ: [COMPLETAR]

JAUNA/ANDREA [COMPLETAR] IFZ/AIZ: [COMPLETAR]

KONTZEPTUA: [COMPLETAR]

ENPRESAREN EDO SOZIETATEAREN IZENA: [COMPLETAR]

EGOITZA SOZIALA: [COMPLETAR]

UDALERRIA: [COMPLETAR]

POSTA-KODE [COMPLETAR] HERRIALDEA: [COMPLETAR]

KOTIZAZIO KONTUAREN DATUAK
ARAUBIDEA [COMPLETAR] KOTIZAZIO-KONTUAREN KODEA: [COMPLETAR]

JARDUERA EKONOMIKOA: [COMPLETAR]

LANTOKIAREN DATUAK
UDALERRIA: [COMPLETAR]

POSTA-KODE [COMPLETAR] HERRIALDEA: [COMPLETAR]

LANGILEAREN DATUAK
JAUNA/ANDREA [COMPLETAR] IFZ/AIZ: [COMPLETAR]

JAIOTEGUNA (ee/hh/uuuu) [COMPLETAR] GIZARTE SEGURA. ZK. NAZIONALITATEA: [COMPLETAR]

HEZKUNTZA MAILA: [COMPLETAR]

HELBIDEAREN UDALERRIA: [COMPLETAR]

POSTA-KODE [COMPLETAR] HELBIDEAREN HERRIALDEA: [COMPLETAR]

LEGE-LAGUNTZARI BURUZKO DATUAK (HALA BADAGOKIO)
JAUNA/ANDREA [COMPLETAR] IFZ/AIZ: [COMPLETAR]

GISA: [COMPLETAR]

 Zuzendaria, kudeatzailea, etab.
 Aita, ama, tutorea edo ardurapean duen pertsona edo erakundea.

                                                                  KOMUNIKATZEN

                                                                                                                           Enplegu Zerbitzu Publikoari
                                    hilabeteko [COMPLETAR] luzapena egitea erabaki dute, [COMPLETAR] arte.
Kontratua [COMPLETAR] sinatu zen, eta [COMPLETAR] hilabeteko hasierako iraupena izan zuen. Lehen aipatutako alderdiek
sinatu zuten, eta [COMPLETAR] erregistratu zen
Enplegu Zerbitzu Publikoan, [COMPLETAR] zenbakiarekin. Hasierako kontratuaren metatutako denbora gehi
                                                                                                                                   luzapena (k) dira.

                                                                                  (e)n, [COMPLETAR] (e)ko [COMPLETAR] ren [COMPLETAR] (e)(a)n

                         Langilea [COMPLETAR] Enpresaren ordezkaria [COMPLETAR] Adingabearen legezko ordezkaria,
                                                                                                                       hala badagokio

DATUEN BABESA. - Eredu honetan jasotako datuek Europako Parlamentuaren 2016ko apirilaren 27ko 2016/679 (EB) Erregelamendutik eta
abenduaren 5eko 3/2018 Lege Organikotik eratorritako babesa izango dute.

 Lehena, bigarrena, hirugarrena, etab.

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
