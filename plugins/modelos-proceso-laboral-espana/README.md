# Papeleta, demanda y suplicación en lo social · España

> Plugin de Claude Code `modelos-proceso-laboral-espana` · **28 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para pleitear en lo social (LRJS) ante la Sección de lo Social del Tribunal de Instancia: papeleta de conciliación previa, demandas, ejecución de sentencias y acuerdos, recurso de suplicación, revisión y medidas cautelares.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 28 está al final):

- **Demandas, papeletas y reclamaciones previas** (7). Por ejemplo: Monitorio laboral: escrito del demandante tras la oposición de la empresa; Falso autónomo: demanda de reconocimiento de relación laboral; Revisión y declaración de error judicial: demanda.
- **Recursos** (5). Por ejemplo: Revisión contra decretos del LAJ: recurso; Suplicación: formalización del recurso; Anunciar recurso de suplicación.
- **Escritos y solicitudes** (16). Por ejemplo: Pedir la conciliación anticipada ante el tribunal; Reiniciar la ejecución laboral: escrito; Embargo preventivo de bienes tras la demanda: medida cautelar.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Pedir la ejecución de una sentencia firme»
   - «Formalización del recurso de suplicación»
   - «Pedir la conciliación anticipada ante el tribunal»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-proceso-laboral-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-proceso-laboral-espana:pedir-conciliacion-anticipada-ante-tribunal-17`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-proceso-laboral-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-proceso-laboral-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-proceso-laboral-espana:<skill>`). Son 28, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Demandas, papeletas y reclamaciones previas (7)

- **Falso autónomo: demanda de reconocimiento de relación laboral** (`falso-autonomo-demanda-reconocimiento-relacion-laboral-117`). Demanda de la persona que presta servicios como autónomo para que se declare la existencia de una relación laboral por cuenta ajena con la empresa a la que sirve, presentada ante la Sección de lo Social del Tribunal de Instancia.
- **Falso autónomo: papeleta de conciliación previa en el SMAC** (`falso-autonomo-papeleta-conciliacion-previa-smac-181`). Papeleta con la que el supuesto falso autónomo intenta la conciliación previa en el SMAC contra la empresa, para que se reconozca la relación laboral, como trámite previo a la demanda ante el orden social.
- **Incumplimiento de precontrato de trabajo: demanda de daños y perjuicios** (`incumplimiento-precontrato-trabajo-demanda-danos-244`). Demanda del trabajador que reclama daños y perjuicios a quien se comprometió a contratarle mediante un precontrato de trabajo y no lo cumplió, ante la Sección de lo Social del Tribunal de Instancia.
- **Monitorio laboral: escrito del demandante tras la oposición de la empresa** (`monitorio-laboral-escrito-demandante-tras-oposicion-47`). Escrito del demandante en el proceso monitorio laboral cuando la empresa se ha opuesto a la reclamación de cantidad: alega frente a la oposición y, en su caso, solicita que se continúe por el procedimiento ordinario ante la Sección de lo Social.
- **Personal laboral temporal irregular de entidades públicas: demanda para ser fijo** (`personal-laboral-temporal-irregular-entidades-publicas-304`). Demanda del personal laboral temporal de una entidad pública, en situación irregular por encadenar contratos o excederse en la duración, para que se le reconozca la condición de fijo o la indemnización que corresponda.
- **Reconocimiento de relación laboral con una entidad pública: demanda** (`reconocimiento-relacion-laboral-entidad-publica-demanda-303`). Demanda de quien ha prestado servicios para una entidad pública como autónomo mediante contratos administrativos, para que se declare que existe una verdadera relación laboral con ella, ante el orden social.
- **Revisión y declaración de error judicial: demanda** (`revision-declaracion-error-judicial-demanda-187`). Demanda para pedir la revisión de una sentencia firme del orden social o la declaración de error judicial, alegando los motivos legales que lo justifican y adjuntando la documentación y el depósito exigidos.

### Recursos (5)

- **Anunciar recurso de suplicación** (`anunciar-recurso-suplicacion-367`). Escrito con el que la parte anuncia ante el órgano que dictó la resolución su intención de recurrir en suplicación, acreditando en su caso el depósito y la consignación o aval exigibles.
- **Reposición contra la acumulación de procesos: recurso** (`reposicion-contra-acumulacion-procesos-recurso-404`). Recurso de reposición de la parte que se opone a que se acumule su proceso a otro ya iniciado ante el orden social, alegando por qué no procede la acumulación solicitada de contrario.
- **Reposición contra la acumulación indebida de acciones: recurso** (`reposicion-contra-acumulacion-indebida-acciones-recurso-401`). Escrito dirigido a la Sala de lo Social del TSJ para solicitar la acumulación de recursos pendientes; pese a su título, su contenido no es un recurso de reposición, por lo que conviene revisar el planteamiento antes de usarlo.
- **Revisión contra decretos del LAJ: recurso** (`revision-contra-decretos-laj-recurso-188`). Recurso de revisión que la parte interpone contra un decreto del letrado de la Administración de Justicia en el orden social, pidiendo que el tribunal lo deje sin efecto o lo modifique.
- **Suplicación: formalización del recurso** (`suplicacion-formalizacion-recurso-351`). Escrito de formalización del recurso de suplicación contra una resolución de la Sección de lo Social, en el que se exponen los motivos del recurso y se pide a la Sala de lo Social del TSJ que revoque la resolución.

### Escritos y solicitudes (16)

- **Cambio de partes en la ejecución por sucesión empresarial: escrito** (`cambio-partes-ejecucion-sucesion-empresarial-escrito-360`). Escrito para pedir que se tenga como ejecutada a la empresa sucesora de la deudora, cambiando las partes en la ejecución laboral cuando ha habido una sucesión empresarial y se quiere dirigir el embargo contra ella.
- **Conclusiones complementarias sucintas** (`conclusiones-complementarias-sucintas-260`). Escrito de conclusiones complementarias y breves tras la práctica de la prueba en el proceso laboral, en el que la parte resume los hechos y fundamentos y reitera lo que pide al tribunal.
- **Ejecución de sentencia o acta de conciliación firme: solicitud** (`ejecucion-sentencia-acta-conciliacion-firme-solicitud-365`). Solicitud del ejecutante para que se despache ejecución de una sentencia firme o de un acta de conciliación incumplida en el orden social, con designación de bienes para el embargo.
- **Ejecución del acuerdo de conciliación judicial (decreto del LAJ)** (`ejecucion-acuerdo-conciliacion-judicial-decreto-laj-254`). Solicitud de ejecución de lo acordado en una conciliación judicial aprobada por decreto del letrado de la Administración de Justicia, cuando la parte obligada incumple lo pactado, pidiendo que se despache ejecución.
- **Ejecución provisional de sentencia: solicitud** (`ejecucion-provisional-sentencia-solicitud-366`). Solicitud de ejecución provisional de una sentencia laboral recurrida, de cantidad u otras condenas, que presenta quien ha ganado en la instancia para anticipar su cumplimiento mientras se resuelve el recurso.
- **Embargo preventivo de bienes tras la demanda: medida cautelar** (`embargo-preventivo-bienes-tras-demanda-medida-cautelar-122`). Escrito del demandante para solicitar, una vez interpuesta la demanda, el embargo preventivo de bienes del demandado como medida cautelar que asegure el cobro de lo reclamado, ante la Sección de lo Social.
- **Impugnar la liquidación de intereses en la ejecución laboral** (`impugnar-liquidacion-intereses-ejecucion-laboral-163`). Escrito de la parte ejecutada, o de quien discrepe, para impugnar la liquidación de intereses practicada en la ejecución laboral, señalando los errores de cálculo y pidiendo que se rectifique.
- **Multas coercitivas a terceros por incumplir en la ejecución de sentencia laboral: solicitud** (`multas-coercitivas-terceros-incumplir-ejecucion-411`). Solicitud del ejecutante para que el tribunal imponga multas coercitivas a un tercero que no colabora o incumple lo requerido en la ejecución de una sentencia laboral, como entidades o personas que deben informar o retener.
- **Pedir actos preparatorios o prueba anticipada** (`pedir-actos-preparatorios-prueba-anticipada-373`). Escrito para pedir, antes de la demanda o durante el proceso laboral, diligencias preparatorias o la práctica anticipada de una prueba cuando existe riesgo de que después no pueda practicarse.
- **Pedir acumulación de procesos ante el mismo o distinto tribunal** (`pedir-acumulacion-procesos-ante-mismo-distinto-tribunal-372`). Escrito para solicitar la acumulación de varios procesos laborales que se siguen ante el mismo tribunal o ante tribunales distintos, para que se tramiten y resuelvan conjuntamente.
- **Pedir apremio pecuniario o multa coercitiva** (`pedir-apremio-pecuniario-multa-coercitiva-363`). Escrito del ejecutante para que, en la ejecución laboral, se impongan apremios pecuniarios o multas coercitivas al ejecutado que no cumple lo ordenado, con modelos según el supuesto.
- **Pedir declaración de insolvencia** (`pedir-declaracion-insolvencia-362`). Escrito del ejecutante, o del tribunal en otro caso, para que se declare la insolvencia del ejecutado en la ejecución laboral por no tener bienes suficientes, con opciones según haya o no decreto de insolvencia previo.
- **Pedir embargo** (`pedir-embargo-359`). Solicitud del ejecutante de que se embarguen bienes del ejecutado en la ejecución laboral, con modelos para cuentas corrientes y saldos deudores de clientes de la empresa, dirigida a la Sección de lo Social.
- **Pedir la conciliación anticipada ante el tribunal** (`pedir-conciliacion-anticipada-ante-tribunal-17`). Escrito para solicitar al tribunal social, una vez admitida la demanda y antes del juicio, la celebración de un acto de conciliación anticipada que permita llegar a un acuerdo y evitar el juicio.
- **Pedir suspensión o aplazamiento de la ejecución** (`pedir-suspension-aplazamiento-ejecucion-364`). Escrito para solicitar la suspensión o el aplazamiento de la ejecución laboral, ya sea por el ejecutante, de común acuerdo entre las partes, o por las personas trabajadoras, con varios modelos según el motivo.
- **Reiniciar la ejecución laboral: escrito** (`reiniciar-ejecucion-laboral-escrito-18`). Escrito del ejecutante para pedir que se reinicie la ejecución laboral archivada provisionalmente por insolvencia, por haber aparecido bienes o datos nuevos del ejecutado, y se reanuden las actuaciones de embargo.
