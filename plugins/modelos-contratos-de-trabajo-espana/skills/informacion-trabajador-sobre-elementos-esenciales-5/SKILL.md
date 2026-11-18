---
name: informacion-trabajador-sobre-elementos-esenciales-5
description: "Redacta el escrito «Información al trabajador sobre los elementos esenciales del contrato (en catalán)» (formulario 5 de contratación laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Información al trabajador sobre los elementos esenciales del contrato (en catalán)

> Formulario 0005 del plugin **Contratación laboral** · revisado el 17-11-2026.

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
- [ ] Otros 56 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…LS DE DURADA SUPERIOR A QUATRE SETMANES:»; «…OM I COGNOMS DE LA PERSONA TREBALLADORA:»; «…NIF/NIE DE LA PERSONA TREBALLADORA:»; «…NOM O RAÓ SOCIAL DE L’EMPRESA:»; «…CIF/NIF EMPRESA:»; «…DOMICILI SOCIAL DE L’EMPRESA:»; «…TREBALL HABITUAL ON ES PRESTA EL SERVEI:»; «…ONA TREBALLADORA EN TREBALL A DISTÀNCIA:»; «…AR SI CONCORREN AQUESTES CIRCUMSTÀNCIES:»; «…ELACIÓ LABORAL TIPUS DE RELACIÓ LABORAL:»; «…m/aaaa) CONTINGUT DE LA RELACIÓ LABORAL:»; «…EN RELACIONS LABORALS TEMPORALS:»; …

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

### Formulario 0005 · Información al trabajador sobre los elementos esenciales del contrato (en catalán)

- Año del modelo: 2026
- Revisión 17-11-2026: 43 casillas del modelo oficial marcadas en blanco; 12 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco
- Avisos de la revisión: Documento informativo del RD 723/2026 (BOE-A-2026-19200, en vigor el 5-10-2026, deroga el RD 1659/1998): comprobar que recoge todos los extremos del art. 3.2 a)-q), incluidos periodo de prueba, formación, ETT, sistemas algorítmicos, plan de igualdad y protocolo de acoso, medidas LGTBI, mejoras voluntarias y planes de pensiones y supuestos de modificación.

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

MODEL DE DOCUMENT INFORMATIU SOBRE ELS ELEMENTS ESSENCIALS DEL CONTRACTE DE TREBALL
APLICABLE A LES RELACIONS LABORALS DE DURADA SUPERIOR A QUATRE SETMANES: [COMPLETAR]

1. INFORMACIÓ GENERAL

A) IDENTITAT DE LES PARTS QUE SUBSCRIUEN EL CONTRACTE DE TREBALL
NOM I COGNOMS DE LA PERSONA TREBALLADORA: [COMPLETAR]

NIF/NIE DE LA PERSONA TREBALLADORA: [COMPLETAR]

NOM O RAÓ SOCIAL DE L’EMPRESA: [COMPLETAR]

CIF/NIF EMPRESA: [COMPLETAR]

DOMICILI SOCIAL DE L’EMPRESA: [COMPLETAR]

CENTRE DE TREBALL HABITUAL ON ES PRESTA EL SERVEI: [COMPLETAR]

CENTRE DE TREBALL AL QUAL ESTÀ ADSCRITA LA PERSONA TREBALLADORA EN TREBALL A DISTÀNCIA: [COMPLETAR]

CENTRES ITINERANTS, DIFERENTS CENTRES DE TREBALL O DETERMINACIÓ LLIURE DEL LLOC DE PRESTACIÓ DEL SERVEI. INDICAR SI CONCORREN
AQUESTES CIRCUMSTÀNCIES: [COMPLETAR]

B) RELACIÓ LABORAL
TIPUS DE RELACIÓ LABORAL: [COMPLETAR]

DATA INICI RELACIÓ LABORAL (dd/mm/aaaa)

CONTINGUT DE LA RELACIÓ LABORAL: [COMPLETAR]

EN RELACIONS LABORALS TEMPORALS: [COMPLETAR]
DURADA PREVISTA DEL CONTRACTE [COMPLETAR] DATA FI RELACIÓ LABORAL (dd/mm/aaaa): [COMPLETAR]

CAUSA HABILITANT DE LA CONTRACTACIÓ: [COMPLETAR]

CIRCUMSTÀNCIES CONCRETES QUE JUSTIFIQUEN LA CONTRACTACIÓ: [COMPLETAR]

CONNEXIÓ AMB LA DURADA PREVISTA DEL CONTRACTE: [COMPLETAR]

C) LLOC DE TREBALL
 CATEGORIA O GRUP PROFESSIONAL: [COMPLETAR]

 CARACTERITZACIÓ O DESCRIPCIÓ RESUMIDA DEL LLOC DE TREBALL, EN TERMES QUE PERMETIN CONÈIXER AMB SUFICIENT PRECISIÓ EL CONTINGUT
 ESPECÍFIC DEL TREBALL: [COMPLETAR]

D) SALARI
 QUANTIA DEL SALARI BASE (*): [COMPLETAR]

 QUANTIA DELS COMPLEMENTS SALARIALS (*): [COMPLETAR]

 PERIODICITAT (*): [COMPLETAR]

 MÈTODE PAGAMENT (*): [COMPLETAR]

 MODE DE CÀLCUL DELS CONCEPTES SALARIALS VARIABLES: [COMPLETAR]

 CRITERIS QUE DETERMINEN LA PERCEPCIÓ DELS CONCEPTES SALARIALS VARIABLES: [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

E) TEMPS DE TREBALL
 DURADA I DISTRIBUCIÓ HORÀRIA DE LA JORNADA ORDINÀRIA DE TREBALL (*): [COMPLETAR]

 TREBALL NOCTURN O A TORNS (*): [COMPLETAR]

 PROCEDIMENT PER A LA MODIFICACIÓ DELS TORNS I LA DURADA I DISTRIBUCIÓ DE LA JORNADA (*): [COMPLETAR]

 ACORDS RELATIUS A HORES EXTRES I LA SEVA RETRIBUCIÓ (*): [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

 DURADA DE LES VACANCES I PROCEDIMENTS PER A FIXAR EL PERÍODE O PERÍODES DEL SEU GAUDI (*): [COMPLETAR]

 SISTEMA PER A LA DISTRIBUCIÓ IRREGULAR DE JORNADA: [COMPLETAR]

 PERÍODES DE PREAVÍS PER A L’INICI I CANCEL·LACIÓ DE TASQUES: [COMPLETAR]

 PERÍODES ESTIMATS D’ACTIVITAT I INACTIVITAT EN CONTRACTES INDEFINITS FIXOS DISCONTINUS: [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

F) PERÍODE DE PROVA, QUAN ES CONCERTI
 DURADA DEL PERÍODE DE PROVA (*): [COMPLETAR]

 INFORMACIÓ RELATIVA A LES OBLIGACIONS RESPECTIVES DE L’EMPRESA I DE LA PERSONA TREBALLADORA A REALITZAR LES EXPERIÈNCIES QUE CONSTI-
 TUEIXIN L’OBJECTE DE LA PROVA (*): [COMPLETAR]

G) FORMACIÓ
 FORMACIÓ A PROPORCIONAR PER L’EMPRESA, EN EL CAS QUE SIGUI OBLIGATÒRIA PER A L’ACOMPLIMENT DEL LLOC DE TREBALL (*): [COMPLETAR]

H) EMPRESES DE TREBALL TEMPORAL, EN EL CAS DE PERSONES TREBALLADORES CEDIDES PER EMPRE-
SES DE TREBALL TEMPORAL
 IDENTITAT DE L’EMPRESA USUÀRIA I LA CAUSA QUE HABILITA A LA CELEBRACIÓ DE CADA CONTRACTE DE POSADA A DISPOSICIÓ: [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

I) EXISTÈNCIA DE SISTEMES ALGORÍTMICS O AUTOMATITZATS DE PRESA DE DECISIONS RELACIONATS AMB
A FIXACIÓ, VARIACIÓ O MODIFICACIÓ DE CONDICIONS DE TREBALL: [COMPLETAR]

J) IDENTIFICACIÓ, SI EXISTEIX, DEL PLA D’IGUALTAT APLICABLE A L’EMPRESA, EN CAS QUE ES DISPOSI,
POLÍTICA EMPRESARIAL DE CONCILIACIÓ I PROTOCOL D’ASSETJAMENT SEXUAL I PER RAÓ DE SEXE EN [COMPLETAR]
L’EMPRESA: [COMPLETAR]

K) MESURES I RECURSOS PER A ACONSEGUIR LA IGUALTAT REAL I EFECTIVA DE LES PERSONES LGTBI, EN [COMPLETAR]
CAS QUE ES DISPOSI D’ELLS: [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

L) PROCEDIMENT D’EXTINCIÓ DEL CONTRACTE, INCLOSOS ELS REQUISITS FORMALS I LA DURADA DELS
TERMINIS DE PREAVÍS (*): [COMPLETAR]

M) CONVENI O CONVENIS COL·LECTIUS APLICABLES A LA RELACIÓ LABORAL

N) SISTEMA DE COL·LABORACIÓ EN LA GESTIÓ DE LA SEGURETAT SOCIAL QUE OPERA EN L’EMPRESA (*)

O) SUPOSATS I PROCEDIMENT A SEGUIR PER A MODIFICAR EL CONTINGUT DE LA RELACIÓ LABORAL, LA
CATEGORIA O GRUP PROFESSIONAL, EL SALARI I EL TEMPS DE TREBALL: [COMPLETAR]

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

 2. INFORMACIÓ ADDICIONAL EN ELS SUPÒSITS DE PRESTACIÓ DE SERVEIS A L’ESTRANGER. APLICABLE
 SOLO SI LA DURADA DE CADA PERÍODE DE TREBALL A L’ESTRANGER DEPASSA LES QUATRE SETMANES
 CONSECUTIVES

 A) EL PAÍS O PAÏSOS EN ELS QUALS HA DE DUR-SE A TERME EL TREBALL

 B) LA DURADA DEL TREBALL QUE VAGI A PRESTAR-SE A L’ESTRANGER

 C) LA MONEDA DE CURSO LEGAL EN LA QUE SE PAGARÁ EL SALARIO (*)

 D) LES RETRIBUCIONS EN DINERS O EN ESPÈCIE, AIXÍ COM LES COMPENSACIONS PER DESPESES, DESPESES DE VIATGE, DIETES I ELS AVANTATGES
 VINCULATS A LA CIRCUMSTÀNCIA DE LA PRESTACIÓ DE SERVEIS A L’ESTRANGER: [COMPLETAR]

 E) SI ES TROBA PREVISTA LA REPATRIACIÓ DE LA PERSONA TREBALLADORA I LES SEVES CONDICIONS

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
      sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

 3. EN EL CAS D’UNA PERSONA TREBALLADORA DESPLAÇADA AL TERRITORI D’ESTATS MEMBRES DE LA
 UNIÓ EUROPEA O D’ESTATS SIGNATARIS DE L’ACORD SOBRE L’ESPAI ECONÒMIC EUROPEU EN EL MARC
 D’UNA PRESTACIÓ DE SERVEIS TRANSNACIONAL

 A) RETRIBUCIONS A LES QUALS AQUESTA TÉ DRET CONFORMEMENT A LA LEGISLACIÓ APLICABLE DE L’ESTAT MEMBRE D’ACOLLIMENT (*)

 B) DISPOSICIÓ RELATIVA AL REEMBOSSAMENT DE LES DESPESES DE VIATGE, ALLOTJAMENT, MANUTENCIÓ I, D’EXISTIR, COMPLEMENT ESPECÍFIC PER
 DESPLAÇAMENT: [COMPLETAR]

 C) ENLLAÇ AL PORTAL WEB OFICIAL ÚNIC A escala NACIONAL EN MATÈRIA DE DESPLAÇAMENT DESENVOLUPAT PER L’ESTAT O ESTATS MEMBRES D’ACOLLI-
 MENT: [COMPLETAR]

  En [LUGAR], a [DÍA] de [MES] de [AÑO].

                                                                                El/la representant
                                                                                  de l’empresa

(*) [COMPLETAR] Aquesta informació podrà derivar-se d’una referència a les disposicions legals o reglamentàries o als convenis col·lectius d’aplicació que regulin aquests extrems,
       sempre que aquesta referència sigui precisa i permeti identificar clarament les disposicions aplicables.

                                               IMPORTANT: [COMPLETAR]

       El formulari original es genera protegit per a evitar modificacions durant el seu emplenament.
        Una vegada finalitzada aquesta, ha de generar-se un nou document, destinat exclusivament
a la signatura electrònica, mitjançant la impressió a PDF utilitzant la impressora “Microsoft Print to PDF”.

                     Aquest nou document no incorporarà restriccions de seguretat
                    i podrà ser signat electrònicament per les persones intervinents,
             sent la pròpia signatura electrònica la que garantirà la integritat del document.

                                    Generar PDF per a signatura

                    En cas que aquest document no se signi per mitjans electrònics,
totes les pàgines emplenades hauran d’anar signades en el marge esquerre per a major seguretat jurídica.

        Una vegada signat aquest document, es posarà a la disposició de la persona treballadora
       mitjançant lliurament en format electrònic o en suport paper, sempre que sigui accessible,
  que es pugui emmagatzemar i imprimir i que l’empresa conservi la prova de la transmissió o recepció.

════════════════════════════════════════════════════════════════════════
