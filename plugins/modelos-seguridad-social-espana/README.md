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

