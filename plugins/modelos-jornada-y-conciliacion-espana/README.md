# Jornada, permisos, teletrabajo y conciliación · España

> Plugin de Claude Code `modelos-jornada-y-conciliacion-espana` · **42 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para todo lo relativo al tiempo de trabajo: registro de jornada, adaptación de jornada para conciliar, permisos retribuidos, excedencias, trabajo a distancia y desconexión digital.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 42 está al final):

- **Contratos, cláusulas y anexos** (4). Por ejemplo: Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano); Anexo de horas complementarias (contrato a tiempo parcial) (en euskera); Anexo de horas complementarias (contrato a tiempo parcial) (en catalán).
- **Cartas y comunicaciones a la plantilla** (11). Por ejemplo: Propuesta de turnos de guardia al trabajador; Resumen mensual de horas de trabajo: comunicación; Aviso de ausencia por fuerza mayor ante enfermedad o accidente de un familiar: carta.
- **Demandas, papeletas y reclamaciones previas** (4). Por ejemplo: Demanda de adaptación de jornada por conciliación; Conciliación laboral, personal y familiar: demanda genérica de derechos; Trabajo a distancia: demanda por acceso, revisión o modificación.
- **Recursos** (1). Por ejemplo: Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso.
- **Escritos y solicitudes** (14). Por ejemplo: Pedir permiso retribuido por fallecimiento de familiar en incendios forestales; Pedir adaptación de jornada por cuidado de familiares tras la DANA; Pedir permiso retribuido por la DANA.
- **Actas, acuerdos, planes y protocolos** (5). Por ejemplo: Desconexión digital: protocolo; Personal de libre disponibilidad y registro de jornada: acuerdo con la representación; Distribución irregular de la jornada: acuerdo con la representación.
- **Documentos, certificados y modelos oficiales** (2). Por ejemplo: Declaración del hogar familiar sobre reducción de servicios por la DANA; Declaración responsable de trabajadores fuera del permiso retribuido recuperable del RDL 10/2020.
- **Otros** (1). Por ejemplo: Respuesta de la empresa al permiso retribuido por la DANA.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir la adaptación de jornada por conciliación»
   - «Pedir una excedencia»
   - «Protocolo de desconexión digital»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-jornada-y-conciliacion-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-jornada-y-conciliacion-espana:pedir-permiso-retribuido-fallecimiento-familiar-14`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 4.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-jornada-y-conciliacion-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-jornada-y-conciliacion-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

