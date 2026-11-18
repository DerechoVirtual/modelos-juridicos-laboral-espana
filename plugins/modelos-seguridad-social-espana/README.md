# Incapacidad, jubilación y accidentes de trabajo · España

> Plugin de Claude Code `modelos-seguridad-social-espana` · **37 formularios** · área: Laboral (incluye 1 formulario de Procesal, marcado «(Procesal)») · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para prestaciones y contingencias: demandas de reconocimiento de prestaciones, incapacidad permanente, accidente de trabajo y sus indemnizaciones, jubilación (también parcial), complemento de maternidad, cese de actividad e ingreso mínimo vital.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 37 está al final):

- **Cartas y comunicaciones a la plantilla** (3). Por ejemplo: Respuesta de la empresa a la petición de jubilación parcial; Pedir jubilación parcial a la empresa; Imposibilidad de embargar salarios: aviso al INSS.
- **Demandas, papeletas y reclamaciones previas** (23). Por ejemplo: Demanda a la Mutua por cese de autónomos tras la entrada de migrantes en Ceuta (julio 2026); Demanda a la Mutua por cese de actividad de autónomos por incendios forestales; Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19.
- **Recursos** (2). Por ejemplo: Suplicación para elevar la incapacidad permanente de parcial a total; Suplicación para elevar la incapacidad permanente de total a absoluta.
- **Escritos y solicitudes** (3). Por ejemplo: Pedir suspensión del contrato por incendios forestales; Pedir cambio de puesto por embarazo o lactancia; Certificación negativa de descubiertos de la subcontratista: solicitud a la Tesorería.
- **Documentos, certificados y modelos oficiales** (5). Por ejemplo: Certificado del club deportivo sobre periodos de actividad como deportista profesional; Certificado de ministro de culto evangélico y tiempo de actividad en España; Certificado de la federación deportiva sobre periodos de actividad como deportista profesional.
- **Otros** (1). Por ejemplo: Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Demanda de incapacidad permanente»
   - «Papeleta de conciliación para reclamar los daños de un accidente de trabajo»
   - «Reclamación previa contra la denegación del ingreso mínimo vital»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-seguridad-social-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-seguridad-social-espana:certificado-club-deportivo-sobre-periodos-actividad-como-6`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él.
   Todos los datos jurídicos del escrito (artículos vigentes, sentencias con su ECLI, convenios, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las correcciones y avisos de la revisión del 17-11-2026 (reformas legales, órganos, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el escrito; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te indica el plazo y ante quién se presenta, y te entrega el escrito en Word con un resumen de lo que queda pendiente.

El resultado es un borrador para que lo revise un profesional antes de presentarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 4.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-seguridad-social-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-seguridad-social-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-seguridad-social-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-seguridad-social-espana:<skill>`.

### Cartas y comunicaciones a la plantilla (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 149 | Respuesta de la empresa a la petición de jubilación parcial | 2021 | `respuesta-empresa-peticion-jubilacion-parcial-149` |
| 150 | Pedir jubilación parcial a la empresa | 2021 | `pedir-jubilacion-parcial-empresa-150` |
| 170 | Imposibilidad de embargar salarios: aviso al INSS | 2020 | `imposibilidad-embargar-salarios-aviso-inss-170` |

### Demandas, papeletas y reclamaciones previas (23)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 11 | Demanda a la Mutua por cese de autónomos tras la entrada de migrantes en Ceuta (julio 2026) | 2026 | `demanda-mutua-cese-autonomos-tras-entrada-migrantes-11` |
| 12 | Demanda a la Mutua por cese de actividad de autónomos por incendios forestales | 2026 | `demanda-mutua-cese-actividad-autonomos-incendios-12` |
| 16 | Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19 | 2025 | `demanda-inss-contra-devolver-prestacion-cese-autonomos-16` |
| 25 | Demanda de reconocimiento de accidente de trabajo por la DANA (28 octubre a 4 noviembre de 2024) | 2024 | `demanda-reconocimiento-accidente-trabajo-dana-28-octubre-25` |
| 26 | Demanda a la Mutua por cese de actividad de autónomos por la DANA (28 octubre a 4 noviembre de 2024) | 2024 | `demanda-mutua-cese-actividad-autonomos-dana-28-octubre-4-26` |
| 27 | Demanda a la Mutua por prestación de cese de actividad de autónomos | 2024 | `demanda-mutua-prestacion-cese-actividad-autonomos-27` |
| 121 | Incapacidad permanente: demanda genérica | 2022 | `incapacidad-permanente-demanda-generica-121` |
| 139 | Demanda por efectos económicos de la incapacidad temporal tras un proceso anterior | 2022 | `demanda-efectos-economicos-incapacidad-temporal-tras-139` |
| 143 | Demanda por complemento de maternidad en pensión de jubilación contributiva | 2022 | `demanda-complemento-maternidad-pension-jubilacion-143` |
| 151 | Muerte por amianto: demanda de responsabilidad contra la empresa | 2021 | `muerte-amianto-demanda-responsabilidad-contra-empresa-151` |
| 154 | Ingreso mínimo vital denegado: demanda al INSS | 2021 | `ingreso-minimo-vital-denegado-demanda-inss-154` |
| 155 | Ingreso mínimo vital denegado: reclamación previa | 2021 | `ingreso-minimo-vital-denegado-reclamacion-previa-155` |
| 190 | Demanda de la empresa contra la responsabilidad por pensión de jubilación en contrato de relevo | 2020 | `demanda-empresa-contra-responsabilidad-pension-190` |
| 235 | Daños y perjuicios por accidente de trabajo: papeleta de conciliación | 2019 | `danos-perjuicios-accidente-trabajo-papeleta-conciliacion-235` |
| 259 | Riesgo durante la lactancia natural: demanda contra la Mutua | 2011 | `riesgo-durante-lactancia-natural-demanda-contra-mutua-259` |
| 307 | Prestación por maternidad: demanda de reclamación | 2011 | `prestacion-maternidad-demanda-reclamacion-307` |
| 380 | Impugnar la prestación por desempleo: demanda | 2008 | `impugnar-prestacion-desempleo-demanda-380` |
| 382 | Accidente de trabajo por falta de seguridad en contrata o subcontrata: demanda de indemnización | 2013 | `accidente-trabajo-falta-seguridad-contrata-subcontrata-382` |
| 383 | Determinar la contingencia de la incapacidad temporal: demanda | 2015 | `determinar-contingencia-incapacidad-temporal-demanda-383` |
| 390 | Pensión de viudedad del cónyuge separado judicialmente: demanda | 2015 | `pension-viudedad-conyuge-separado-judicialmente-demanda-390` |
| 409 | Autónomo: demanda de prestación económica por incapacidad | 2015 | `autonomo-demanda-prestacion-economica-incapacidad-409` |
| 410 | Gastos médicos por asistencia urgente y vital: demanda de reintegro (modelo 1) | 2015 | `gastos-medicos-asistencia-urgente-vital-demanda-410` |
| 202 (Procesal) | Prestaciones de la Seguridad Social: demanda de reconocimiento | 2020 | `prestaciones-seguridad-social-demanda-reconocimiento-p202` |

### Recursos (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 166 | Suplicación para elevar la incapacidad permanente de parcial a total | 2021 | `suplicacion-elevar-incapacidad-permanente-parcial-total-166` |
| 167 | Suplicación para elevar la incapacidad permanente de total a absoluta | 2021 | `suplicacion-elevar-incapacidad-permanente-total-absoluta-167` |

### Escritos y solicitudes (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 15 | Pedir suspensión del contrato por incendios forestales | 2026 | `pedir-suspension-contrato-incendios-forestales-15` |
| 218 | Pedir cambio de puesto por embarazo o lactancia | 2019 | `pedir-cambio-puesto-embarazo-lactancia-218` |
| 384 | Certificación negativa de descubiertos de la subcontratista: solicitud a la Tesorería | 2003 | `certificacion-negativa-descubiertos-subcontratista-384` |

### Documentos, certificados y modelos oficiales (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 6 | Certificado del club deportivo sobre periodos de actividad como deportista profesional | 2026 | `certificado-club-deportivo-sobre-periodos-actividad-como-6` |
| 7 | Certificado de ministro de culto evangélico y tiempo de actividad en España | 2026 | `certificado-ministro-culto-evangelico-tiempo-actividad-7` |
| 8 | Certificado de la federación deportiva sobre periodos de actividad como deportista profesional | 2026 | `certificado-federacion-deportiva-sobre-periodos-8` |
| 256 | Convenios bilaterales de Seguridad Social de España con otros países | 2018 | `convenios-bilaterales-seguridad-social-espana-otros-256` |
| 355 | Aptitud tras el reconocimiento médico: declaración | 2013 | `aptitud-tras-reconocimiento-medico-declaracion-355` |

### Otros (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 13 | Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales | 2026 | `respuesta-empresa-suspension-permiso-fallecimiento-13` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
