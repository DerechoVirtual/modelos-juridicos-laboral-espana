# ERE, ERTE y Mecanismo RED · España

> Plugin de Claude Code `modelos-ere-y-erte-espana` · **36 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para reestructuraciones: despido colectivo con su periodo de consultas, comisión negociadora, ERTE por causas ETOP o por fuerza mayor, Mecanismo RED y comunicaciones a la autoridad laboral.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 36 está al final):

- **Cartas y comunicaciones a la plantilla** (17). Por ejemplo: Mecanismo RED: inicio del procedimiento comunicado a la representación de los trabajadores; Cierre de centro en un despido colectivo: aviso a la autoridad laboral; Prórroga de la suspensión o reducción de jornada por ETOP (ERTE): aviso al trabajador.
- **Demandas, papeletas y reclamaciones previas** (7). Por ejemplo: Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED; Despido colectivo en grupo mercantil sin cuentas consolidadas: nulidad por falta de documentación; Despido colectivo: demanda de nulidad por falta de documentación.
- **Escritos y solicitudes** (1). Por ejemplo: Mecanismo RED: petición de la empresa para constituir la comisión negociadora.
- **Actas, acuerdos, planes y protocolos** (8). Por ejemplo: ERTE por ETOP: acta de designación de la comisión ad hoc; Calendario del expediente de regulación de empleo; ERTE suspensivo por fuerza mayor temporal: acta de reunión con la representación.
- **Documentos, certificados y modelos oficiales** (3). Por ejemplo: Declaración responsable de exención de cuotas en ERTE y Mecanismo RED; Lista de trabajadores afectados por expedientes de regulación de empleo; Memoria de ejemplo sobre causa productiva en un despido colectivo.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Comunicación a la plantilla de la apertura del periodo de consultas de un ERTE»
   - «Acta de constitución de la comisión negociadora de un despido colectivo»
   - «Acta final del periodo de consultas del Mecanismo RED»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-ere-y-erte-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-ere-y-erte-espana:mecanismo-red-inicio-procedimiento-comunicado-55`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-ere-y-erte-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-ere-y-erte-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-ere-y-erte-espana:<skill>`). Son 36, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Cartas y comunicaciones a la plantilla (17)

- **Cierre de centro en un despido colectivo: aviso a la autoridad laboral** (`cierre-centro-despido-colectivo-aviso-autoridad-laboral-73`). Comunicación de la empresa a la autoridad laboral del cierre de un centro de trabajo en el marco de un despido colectivo, con los datos del centro y de los trabajadores afectados.
- **Despido colectivo: carta a la plantilla para nombrar la comisión negociadora** (`despido-colectivo-carta-plantilla-nombrar-comision-186`). Carta de la empresa a la plantilla para que designe a su comisión negociadora en un despido colectivo, con los plazos de designación. Conviene revisar los requisitos de constitución de la comisión.
- **Despido colectivo: inicio del periodo de consultas comunicado a la autoridad laboral** (`despido-colectivo-inicio-periodo-consultas-comunicado-420`). Comunicación de la empresa a la autoridad laboral del inicio del periodo de consultas de un despido colectivo, con las causas, el número de afectados y los criterios de selección.
- **Despido colectivo: miembros de la comisión negociadora comunicados a la empresa** (`despido-colectivo-miembros-comision-negociadora-185`). Comunicación a la empresa de las personas designadas por los trabajadores para formar parte de la comisión negociadora del despido colectivo. Conviene revisar los plazos y los requisitos de constitución.
- **ERTE por ETOP: apertura del periodo de consultas comunicada a los trabajadores** (`erte-etop-apertura-periodo-consultas-comunicada-250`). Comunicación de la empresa a los trabajadores de la apertura del periodo de consultas de un ERTE por causas económicas, técnicas, organizativas o de producción, e invitación a designar representantes.
- **ERTE por ETOP: suspensión o reducción de jornada comunicada al trabajador** (`erte-etop-suspension-reduccion-jornada-comunicada-335`). Comunicación individual de la empresa al trabajador sobre la suspensión de su contrato o la reducción de su jornada decidida en un ERTE por causas económicas, técnicas, organizativas o de producción.
- **ERTE por fuerza mayor temporal: comunicación al trabajador** (`erte-fuerza-mayor-temporal-comunicacion-trabajador-200`). Comunicación de la empresa al trabajador de que su contrato queda suspendido o su jornada reducida por un ERTE de fuerza mayor temporal, con fecha de efectos y duración prevista.
- **Fin de las medidas de ERTE: comunicación a la autoridad laboral** (`fin-medidas-erte-comunicacion-autoridad-laboral-195`). Comunicación de la empresa a la autoridad laboral de que han terminado las medidas de suspensión o reducción de jornada de un ERTE, con la fecha de finalización y los trabajadores afectados.
- **Fin del ERTE y reincorporación al trabajo: carta al trabajador** (`fin-erte-reincorporacion-trabajo-carta-trabajador-194`). Carta de la empresa al trabajador para comunicarle el fin del ERTE que le afectaba y su reincorporación al trabajo, con la fecha en que debe volver.
- **Mecanismo RED: acuerdo comunicado a la autoridad laboral** (`mecanismo-red-acuerdo-comunicado-autoridad-laboral-58`). Comunicación a la autoridad laboral del acuerdo alcanzado en el periodo de consultas para aplicar medidas del Mecanismo RED de flexibilidad y estabilización del empleo.
- **Mecanismo RED: apertura del periodo de consultas comunicada a la plantilla** (`mecanismo-red-apertura-periodo-consultas-comunicada-61`). Comunicación de la empresa a la plantilla de la apertura del periodo de consultas para aplicar medidas del Mecanismo RED, e invitación a designar a sus representantes en la comisión negociadora.
- **Mecanismo RED: decisión sin acuerdo comunicada a la autoridad laboral** (`mecanismo-red-decision-sin-acuerdo-comunicada-autoridad-57`). Comunicación a la autoridad laboral de la decisión de la empresa de aplicar medidas del Mecanismo RED cuando el periodo de consultas termina sin acuerdo con la representación.
- **Mecanismo RED: designación de miembros de la comisión negociadora comunicada a la empresa** (`mecanismo-red-designacion-miembros-comision-negociadora-63`). Comunicación por la que los trabajadores o sus representantes informan a la empresa de los miembros que han designado para la comisión negociadora del Mecanismo RED.
- **Mecanismo RED: inicio del periodo de consultas comunicado a la autoridad laboral** (`mecanismo-red-inicio-periodo-consultas-comunicado-60`). Comunicación de la empresa a la autoridad laboral del inicio del periodo de consultas en el procedimiento de suspensión o reducción de jornada con el Mecanismo RED activado.
- **Mecanismo RED: inicio del procedimiento comunicado a la representación de los trabajadores** (`mecanismo-red-inicio-procedimiento-comunicado-55`). Comunicación de la dirección de la empresa a la representación de los trabajadores con la que inicia, con el Mecanismo RED activado, el procedimiento de suspensión de contratos o reducción de jornada.
- **Prórroga de la suspensión o reducción de jornada por ETOP (ERTE): aviso al trabajador** (`prorroga-suspension-reduccion-jornada-etop-erte-aviso-180`). Aviso de la empresa al trabajador de que se prorroga la suspensión de su contrato o la reducción de su jornada derivadas de un ERTE por causas económicas, técnicas, organizativas o de producción.
- **Reducción de jornada o suspensión de contratos sin representantes: aviso a todos los trabajadores** (`reduccion-jornada-suspension-contratos-sin-421`). Aviso de la empresa a todos los trabajadores, cuando no hay representantes, para informarles de una reducción de jornada o suspensión de contratos y de la forma de intervenir en la negociación.

### Demandas, papeletas y reclamaciones previas (7)

- **Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED** (`demanda-contra-denegacion-erte-fuerza-mayor-temporal-179`). Demanda de los afectados o de sus representantes ante el orden social contra la denegación de un ERTE por fuerza mayor temporal o de la solicitud de activación del Mecanismo RED.
- **Despido colectivo con acuerdo: demanda de sindicatos que no lo firmaron** (`despido-colectivo-acuerdo-demanda-sindicatos-no-lo-391`). Demanda de los sindicatos que no firmaron el acuerdo de un despido colectivo para impugnarlo ante la Sección de lo Social, por ejemplo por fraude, dolo o abuso de derecho.
- **Despido colectivo en grupo laboral: nulidad por tramitarse solo en una empresa** (`despido-colectivo-grupo-laboral-nulidad-tramitarse-solo-392`). Demanda de impugnación de un despido colectivo que pide su nulidad porque el procedimiento se tramitó solo en una de las empresas del grupo laboral, y no en el conjunto.
- **Despido colectivo en grupo mercantil con cuentas consolidadas: nulidad por falta de documentación** (`despido-colectivo-grupo-mercantil-cuentas-consolidadas-389`). Demanda de impugnación de un despido colectivo en un grupo mercantil con cuentas consolidadas, que pide su nulidad por falta de la documentación exigida en el periodo de consultas.
- **Despido colectivo en grupo mercantil sin cuentas consolidadas: nulidad por falta de documentación** (`despido-colectivo-grupo-mercantil-sin-cuentas-375`). Demanda de impugnación de un despido colectivo en un grupo mercantil sin cuentas consolidadas, que pide su nulidad por no haberse aportado toda la documentación exigida en el periodo de consultas.
- **Despido colectivo por fuerza mayor sin resolución administrativa: demanda** (`despido-colectivo-fuerza-mayor-sin-resolucion-249`). Demanda ante la Sección de lo Social para impugnar un despido colectivo por fuerza mayor decidido por la empresa sin que exista resolución administrativa que la constate.
- **Despido colectivo: demanda de nulidad por falta de documentación** (`despido-colectivo-demanda-nulidad-falta-documentacion-388`). Demanda de impugnación de un despido colectivo que pide su nulidad porque la empresa no entregó en el periodo de consultas la documentación exigida por la normativa.

### Escritos y solicitudes (1)

- **Mecanismo RED: petición de la empresa para constituir la comisión negociadora** (`mecanismo-red-peticion-empresa-constituir-comision-64`). Escrito de la empresa para pedir la constitución de la comisión negociadora del Mecanismo RED, dirigido a los trabajadores o sus representantes para iniciar la negociación.

### Actas, acuerdos, planes y protocolos (8)

- **Acta de consultas del despido colectivo** (`acta-consultas-despido-colectivo-418`). Acta de una reunión del periodo de consultas de un despido colectivo, con la información aportada, las propuestas de las partes y los acuerdos o discrepancias. Conviene revisar los plazos de las consultas.
- **Calendario del expediente de regulación de empleo** (`calendario-expediente-regulacion-empleo-198`). Calendario que fija las reuniones del periodo de consultas de un expediente de regulación de empleo, con fechas, horas y lugar, y que se incorpora a la negociación.
- **Despido colectivo: acta de constitución de la comisión negociadora** (`despido-colectivo-acta-constitucion-comision-negociadora-184`). Acta de constitución de la comisión negociadora del despido colectivo, con sus miembros, la representación que ostentan y los acuerdos iniciales. Conviene revisar los plazos y requisitos de constitución.
- **ERTE por ETOP: acta de designación de la comisión ad hoc** (`erte-etop-acta-designacion-comision-ad-hoc-193`). Acta por la que los trabajadores designan la comisión ad hoc que los representará en las consultas de un ERTE por causas económicas, técnicas, organizativas o de producción.
- **ERTE suspensivo por fuerza mayor temporal: acta de reunión con la representación** (`erte-suspensivo-fuerza-mayor-temporal-acta-reunion-201`). Acta de una reunión entre la empresa y la representación de los trabajadores en un ERTE suspensivo por fuerza mayor temporal, con la información facilitada y las posiciones de las partes.
- **Mecanismo RED: acta de designación de la comisión ad hoc** (`mecanismo-red-acta-designacion-comision-ad-hoc-62`). Acta por la que los trabajadores, cuando no hay representantes, designan la comisión ad hoc que les representará en el periodo de consultas del Mecanismo RED.
- **Mecanismo RED: acta final del periodo de consultas** (`mecanismo-red-acta-final-periodo-consultas-56`). Acta que recoge el resultado final del periodo de consultas del Mecanismo RED, con las posiciones de las partes, los acuerdos o la falta de ellos y las firmas.
- **Mecanismo RED: acuerdo en el periodo de consultas con la representación de los trabajadores** (`mecanismo-red-acuerdo-periodo-consultas-representacion-59`). Acta o documento que recoge el acuerdo entre la empresa y la representación de los trabajadores en el periodo de consultas del Mecanismo RED, con las medidas pactadas.

### Documentos, certificados y modelos oficiales (3)

- **Declaración responsable de exención de cuotas en ERTE y Mecanismo RED** (`declaracion-responsable-exencion-cuotas-erte-mecanismo-192`). Declaración responsable que presenta la empresa a la Tesorería General de la Seguridad Social para aplicar las exenciones de cuotas ligadas a un ERTE o al Mecanismo RED.
- **Lista de trabajadores afectados por expedientes de regulación de empleo** (`lista-trabajadores-afectados-expedientes-regulacion-199`). Relación de trabajadores afectados por un expediente de regulación de empleo, con sus datos y la medida que se les aplica, para acompañar a las comunicaciones y declaraciones del procedimiento.
- **Memoria de ejemplo sobre causa productiva en un despido colectivo** (`memoria-ejemplo-sobre-causa-productiva-despido-colectivo-419`). Ejemplo de memoria sobre la causa productiva que fundamenta un despido colectivo, con sus datos y razonamientos, para presentar al abrir el periodo de consultas.
