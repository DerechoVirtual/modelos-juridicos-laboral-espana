# Reclamar salarios y modificar condiciones · España

> Plugin de Claude Code `modelos-salario-y-condiciones-espana` · **23 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para cambios en las condiciones de trabajo y cuestiones salariales: modificación sustancial de condiciones, sucesión de empresa, salario y diferencias salariales, reclamación de cantidad, anticipos y préstamos al trabajador.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 23 está al final):

- **Contratos, cláusulas y anexos** (1). Por ejemplo: Préstamo de la empresa al trabajador: contrato.
- **Cartas y comunicaciones a la plantilla** (4). Por ejemplo: Modificación sustancial: comunicación de los miembros de la comisión negociadora; Sucesión de empresa: aviso al trabajador; Compensación y absorción sin subida de salario: aviso al trabajador.
- **Demandas, papeletas y reclamaciones previas** (10). Por ejemplo: Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge; Reclamación de cantidad de la empresa al trabajador: demanda; Extinguir el contrato por modificación sustancial de condiciones: demanda.
- **Escritos y solicitudes** (3). Por ejemplo: Modificación sustancial colectiva: petición de la empresa para constituir comisión negociadora; Pedir anticipo de salario; Ascenso de categoría y diferencias salariales por funciones superiores: solicitud.
- **Actas, acuerdos, planes y protocolos** (4). Por ejemplo: Designación de trabajadores para negociar una modificación sustancial colectiva: acta; Reconocimiento de deuda de la empresa al trabajador: acuerdo; Reconocimiento de deuda del trabajador a la empresa: acuerdo.
- **Otros** (1). Por ejemplo: Negativa de la empresa tras modificación sustancial de condiciones: resolución.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Demanda de reclamación de cantidad»
   - «Solicitud de diferencias salariales por realizar funciones superiores»
   - «Contrato de préstamo de la empresa a un trabajador»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-salario-y-condiciones-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-salario-y-condiciones-espana:demanda-traslado-violencia-genero-sexual-terrorismo-28`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-salario-y-condiciones-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-salario-y-condiciones-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-salario-y-condiciones-espana:<skill>`). Son 23, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (1)

- **Préstamo de la empresa al trabajador: contrato** (`prestamo-empresa-trabajador-contrato-346`). Contrato por el que la empresa concede un préstamo al trabajador, con las condiciones de devolución y de intereses, y las consideraciones fiscales de la retribución en especie cuando procedan.

### Cartas y comunicaciones a la plantilla (4)

- **Compensación y absorción sin subida de salario: aviso al trabajador** (`compensacion-absorcion-sin-subida-salario-aviso-379`). Comunicación de la empresa al trabajador para informarle de que su aumento por convenio o ley se compensa y absorbe con complementos que ya percibía, de modo que su salario total no sube.
- **Modificación sustancial: comunicación de los miembros de la comisión negociadora** (`modificacion-sustancial-comunicacion-miembros-comision-101`). Comunicación de la empresa a quienes han de integrar la comisión negociadora para informarles de que va a iniciar el periodo de consultas de una modificación sustancial de condiciones de trabajo de carácter colectivo.
- **Sucesión de empresa: aviso al trabajador** (`sucesion-empresa-aviso-trabajador-357`). Carta de la empresa al trabajador para comunicarle una sucesión de empresa o de contrata, por transmisión, subrogación o fallecimiento del empresario, y la subrogación en su contrato de trabajo.
- **Sucesión en la contrata: aviso de la empresa a la representación de los trabajadores** (`sucesion-contrata-aviso-empresa-representacion-356`). Carta de la empresa a la representación de los trabajadores para informarles del cambio de titularidad en una contrata y de sus consecuencias, como exige la normativa sobre sucesión de empresa.

### Demandas, papeletas y reclamaciones previas (10)

- **Cambio de titularidad de la contrata: demanda de reconocimiento laboral** (`cambio-titularidad-contrata-demanda-reconocimiento-189`). Demanda del trabajador para que se reconozcan sus derechos laborales frente a la nueva empresa que asume la contrata y que se niega a subrogarse en su contrato, ante el orden social.
- **Daños en vehículo de empresa: demanda de indemnización** (`danos-vehiculo-empresa-demanda-indemnizacion-145`). Demanda de la empresa que reclama a un trabajador la indemnización por los daños causados al vehículo de la empresa durante su trabajo, ante la Sección de lo Social del Tribunal de Instancia.
- **Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge** (`demanda-traslado-violencia-genero-sexual-terrorismo-28`). Demanda del trabajador que pide el traslado de centro de trabajo por ser víctima de violencia de género, sexual o terrorismo, o por motivos de salud o traslado del cónyuge, cuando la empresa lo ha denegado.
- **Despido disciplinario o reclamación de cantidad: papeleta de conciliación en el SMAC** (`despido-disciplinario-reclamacion-cantidad-papeleta-368`). Papeleta de conciliación previa ante el SMAC para despido disciplinario o reclamación de cantidad, como trámite necesario antes de presentar la demanda contra la empresa en el orden social.
- **Extinguir el contrato por modificación sustancial de condiciones: demanda** (`extinguir-contrato-modificacion-sustancial-condiciones-120`). Demanda del trabajador que, tras una modificación sustancial de sus condiciones de trabajo que le perjudica, pide la extinción de su contrato con la indemnización legal correspondiente.
- **Negativa a la subrogación empresarial: demanda de extinción del trabajador** (`negativa-subrogacion-empresarial-demanda-extincion-407`). Demanda del trabajador que pide la extinción de su contrato por voluntad propia, con indemnización, porque la nueva empresa se niega a subrogarse en su relación laboral tras un cambio de empresa.
- **Reclamación de cantidad de la empresa al trabajador: demanda** (`reclamacion-cantidad-empresa-trabajador-demanda-31`). Demanda con la que la empresa reclama a un trabajador una cantidad de dinero que este le debe, como anticipos o daños, ante la Sección de lo Social del Tribunal de Instancia.
- **Reclamación de cantidad: demanda** (`reclamacion-cantidad-demanda-371`). Demanda del trabajador contra la empresa en reclamación de cantidad, con modelos para salarios, horas extras, indemnización por despido y otros conceptos, ante la Sección de lo Social del Tribunal de Instancia.
- **Salarios contra grupo laboral de empresas: demanda** (`salarios-contra-grupo-laboral-empresas-demanda-387`). Demanda del trabajador que reclama salarios adeudados a varias empresas a la vez por formar un grupo laboral, para que respondan solidariamente de la deuda, ante la Sección de lo Social.
- **TRADE: demanda de reclamación de cantidad a la empresa cliente** (`trade-demanda-reclamacion-cantidad-empresa-cliente-405`). Demanda del trabajador autónomo económicamente dependiente que reclama a la empresa cliente el importe de los trabajos realizados y no pagados, por el proceso ordinario ante el orden social.

### Escritos y solicitudes (3)

- **Ascenso de categoría y diferencias salariales por funciones superiores: solicitud** (`ascenso-categoria-diferencias-salariales-funciones-417`). Solicitud del trabajador a la empresa para que se le reconozca la categoría y se le abonen las diferencias salariales por llevar tiempo realizando funciones superiores a las de su grupo profesional.
- **Modificación sustancial colectiva: petición de la empresa para constituir comisión negociadora** (`modificacion-sustancial-colectiva-peticion-empresa-102`). Escrito con el que la empresa solicita la constitución de la comisión negociadora ante una modificación sustancial colectiva de condiciones de trabajo y propone iniciar el periodo de consultas con los representantes.
- **Pedir anticipo de salario** (`pedir-anticipo-salario-171`). Escrito del trabajador a la empresa para solicitar un anticipo a cuenta del salario ya devengado y todavía no cobrado, dirigido a recursos humanos.

### Actas, acuerdos, planes y protocolos (4)

- **Cesión de vivienda al trabajador: acuerdo de uso** (`cesion-vivienda-trabajador-acuerdo-uso-183`). Acuerdo entre la empresa y el trabajador por el que aquella le cede el uso de una vivienda por razón del trabajo, con las condiciones de uso, duración y extinción de la cesión.
- **Designación de trabajadores para negociar una modificación sustancial colectiva: acta** (`designacion-trabajadores-negociar-modificacion-100`). Acta de la asamblea en la que las personas trabajadoras, sin representación legal, designan a quienes las representarán en la negociación de una modificación sustancial colectiva con la empresa.
- **Reconocimiento de deuda de la empresa al trabajador: acuerdo** (`reconocimiento-deuda-empresa-trabajador-acuerdo-174`). Acuerdo por el que la empresa reconoce deber una cantidad al trabajador y se compromete a pagarla, con las condiciones y plazos pactados, para documentar la deuda y evitar el litigio.
- **Reconocimiento de deuda del trabajador a la empresa: acuerdo** (`reconocimiento-deuda-trabajador-empresa-acuerdo-175`). Acuerdo por el que el trabajador reconoce que debe una cantidad a la empresa y se compromete a devolverla, con la forma y plazos pactados, para dejar documentada la deuda.

### Otros (1)

- **Negativa de la empresa tras modificación sustancial de condiciones: resolución** (`negativa-empresa-tras-modificacion-sustancial-416`). Respuesta del trabajador, o resolución de la empresa, tras una modificación sustancial de condiciones de trabajo comunicada con el procedimiento del Estatuto de los Trabajadores, ante la negativa a aceptarla.
