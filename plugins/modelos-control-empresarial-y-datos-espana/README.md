# Videovigilancia, geolocalización y datos de la plantilla · España

> Plugin de Claude Code `modelos-control-empresarial-y-datos-espana` · **11 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para controlar la actividad de la plantilla respetando su intimidad: cláusulas de protección de datos, videovigilancia, geolocalización, uso de los medios informáticos de la empresa y códigos de conducta.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 11 está al final):

- **Contratos, cláusulas y anexos** (4). Por ejemplo: Protección de datos en contratos de trabajo: cláusula; Confidencialidad, control de medios y desconexión digital: cláusula; Protección de datos en contratos con empresa subcontratista: cláusula.
- **Cartas y comunicaciones a la plantilla** (3). Por ejemplo: Aviso emergente sobre el uso laboral de los medios de la empresa; Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores; Aviso al trabajador de videovigilancia, control de jornada o geolocalización.
- **Actas, acuerdos, planes y protocolos** (4). Por ejemplo: Información sobre protección de datos a los empleados; Código de conducta en la relación empresa-trabajador; Vestimenta en la empresa: código.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Cláusula de protección de datos para los contratos de trabajo»
   - «Aviso a los representantes de la instalación de cámaras de videovigilancia»
   - «Normas de uso del sistema informático y del correo de la empresa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-control-empresarial-y-datos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-control-empresarial-y-datos-espana:proteccion-datos-contratos-trabajo-clausula-172`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 1.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-control-empresarial-y-datos-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-control-empresarial-y-datos-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-control-empresarial-y-datos-espana:<skill>`). Son 11, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (4)

- **Confidencialidad, control de medios y desconexión digital: cláusula** (`confidencialidad-control-medios-desconexion-digital-173`). Cláusula del contrato de trabajo sobre confidencialidad, control empresarial de los medios digitales y derecho a la desconexión digital, que debe ajustarse a la política interna y a la participación de la representación legal.
- **Información sobre protección de datos en la geolocalización: cláusula** (`informacion-sobre-proteccion-datos-geolocalizacion-252`). Cláusula informativa para el trabajador sobre el uso de sistemas de geolocalización de la empresa, con su finalidad, base legal y derechos, y con información a la representación de los trabajadores.
- **Protección de datos en contratos con empresa subcontratista: cláusula** (`proteccion-datos-contratos-empresa-subcontratista-251`). Cláusula de protección de datos para el contrato con una empresa subcontratista que accede a datos personales por cuenta de la contratante, y que debe plantearse conforme a la normativa de encargados del tratamiento.
- **Protección de datos en contratos de trabajo: cláusula** (`proteccion-datos-contratos-trabajo-clausula-172`). Cláusula para incluir en los contratos de trabajo con la información y las garantías sobre protección de datos personales de los trabajadores, adaptada al tratamiento que hace la empresa.

### Cartas y comunicaciones a la plantilla (3)

- **Aviso al trabajador de videovigilancia, control de jornada o geolocalización** (`aviso-trabajador-videovigilancia-control-jornada-376`). Aviso de la empresa al trabajador sobre el uso de videovigilancia, control de jornada o geolocalización, con la información que exige la normativa de protección de datos y de derechos digitales.
- **Aviso emergente sobre el uso laboral de los medios de la empresa** (`aviso-emergente-sobre-uso-laboral-medios-empresa-223`). Texto de aviso que aparece en pantalla a los empleados para informarles de que los medios informáticos de la empresa son de uso laboral y de que puede controlarlos.
- **Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores** (`instalacion-camaras-videovigilancia-aviso-representacion-253`). Comunicación de la empresa a la representación de los trabajadores para informarle de la instalación de cámaras de videovigilancia, con su finalidad y ubicación, antes de ponerlas en funcionamiento.

### Actas, acuerdos, planes y protocolos (4)

- **Código de conducta en la relación empresa-trabajador** (`codigo-conducta-relacion-empresa-trabajador-232`). Código que fija las normas de comportamiento y los valores que deben respetar los trabajadores en la empresa, como base para exigir su cumplimiento y, en su caso, para aplicar el régimen disciplinario.
- **Información sobre protección de datos a los empleados** (`informacion-sobre-proteccion-datos-empleados-222`). Documento con el que la empresa informa a sus empleados sobre el tratamiento de sus datos personales: finalidades, bases legales, destinatarios, plazos de conservación y ejercicio de derechos.
- **Normas de uso del sistema informático y las comunicaciones electrónicas** (`normas-uso-sistema-informatico-comunicaciones-239`). Normas internas que regulan el uso por los trabajadores del ordenador, el correo electrónico e internet de la empresa, y los límites y controles que esta puede aplicar.
- **Vestimenta en la empresa: código** (`vestimenta-empresa-codigo-233`). Normas internas de la empresa sobre la vestimenta que deben llevar los trabajadores en el puesto de trabajo, para entregar a la plantilla y fijar criterios claros.
