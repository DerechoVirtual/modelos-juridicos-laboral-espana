# Planes de igualdad y protocolos de acoso y LGTBI · España

> Plugin de Claude Code `modelos-plan-de-igualdad-y-acoso-espana` · **35 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para cumplir en igualdad y prevenir el acoso: plan de igualdad y su comisión negociadora, protocolos de acoso sexual y por razón de sexo, plan y protocolo LGTBI, y canal de denuncias.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 35 está al final):

- **Contratos, cláusulas y anexos** (1). Por ejemplo: Compromiso con el plan de igualdad en el convenio colectivo: cláusula.
- **Cartas y comunicaciones a la plantilla** (7). Por ejemplo: Aviso a la plantilla de la implantación del canal de denuncias; Carta para constituir la comisión negociadora del plan de igualdad; Criterios de selección de la empresa usuaria: comunicación a la empresa externa.
- **Demandas, papeletas y reclamaciones previas** (1). Por ejemplo: Acoso laboral (mobbing): demanda por infracción de la normativa de prevención.
- **Escritos y solicitudes** (2). Por ejemplo: Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso; Denuncia de acoso sexual o por razón de sexo.
- **Expediente disciplinario** (1). Por ejemplo: Cargos por acoso sexual: pliego.
- **Actas, acuerdos, planes y protocolos** (16). Por ejemplo: Impulso por la empresa de la negociación del plan de igualdad o del plan LGTBI; Protocolo contra el acoso y la violencia hacia personas LGTBI; Acuerdo con la representación de los trabajadores sobre medidas de igualdad LGTBI.
- **Documentos, certificados y modelos oficiales** (7). Por ejemplo: Evaluación para la comisión de seguimiento: cuestionario; Cuestionario de evaluación del plan dirigido a la plantilla; Cuestionario de evaluación dirigido a la dirección.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Protocolo contra el acoso sexual y por razón de sexo»
   - «Acta de constitución de la comisión negociadora del plan de igualdad»
   - «Protocolo contra el acoso y la violencia hacia las personas LGTBI»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-plan-de-igualdad-y-acoso-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-plan-de-igualdad-y-acoso-espana:evaluacion-comision-seguimiento-cuestionario-51`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-plan-de-igualdad-y-acoso-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-plan-de-igualdad-y-acoso-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-plan-de-igualdad-y-acoso-espana:<skill>`). Son 35, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (1)

- **Compromiso con el plan de igualdad en el convenio colectivo: cláusula** (`compromiso-plan-igualdad-convenio-colectivo-clausula-219`). Cláusula para incluir en un convenio colectivo el compromiso de las partes con la elaboración e implantación del plan de igualdad y con la no discriminación en la empresa o el sector.

### Cartas y comunicaciones a la plantilla (7)

- **Aviso a la plantilla de la implantación del canal de denuncias** (`aviso-plantilla-implantacion-canal-denuncias-95`). Comunicado de la empresa a la plantilla para informar de que ha implantado un canal de denuncias, con su finalidad, quién puede usarlo y cómo se garantizan la confidencialidad y la protección del informante.
- **Aviso a la plantilla del inicio del Plan de Igualdad** (`aviso-plantilla-inicio-plan-igualdad-213`). Comunicado de la empresa a toda la plantilla para anunciar el inicio del proceso de elaboración del Plan de Igualdad, informando de las fases previstas y de cómo participar.
- **Carta para constituir la comisión negociadora del plan de igualdad** (`carta-constituir-comision-negociadora-plan-igualdad-161`). Carta de la empresa a la representación de los trabajadores para convocar la constitución de la comisión negociadora del plan de igualdad e iniciar así el proceso de negociación.
- **Compromiso de la empresa con la igualdad: carta** (`compromiso-empresa-igualdad-carta-214`). Carta con la que la dirección de la empresa expresa a la plantilla su compromiso con la igualdad de trato y de oportunidades entre mujeres y hombres y con la prevención de la discriminación.
- **Criterios de selección de la empresa usuaria: comunicación a la empresa externa** (`criterios-seleccion-empresa-usuaria-comunicacion-empresa-206`). Comunicación de la empresa usuaria a la empresa externa que le presta servicios para trasladarle los criterios de selección que ha de aplicar con perspectiva de igualdad al proponer personal.
- **Reunión con perspectiva de igualdad: convocatoria** (`reunion-perspectiva-igualdad-convocatoria-212`). Convocatoria de una reunión con perspectiva de igualdad, que fija fecha, hora, lugar y orden del día para favorecer la participación equilibrada de mujeres y hombres convocados.
- **Sanción por acoso: carta** (`sancion-acoso-carta-316`). Carta de la empresa al trabajador para comunicarle la sanción disciplinaria impuesta por una conducta de acoso, con los hechos acreditados, la falta cometida y la sanción aplicada.

### Demandas, papeletas y reclamaciones previas (1)

- **Acoso laboral (mobbing): demanda por infracción de la normativa de prevención** (`acoso-laboral-mobbing-demanda-infraccion-normativa-162`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia por acoso laboral o mobbing, por infracción de la normativa de prevención de riesgos, para reclamar el cese del acoso y una indemnización.

### Escritos y solicitudes (2)

- **Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso** (`autorizar-tramites-inscripcion-plan-igualdad-protocolo-165`). Autorización de la empresa a una persona para que realice los trámites de inscripción del plan de igualdad o del protocolo de acoso en el registro correspondiente, en su nombre.
- **Denuncia de acoso sexual o por razón de sexo** (`denuncia-acoso-sexual-razon-sexo-217`). Denuncia de la persona que sufre acoso sexual o por razón de sexo en el trabajo, dirigida a la empresa o al órgano competente para que investigue los hechos y adopte medidas de protección y sanción.

### Expediente disciplinario (1)

- **Cargos por acoso sexual: pliego** (`cargos-acoso-sexual-pliego-326`). Pliego de cargos por el que la empresa imputa formalmente a un trabajador una falta de acoso sexual en un expediente disciplinario, describiendo los hechos para que presente sus alegaciones.

### Actas, acuerdos, planes y protocolos (16)

- **Acta de aprobación del plan de igualdad o del plan LGTBI** (`acta-aprobacion-plan-igualdad-plan-lgtbi-164`). Acta en la que la comisión aprueba el plan de igualdad o el plan LGTBI de la empresa, con sus objetivos, medidas, calendario y sistema de seguimiento, y deja constancia del acuerdo.
- **Acta de aprobación del protocolo contra el acoso sexual o por razón de sexo** (`acta-aprobacion-protocolo-contra-acoso-sexual-razon-sexo-158`). Acta en la que se aprueba el protocolo contra el acoso sexual o por razón de sexo, con la representación de la empresa y de los trabajadores, para dejar constancia del acuerdo y de su entrada en vigor.
- **Acta de constitución de la Comisión de seguimiento del plan de igualdad o plan LGTBI** (`acta-constitucion-comision-seguimiento-plan-igualdad-146`). Acta por la que se constituye formalmente la comisión de seguimiento del plan de igualdad o del plan LGTBI, con los miembros designados, sus funciones y las reglas básicas de funcionamiento.
- **Acta de constitución de la comisión negociadora del plan de igualdad o plan LGTBI** (`acta-constitucion-comision-negociadora-plan-igualdad-211`). Acta por la que se constituye la comisión negociadora del plan de igualdad o del plan LGTBI, con la representación de la empresa y de los trabajadores y las reglas del proceso de negociación.
- **Acta de reunión de la Comisión de seguimiento del Plan de Igualdad** (`acta-reunion-comision-seguimiento-plan-igualdad-141`). Acta que recoge una reunión de la comisión de seguimiento del Plan de Igualdad: asistentes, orden del día, acuerdos adoptados y evaluación de las medidas aplicadas hasta el momento.
- **Acuerdo con la representación de los trabajadores sobre medidas de igualdad LGTBI** (`acuerdo-representacion-trabajadores-sobre-medidas-118`). Acuerdo entre la empresa y la representación de los trabajadores sobre las medidas de igualdad y no discriminación de las personas LGTBI, que se pactan y se incorporan a la organización del trabajo.
- **Comisión negociadora del plan de igualdad: acta de reunión** (`comision-negociadora-plan-igualdad-acta-reunion-209`). Acta de una reunión de la comisión negociadora del plan de igualdad, con asistentes, orden del día, propuestas de cada parte y acuerdos adoptados durante la negociación.
- **Compromiso de la organización contra el acoso sexual y por razón de sexo** (`compromiso-organizacion-contra-acoso-sexual-razon-sexo-215`). Compromiso formal de la organización de prevenir y no tolerar el acoso sexual y por razón de sexo, con las conductas rechazadas, las garantías para quien denuncia y las vías de actuación.
- **Compromisos de la organización en selección y promoción** (`compromisos-organizacion-seleccion-promocion-208`). Compromisos de la organización en los procesos de selección y promoción para garantizar la igualdad de trato y de oportunidades, como parte de las medidas del plan de igualdad.
- **Confidencialidad en la tramitación de denuncias de acoso: compromiso** (`confidencialidad-tramitacion-denuncias-acoso-compromiso-220`). Compromiso de confidencialidad que firman quienes intervienen en la tramitación de una denuncia de acoso, para proteger la identidad de las personas implicadas y la información del procedimiento.
- **Diagnóstico del Plan de Igualdad: acta de aprobación** (`diagnostico-plan-igualdad-acta-aprobacion-160`). Acta en la que se aprueba el diagnóstico de situación que sirve de base al plan de igualdad, con los resultados analizados y los acuerdos de la comisión sobre las medidas a adoptar.
- **Impulso por la empresa de la negociación del plan de igualdad o del plan LGTBI** (`impulso-empresa-negociacion-plan-igualdad-plan-lgtbi-54`). Escrito de la empresa a la representación de los trabajadores para impulsar la negociación del plan de igualdad o del plan LGTBI, proponiendo constituir la comisión negociadora e iniciar el proceso.
- **Impulso por la representación de los trabajadores de la negociación del plan de igualdad** (`impulso-representacion-trabajadores-negociacion-plan-177`). Escrito de la representación de los trabajadores para impulsar la negociación del plan de igualdad y pedir a la empresa que constituya la comisión negociadora e inicie el proceso.
- **Protocolo contra el acoso sexual y por razón de sexo en el trabajo** (`protocolo-contra-acoso-sexual-razon-sexo-trabajo-216`). Protocolo de la empresa para prevenir el acoso sexual y por razón de sexo en el trabajo y actuar frente a él, con el procedimiento de denuncia, las garantías, las medidas cautelares y las sanciones.
- **Protocolo contra el acoso y la violencia hacia personas LGTBI** (`protocolo-contra-acoso-violencia-hacia-personas-lgtbi-108`). Protocolo de la empresa para prevenir el acoso y la violencia hacia personas LGTBI en el trabajo y para canalizar las denuncias, con medidas de protección, procedimiento de actuación y sanciones.
- **Reglamento de la Comisión de seguimiento y evaluación** (`reglamento-comision-seguimiento-evaluacion-136`). Reglamento de funcionamiento de la comisión que realiza el seguimiento y la evaluación del plan de igualdad, con su composición, funciones, periodicidad de reuniones y reglas de adopción de acuerdos.

### Documentos, certificados y modelos oficiales (7)

- **Cuestionario de evaluación del plan dirigido a la plantilla** (`cuestionario-evaluacion-plan-dirigido-plantilla-52`). Cuestionario dirigido a la plantilla para conocer su valoración del plan de igualdad, su grado de conocimiento y los efectos percibidos, como fuente de información para su evaluación.
- **Cuestionario de evaluación dirigido a la dirección** (`cuestionario-evaluacion-dirigido-direccion-53`). Cuestionario dirigido a la dirección de la empresa para recabar su valoración de la aplicación del plan de igualdad, los recursos empleados y las dificultades encontradas, para su evaluación.
- **Cuestionario de igualdad para la dirección** (`cuestionario-igualdad-direccion-205`). Modelo de cuestionario dirigido a las personas de la dirección de la empresa para recoger su visión y datos sobre igualdad, como apoyo al diagnóstico del plan de igualdad; se adapta a la estructura de cada empresa.
- **Cuestionario de igualdad para la plantilla** (`cuestionario-igualdad-plantilla-203`). Modelo de cuestionario que la empresa distribuye entre su plantilla para recabar datos sobre igualdad de trato y oportunidades, como base del diagnóstico del plan de igualdad; debe adaptarse a las características de cada empresa.
- **Evaluación del Plan de Igualdad: informe** (`evaluacion-plan-igualdad-informe-50`). Informe de evaluación del plan de igualdad de la empresa, que valora el grado de ejecución de las medidas, los resultados obtenidos y las propuestas de mejora para la comisión de seguimiento.
- **Evaluación para la comisión de seguimiento: cuestionario** (`evaluacion-comision-seguimiento-cuestionario-51`). Cuestionario para recoger información que la comisión de seguimiento necesita para evaluar el plan de igualdad, con preguntas sobre la ejecución de las medidas y sus resultados.
- **Plan de igualdad: hoja estadística** (`plan-igualdad-hoja-estadistica-169`). Hoja estadística del plan de igualdad que recoge los datos de plantilla y de las medidas del plan, con la información que se aporta al registro y a la evaluación del plan.
