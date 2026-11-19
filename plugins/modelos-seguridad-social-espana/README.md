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

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork).
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 4.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-seguridad-social-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-seguridad-social-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-seguridad-social-espana:<skill>`). Son 37, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Cartas y comunicaciones a la plantilla (3)

- **Imposibilidad de embargar salarios: aviso al INSS** (`imposibilidad-embargar-salarios-aviso-inss-170`). Escrito dirigido al INSS para comunicar que no es posible embargar los salarios de una persona trabajadora, indicando los datos del afectado y de la representación que firma.
- **Pedir jubilación parcial a la empresa** (`pedir-jubilacion-parcial-empresa-150`). Escrito del trabajador a la empresa para solicitar la jubilación parcial, con el contrato de relevo que corresponda, dirigido a recursos humanos y adaptado a la normativa vigente.
- **Respuesta de la empresa a la petición de jubilación parcial** (`respuesta-empresa-peticion-jubilacion-parcial-149`). Carta de la empresa en respuesta a la petición de jubilación parcial de un trabajador, para aceptarla y proponer el acuerdo o para denegarla motivadamente, según la opción elegida.

### Demandas, papeletas y reclamaciones previas (23)

- **Accidente de trabajo por falta de seguridad en contrata o subcontrata: demanda de indemnización** (`accidente-trabajo-falta-seguridad-contrata-subcontrata-382`). Demanda del trabajador accidentado, o de su familia, que reclama indemnización de daños y perjuicios a las empresas de una contrata o subcontrata por falta de medidas de seguridad.
- **Autónomo: demanda de prestación económica por incapacidad** (`autonomo-demanda-prestacion-economica-incapacidad-409`). Demanda del trabajador autónomo que reclama la prestación económica por incapacidad temporal derivada de accidente laboral cuando la Mutua o la entidad gestora se la ha denegado.
- **Daños y perjuicios por accidente de trabajo: papeleta de conciliación** (`danos-perjuicios-accidente-trabajo-papeleta-conciliacion-235`). Papeleta de conciliación previa que presenta el trabajador accidentado, o su familia, para reclamar a la empresa daños y perjuicios por accidente de trabajo, antes de presentar la demanda.
- **Demanda a la Mutua por cese de actividad de autónomos por incendios forestales** (`demanda-mutua-cese-actividad-autonomos-incendios-12`). Demanda del trabajador autónomo contra la Mutua que le deniega la prestación por cese de actividad ocasionado por incendios forestales, para que se la reconozca ante el orden social.
- **Demanda a la Mutua por cese de actividad de autónomos por la DANA (28 octubre a 4 noviembre de 2024)** (`demanda-mutua-cese-actividad-autonomos-dana-28-octubre-4-26`). Demanda del trabajador autónomo contra la Mutua por denegar la prestación por cese de actividad derivada de la DANA ocurrida entre el 28 de octubre y el 4 de noviembre de 2024.
- **Demanda a la Mutua por cese de autónomos tras la entrada de migrantes en Ceuta (julio 2026)** (`demanda-mutua-cese-autonomos-tras-entrada-migrantes-11`). Demanda del trabajador autónomo contra la Mutua que le deniega la prestación extraordinaria por cese de actividad derivada de la entrada de migrantes en Ceuta en julio de 2026, ante el orden social.
- **Demanda a la Mutua por prestación de cese de actividad de autónomos** (`demanda-mutua-prestacion-cese-actividad-autonomos-27`). Demanda del trabajador autónomo contra la Mutua que le ha denegado la prestación por cese de actividad, pidiendo que se la reconozca ante la Sección de lo Social del Tribunal de Instancia.
- **Demanda al INSS contra devolver la prestación de cese de autónomos en la COVID-19** (`demanda-inss-contra-devolver-prestacion-cese-autonomos-16`). Demanda del trabajador autónomo contra el INSS que le reclama devolver la prestación de cese de actividad percibida durante la COVID-19, para impugnar el cálculo y los criterios aplicados.
- **Demanda de la empresa contra la responsabilidad por pensión de jubilación en contrato de relevo** (`demanda-empresa-contra-responsabilidad-pension-190`). Demanda de la empresa que impugna la responsabilidad que se le imputa por la pensión de jubilación derivada de un contrato de relevo que se considera incumplido.
- **Demanda de reconocimiento de accidente de trabajo por la DANA (28 octubre a 4 noviembre de 2024)** (`demanda-reconocimiento-accidente-trabajo-dana-28-octubre-25`). Demanda para que se reconozca como accidente de trabajo, a efectos de la prestación económica, la situación sufrida por la DANA entre el 28 de octubre y el 4 de noviembre de 2024, frente a la entidad que la denegó.
- **Demanda por complemento de maternidad en pensión de jubilación contributiva** (`demanda-complemento-maternidad-pension-jubilacion-143`). Demanda de la pensionista que reclama el complemento de maternidad en su pensión de jubilación contributiva, cuando el INSS se lo ha denegado, ante la Sección de lo Social del Tribunal de Instancia.
- **Demanda por efectos económicos de la incapacidad temporal tras un proceso anterior** (`demanda-efectos-economicos-incapacidad-temporal-tras-139`). Demanda de quien, tras un proceso anterior, reclama los efectos económicos de la incapacidad temporal, es decir, el pago del subsidio por los periodos de baja reconocidos, ante el orden social.
- **Determinar la contingencia de la incapacidad temporal: demanda** (`determinar-contingencia-incapacidad-temporal-demanda-383`). Demanda para que se determine si la baja por incapacidad temporal deriva de accidente de trabajo o de contingencia común, frente a la resolución del INSS o la mutua, ante el orden social.
- **Gastos médicos por asistencia urgente y vital: demanda de reintegro (modelo 1)** (`gastos-medicos-asistencia-urgente-vital-demanda-410`). Demanda para reclamar el reintegro de gastos médicos que el paciente abonó por una asistencia sanitaria urgente y vital recibida fuera del sistema público, ante el orden social.
- **Impugnar la prestación por desempleo: demanda** (`impugnar-prestacion-desempleo-demanda-380`). Demanda para impugnar la resolución sobre la prestación por desempleo, ya sea su denegación, su cuantía o su duración, y pedir que se reconozca el derecho del trabajador, ante el orden social.
- **Incapacidad permanente: demanda genérica** (`incapacidad-permanente-demanda-generica-121`). Demanda genérica en materia de incapacidad permanente, para impugnar la resolución del INSS y que se reconozca al trabajador el grado y la prestación que le corresponden, ante la Sección de lo Social.
- **Ingreso mínimo vital denegado: demanda al INSS** (`ingreso-minimo-vital-denegado-demanda-inss-154`). Demanda contra el INSS por la denegación del ingreso mínimo vital, para que se reconozca la prestación a la persona solicitante, una vez agotada la vía previa, ante la Sección de lo Social.
- **Ingreso mínimo vital denegado: reclamación previa** (`ingreso-minimo-vital-denegado-reclamacion-previa-155`). Reclamación previa que el solicitante dirige al INSS contra la resolución que le deniega el ingreso mínimo vital, como paso previo a la demanda ante el orden social.
- **Muerte por amianto: demanda de responsabilidad contra la empresa** (`muerte-amianto-demanda-responsabilidad-contra-empresa-151`). Demanda de los familiares de un trabajador fallecido por enfermedad profesional causada por el amianto, para reclamar a la empresa la responsabilidad e indemnización por daños, ante el orden social.
- **Pensión de viudedad del cónyuge separado judicialmente: demanda** (`pension-viudedad-conyuge-separado-judicialmente-demanda-390`). Demanda de quien, separado judicialmente del causante, reclama la pensión de viudedad que se le ha denegado, ante la Sección de lo Social del Tribunal de Instancia.
- **Prestaciones de la Seguridad Social: demanda de reconocimiento** (`prestaciones-seguridad-social-demanda-reconocimiento-p202`). Demanda genérica para que se reconozca una prestación de la Seguridad Social denegada por la entidad gestora, una vez presentada la reclamación previa, ante la Sección de lo Social.
- **Prestación por maternidad: demanda de reclamación** (`prestacion-maternidad-demanda-reclamacion-307`). Demanda para reclamar la prestación por nacimiento y cuidado de menor, antes llamada maternidad, cuando la entidad gestora la ha denegado, ante la Sección de lo Social del Tribunal de Instancia.
- **Riesgo durante la lactancia natural: demanda contra la Mutua** (`riesgo-durante-lactancia-natural-demanda-contra-mutua-259`). Demanda de la trabajadora contra la Mutua que le deniega la prestación por riesgo durante la lactancia natural, para que se le reconozca ante la Sección de lo Social del Tribunal de Instancia.

### Recursos (2)

- **Suplicación para elevar la incapacidad permanente de parcial a total** (`suplicacion-elevar-incapacidad-permanente-parcial-total-166`). Recurso de suplicación del demandante, ante la Sala de lo Social del TSJ, para que la incapacidad permanente reconocida como parcial se eleve a total.
- **Suplicación para elevar la incapacidad permanente de total a absoluta** (`suplicacion-elevar-incapacidad-permanente-total-absoluta-167`). Recurso de suplicación del demandante, ante la Sala de lo Social del TSJ, para que la incapacidad permanente reconocida como total se eleve a absoluta, con los motivos del recurso.

### Escritos y solicitudes (3)

- **Certificación negativa de descubiertos de la subcontratista: solicitud a la Tesorería** (`certificacion-negativa-descubiertos-subcontratista-384`). Solicitud de la empresa principal a la Tesorería General de la Seguridad Social de certificación negativa de descubiertos de la empresa subcontratista, para acreditar que está al corriente de cotizaciones.
- **Pedir cambio de puesto por embarazo o lactancia** (`pedir-cambio-puesto-embarazo-lactancia-218`). Escrito de la trabajadora a la empresa para pedir un cambio de puesto o la adaptación de sus condiciones por riesgo para su salud, la del feto o del lactante durante el embarazo o la lactancia.
- **Pedir suspensión del contrato por incendios forestales** (`pedir-suspension-contrato-incendios-forestales-15`). Escrito del trabajador a la empresa para pedir la suspensión de su contrato por emergencia ante incendios forestales y acceder a la prestación extraordinaria prevista en la norma temporal.

### Documentos, certificados y modelos oficiales (5)

- **Aptitud tras el reconocimiento médico: declaración** (`aptitud-tras-reconocimiento-medico-declaracion-355`). Declaración del médico del trabajo que comunica a la empresa la aptitud del trabajador tras el reconocimiento médico, indicando el tipo de reconocimiento y las medidas preventivas propuestas.
- **Certificado de la federación deportiva sobre periodos de actividad como deportista profesional** (`certificado-federacion-deportiva-sobre-periodos-8`). Certificado que expide la federación deportiva para acreditar los periodos de actividad como deportista profesional, cuando dispone de la información, a efectos de la Seguridad Social.
- **Certificado de ministro de culto evangélico y tiempo de actividad en España** (`certificado-ministro-culto-evangelico-tiempo-actividad-7`). Certificado que acredita el tiempo de actividad en España de un ministro de culto evangélico, expedido por su iglesia con la conformidad de la comisión permanente, a efectos de la Seguridad Social.
- **Certificado del club deportivo sobre periodos de actividad como deportista profesional** (`certificado-club-deportivo-sobre-periodos-actividad-como-6`). Certificado que expide el club para acreditar los periodos de actividad como deportista profesional y que se computen en la Seguridad Social; debe firmarlo quien represente al club.
- **Convenios bilaterales de Seguridad Social de España con otros países** (`convenios-bilaterales-seguridad-social-espana-otros-256`). Listado de consulta de los países con los que España tiene convenio bilateral de Seguridad Social, útil para valorar si pueden totalizarse cotizaciones; la relación puede estar incompleta y conviene contrastarla.

### Otros (1)

- **Respuesta de la empresa a suspensión o permiso por fallecimiento en incendios forestales** (`respuesta-empresa-suspension-permiso-fallecimiento-13`). Respuesta de la empresa a la petición de suspensión del contrato o permiso por fallecimiento en incendios forestales, aceptando o negando la solicitud según la normativa temporal.
