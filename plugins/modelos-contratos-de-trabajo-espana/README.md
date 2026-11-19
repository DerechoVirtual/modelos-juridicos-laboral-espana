# Contratos de trabajo: indefinidos, temporales y formativos · España

> Plugin de Claude Code `modelos-contratos-de-trabajo-espana` · **84 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para contratar: contratos indefinidos, temporales y formativos (también los del Plan de Recuperación y versiones en catalán, euskera, gallego, valenciano e inglés), llamamiento y novación de fijos discontinuos, información obligatoria al trabajador (RD 723/2026), ETT y relaciones laborales especiales.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 84 está al final):

- **Contratos, cláusulas y anexos** (59). Por ejemplo: Novación de fijo discontinuo a indefinido ordinario: acuerdo; Contrato indefinido del Plan de Recuperación (en valenciano); Contrato de trabajo de pescadores (en inglés).
- **Cartas y comunicaciones a la plantilla** (11). Por ejemplo: Información al trabajador sobre los elementos esenciales del contrato: carta; Llamamiento a la actividad del fijo discontinuo: comunicación de la empresa; Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en valenciano).
- **Escritos y solicitudes** (3). Por ejemplo: Pedir información sobre los elementos esenciales de la relación laboral; Pedir trabajar a distancia; Pedir que el contrato de trabajo conste por escrito.
- **Documentos, certificados y modelos oficiales** (11). Por ejemplo: Información al trabajador sobre los elementos esenciales del contrato (en valenciano); Información al trabajador sobre los elementos esenciales del contrato (en euskera); Información al trabajador sobre los elementos esenciales del contrato (en gallego).

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Contrato de trabajo indefinido»
   - «Comunicación de llamamiento a un trabajador fijo discontinuo»
   - «Acuerdo de novación de un fijo discontinuo a indefinido ordinario»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-contratos-de-trabajo-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-contratos-de-trabajo-espana:informacion-trabajador-sobre-elementos-esenciales-1`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-contratos-de-trabajo-espana@modelos-juridicos-laboral-espana`).

## Instalación

**En Claude Code**, añade una vez el catálogo de este repositorio y después instala el plugin:

```bash
claude plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
claude plugin install modelos-contratos-de-trabajo-espana@modelos-juridicos-laboral-espana
```

Al terminar, abre una conversación nueva para que aparezcan sus skills.

**En Claude (web y escritorio)** también puedes subirlo como ZIP desde **Personalizar → Plugins**. El ZIP de este plugin está en la página de versiones del repositorio: https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-contratos-de-trabajo-espana:<skill>`). Son 84, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (59)

- **Acuerdo con voluntarios** (`acuerdo-voluntarios-412`). Acuerdo de compromiso de voluntariado entre una asociación o fundación y la persona voluntaria, que recoge las actividades que realizará y deja claro que no existe relación laboral.
- **Cláusulas adicionales del contrato de grupo** (`clausulas-adicionales-contrato-grupo-229`). Cláusulas adicionales para el contrato de trabajo de grupo, como las labores, la duración, el reparto de la retribución, la jornada, las vacaciones y los cambios en los componentes del grupo.
- **Cláusulas adicionales del contrato de trabajo** (`clausulas-adicionales-contrato-trabajo-342`). Colección de cláusulas adicionales que pueden anexarse a un contrato de trabajo, como exclusividad, periodo de prueba, permanencia, no competencia, preaviso o confidencialidad, con distintas redacciones.
- **Contrato de actuación de toreros, novilleros y rejoneadores** (`contrato-actuacion-toreros-novilleros-rejoneadores-132`). Contrato de actuación entre quien contrata y el torero, novillero o rejoneador, que recoge por escrito las condiciones esenciales y la composición de las cuadrillas con su afiliación a la Seguridad Social.
- **Contrato de artistas de duración determinada (relación laboral especial)** (`contrato-artistas-duracion-determinada-relacion-laboral-137`). Contrato de duración determinada de personas artistas en espectáculos públicos (relación laboral especial), que regula por escrito la actuación y las condiciones entre la empresa y la persona artista.
- **Contrato de formación en alternancia del Plan de Recuperación** (`contrato-formacion-alternancia-plan-recuperacion-87`). Modelo en castellano de contrato de trabajo de formación en alternancia del Plan de Recuperación, para contratar a una persona que compagina trabajo y formación.
- **Contrato de formación en alternancia del Plan de Recuperación (en catalán)** (`contrato-formacion-alternancia-plan-recuperacion-catalan-82`). Modelo de contrato de trabajo de formación en alternancia del Plan de Recuperación redactado en catalán, para contratar a una persona que compagina trabajo y formación.
- **Contrato de formación en alternancia del Plan de Recuperación (en euskera)** (`contrato-formacion-alternancia-plan-recuperacion-euskera-81`). Modelo de contrato de trabajo de formación en alternancia del Plan de Recuperación redactado en euskera, para contratar a una persona que compagina trabajo y formación.
- **Contrato de formación en alternancia del Plan de Recuperación (en gallego)** (`contrato-formacion-alternancia-plan-recuperacion-gallego-83`). Modelo de contrato de trabajo de formación en alternancia del Plan de Recuperación redactado en gallego, para contratar a una persona que compagina trabajo y formación.
- **Contrato de formación en alternancia del Plan de Recuperación (en valenciano)** (`contrato-formacion-alternancia-plan-recuperacion-78`). Modelo de contrato de trabajo de formación en alternancia del Plan de Recuperación redactado en valenciano, para contratar a una persona que compagina trabajo y formación.
- **Contrato de interinidad de profesor de religión** (`contrato-interinidad-profesor-religion-413`). Contrato de sustitución de un profesor de religión por vacante, entre el centro educativo y la persona con declaración de idoneidad propuesta por la confesión religiosa.
- **Contrato de patrón de embarcaciones de recreo** (`contrato-patron-embarcaciones-recreo-378`). Contrato entre una empresa con embarcaciones y un patrón profesional de embarcaciones de recreo, que regula la prestación de servicios y el cumplimiento de los requisitos de titulación náutica.
- **Contrato de personal civil de establecimientos militares** (`contrato-personal-civil-establecimientos-militares-415`). Contrato de trabajo entre un establecimiento militar y una persona que ha superado las pruebas de aptitud para un puesto de personal civil, con las condiciones de la relación laboral.
- **Contrato de personal técnico y auxiliar artístico de duración determinada** (`contrato-personal-tecnico-auxiliar-artistico-duracion-138`). Contrato de duración determinada del personal técnico y auxiliar que colabora con artistas en espectáculos públicos (relación laboral especial), con las condiciones pactadas entre empresa y trabajador.
- **Contrato de servicios profesionales** (`contrato-servicios-profesionales-144`). Contrato de servicios profesionales entre una empresa y un trabajador autónomo, que incluye cláusulas de prevención de riesgos laborales y regula el encargo, la duración y la retribución.
- **Contrato de trabajo de pescadores** (`contrato-trabajo-pescadores-178`). Modelo del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que presta servicios a bordo.
- **Contrato de trabajo de pescadores (en catalán)** (`contrato-trabajo-pescadores-catalan-70`). Modelo en catalán del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que trabaja a bordo.
- **Contrato de trabajo de pescadores (en euskera)** (`contrato-trabajo-pescadores-euskera-69`). Modelo en euskera del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que trabaja a bordo.
- **Contrato de trabajo de pescadores (en gallego)** (`contrato-trabajo-pescadores-gallego-71`). Modelo en gallego del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que trabaja a bordo.
- **Contrato de trabajo de pescadores (en inglés)** (`contrato-trabajo-pescadores-ingles-68`). Modelo en inglés del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que trabaja a bordo.
- **Contrato de trabajo de pescadores (en valenciano)** (`contrato-trabajo-pescadores-valenciano-72`). Modelo en valenciano del contrato de trabajo de pescadores, para formalizar por escrito la relación laboral entre la empresa o armador y la persona que trabaja a bordo.
- **Contrato del autónomo económicamente dependiente (TRADE)** (`contrato-autonomo-economicamente-dependiente-trade-248`). Contrato entre un cliente y un trabajador autónomo económicamente dependiente (TRADE), que fija por escrito las condiciones de la prestación de servicios y debe registrarse en el Servicio Público de Empleo Estatal.
- **Contrato formativo de práctica profesional del Plan de Recuperación** (`contrato-formativo-practica-profesional-plan-86`). Modelo en castellano de contrato formativo para obtener la práctica profesional, del Plan de Recuperación, para contratar a una persona con titulación que necesita ganar experiencia.
- **Contrato formativo de práctica profesional del Plan de Recuperación (en catalán)** (`contrato-formativo-practica-profesional-plan-80`). Modelo de contrato formativo para obtener la práctica profesional, del Plan de Recuperación, redactado en catalán, para contratar a una persona con titulación que necesita ganar experiencia.
- **Contrato formativo de práctica profesional del Plan de Recuperación (en euskera)** (`contrato-formativo-practica-profesional-plan-84`). Modelo de contrato formativo para obtener la práctica profesional, del Plan de Recuperación, redactado en euskera, para contratar a una persona con titulación que necesita ganar experiencia.
- **Contrato formativo de práctica profesional del Plan de Recuperación (en gallego)** (`contrato-formativo-practica-profesional-plan-85`). Modelo de contrato formativo para obtener la práctica profesional, del Plan de Recuperación, redactado en gallego, para contratar a una persona con titulación que necesita ganar experiencia.
- **Contrato formativo de práctica profesional del Plan de Recuperación (en valenciano)** (`contrato-formativo-practica-profesional-plan-79`). Modelo de contrato formativo para obtener la práctica profesional, del Plan de Recuperación, redactado en valenciano, para contratar a una persona con titulación que necesita ganar experiencia.
- **Contrato formativo en alternancia (en catalán)** (`contrato-formativo-alternancia-catalan-103`). Modelo de contrato de trabajo de formación en alternancia redactado en catalán, para contratar a una persona que compagina la actividad laboral con su formación.
- **Contrato formativo en alternancia (en euskera)** (`contrato-formativo-alternancia-euskera-105`). Modelo de contrato de trabajo de formación en alternancia redactado en euskera, para contratar a una persona que compagina la actividad laboral con su formación.
- **Contrato formativo en alternancia (en gallego)** (`contrato-formativo-alternancia-gallego-104`). Modelo de contrato de trabajo de formación en alternancia redactado en gallego, para contratar a una persona que compagina la actividad laboral con su formación.
- **Contrato formativo en alternancia (en valenciano)** (`contrato-formativo-alternancia-valenciano-106`). Modelo de contrato de trabajo de formación en alternancia redactado en valenciano, para contratar a una persona que compagina la actividad laboral con su formación.
- **Contrato formativo para la práctica profesional (en catalán)** (`contrato-formativo-practica-profesional-catalan-97`). Modelo de contrato formativo para obtener la práctica profesional, redactado en catalán, para contratar a una persona con titulación que necesita ganar experiencia laboral.
- **Contrato formativo para la práctica profesional (en euskera)** (`contrato-formativo-practica-profesional-euskera-99`). Modelo de contrato formativo para obtener la práctica profesional, redactado en euskera, para contratar a una persona con titulación que necesita ganar experiencia laboral.
- **Contrato formativo para la práctica profesional (en gallego)** (`contrato-formativo-practica-profesional-gallego-98`). Modelo de contrato formativo para obtener la práctica profesional, redactado en gallego, para contratar a una persona con titulación que necesita ganar experiencia laboral.
- **Contrato formativo para la práctica profesional (en valenciano)** (`contrato-formativo-practica-profesional-valenciano-96`). Modelo de contrato formativo para obtener la práctica profesional, redactado en valenciano, para contratar a una persona con titulación que necesita ganar experiencia laboral.
- **Contrato indefinido de profesor de religión** (`contrato-indefinido-profesor-religion-414`). Contrato indefinido entre un centro educativo y un profesor de religión con declaración de idoneidad propuesto por la confesión religiosa, con las condiciones de la relación laboral.
- **Contrato indefinido del Plan de Recuperación** (`contrato-indefinido-plan-recuperacion-77`). Modelo en castellano del contrato de trabajo indefinido del Plan de Recuperación, para formalizar por escrito la contratación entre la empresa y la persona trabajadora.
- **Contrato indefinido del Plan de Recuperación (en catalán)** (`contrato-indefinido-plan-recuperacion-catalan-74`). Modelo de contrato de trabajo indefinido del Plan de Recuperación redactado en catalán, para formalizar por escrito la contratación entre la empresa y la persona trabajadora.
- **Contrato indefinido del Plan de Recuperación (en euskera)** (`contrato-indefinido-plan-recuperacion-euskera-75`). Modelo de contrato de trabajo indefinido del Plan de Recuperación redactado en euskera, para formalizar por escrito la contratación entre la empresa y la persona trabajadora.
- **Contrato indefinido del Plan de Recuperación (en gallego)** (`contrato-indefinido-plan-recuperacion-gallego-76`). Modelo de contrato de trabajo indefinido del Plan de Recuperación redactado en gallego, para formalizar por escrito la contratación entre la empresa y la persona trabajadora.
- **Contrato indefinido del Plan de Recuperación (en valenciano)** (`contrato-indefinido-plan-recuperacion-valenciano-66`). Modelo de contrato de trabajo indefinido del Plan de Recuperación redactado en valenciano, para formalizar por escrito la contratación entre la empresa y la persona trabajadora.
- **Contrato laboral de colaboración para formar una cuadrilla** (`contrato-laboral-colaboracion-formar-cuadrilla-133`). Contrato laboral por el que un jefe de cuadrilla y las personas que la integran pactan por escrito su colaboración y las condiciones de trabajo en la cuadrilla.
- **Contrato laboral indefinido (en catalán)** (`contrato-laboral-indefinido-catalan-116`). Modelo de contrato de trabajo indefinido redactado en catalán, para formalizar por escrito una contratación por tiempo indefinido entre la empresa y la persona trabajadora.
- **Contrato laboral indefinido (en euskera)** (`contrato-laboral-indefinido-euskera-114`). Modelo de contrato de trabajo indefinido redactado en euskera, para formalizar por escrito una contratación por tiempo indefinido entre la empresa y la persona trabajadora.
- **Contrato laboral indefinido (en gallego)** (`contrato-laboral-indefinido-gallego-113`). Modelo de contrato de trabajo indefinido redactado en gallego, para formalizar por escrito una contratación por tiempo indefinido entre la empresa y la persona trabajadora.
- **Contrato laboral indefinido (en valenciano)** (`contrato-laboral-indefinido-valenciano-115`). Modelo de contrato de trabajo indefinido redactado en valenciano, para formalizar por escrito una contratación por tiempo indefinido entre la empresa y la persona trabajadora.
- **Contrato laboral temporal (en catalán)** (`contrato-laboral-temporal-catalan-112`). Modelo de contrato de trabajo temporal redactado en catalán, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato laboral temporal (en euskera)** (`contrato-laboral-temporal-euskera-111`). Modelo de contrato de trabajo temporal redactado en euskera, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato laboral temporal (en gallego)** (`contrato-laboral-temporal-gallego-110`). Modelo de contrato de trabajo temporal redactado en gallego, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato laboral temporal (en valenciano)** (`contrato-laboral-temporal-valenciano-109`). Modelo de contrato de trabajo temporal redactado en valenciano, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato temporal del Plan de Recuperación** (`contrato-temporal-plan-recuperacion-92`). Modelo en castellano de contrato de trabajo temporal del Plan de Recuperación, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato temporal del Plan de Recuperación (en catalán)** (`contrato-temporal-plan-recuperacion-catalan-91`). Modelo de contrato de trabajo temporal del Plan de Recuperación redactado en catalán, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato temporal del Plan de Recuperación (en euskera)** (`contrato-temporal-plan-recuperacion-euskera-90`). Modelo de contrato de trabajo temporal del Plan de Recuperación redactado en euskera, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato temporal del Plan de Recuperación (en gallego)** (`contrato-temporal-plan-recuperacion-gallego-89`). Modelo de contrato de trabajo temporal del Plan de Recuperación redactado en gallego, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Contrato temporal del Plan de Recuperación (en valenciano)** (`contrato-temporal-plan-recuperacion-valenciano-88`). Modelo de contrato de trabajo temporal del Plan de Recuperación redactado en valenciano, para formalizar por escrito una contratación de duración determinada entre la empresa y la persona trabajadora.
- **Novación de fijo discontinuo a indefinido ordinario: acuerdo** (`novacion-fijo-discontinuo-indefinido-ordinario-acuerdo-46`). Acuerdo entre empresa y persona trabajadora para novar un contrato fijo discontinuo en un contrato indefinido ordinario a tiempo completo, que fija las nuevas condiciones de la relación laboral.
- **Plan formativo** (`plan-formativo-207`). Plan de formación de la empresa para garantizar a sus trabajadores el derecho a la promoción y formación profesional en el trabajo, con las acciones formativas que se prevé desarrollar.
- **Plan individual de formación** (`plan-individual-formacion-135`). Plan individual de formación que se adjunta al contrato formativo y fija el itinerario formativo-laboral, los sistemas de evaluación y las actividades de tutoría de la persona contratada.
- **Puesta a disposición: contrato** (`puesta-disposicion-contrato-385`). Contrato de puesta a disposición entre una empresa de trabajo temporal y la empresa usuaria, que fija las condiciones del trabajador cedido, conforme al modelo oficial publicado en el BOE.

### Cartas y comunicaciones a la plantilla (11)

- **Información al trabajador sobre los elementos esenciales del contrato: carta** (`informacion-trabajador-sobre-elementos-esenciales-9`). Carta con la que la empresa entrega al trabajador la información escrita sobre los elementos esenciales de su contrato, con opciones para detallar o remitir al convenio. Debe contrastarse con el contenido exigido por la norma vigente.
- **Interrupción de actividad del TRADE: comunicación** (`interrupcion-actividad-trade-comunicacion-353`). Carta con la que el trabajador autónomo económicamente dependiente comunica a su empresa cliente la interrupción de su actividad por una causa del Estatuto del trabajo autónomo, como responsabilidades familiares urgentes o incapacidad temporal.
- **Llamamiento a la actividad de fijos discontinuos: comunicación (en catalán)** (`llamamiento-actividad-fijos-discontinuos-comunicacion-42`). Comunicación de la empresa a los trabajadores fijos discontinuos, en catalán, para llamarles a reincorporarse a la actividad en el nuevo periodo, con indicación de fecha y condiciones.
- **Llamamiento a la actividad de fijos discontinuos: comunicación (en euskera)** (`llamamiento-actividad-fijos-discontinuos-comunicacion-44`). Comunicación de la empresa a los trabajadores fijos discontinuos, en euskera, para llamarles a reincorporarse a la actividad en el nuevo periodo, con indicación de fecha y condiciones.
- **Llamamiento a la actividad de fijos discontinuos: comunicación (en gallego)** (`llamamiento-actividad-fijos-discontinuos-comunicacion-43`). Comunicación de la empresa a los trabajadores fijos discontinuos, en gallego, para llamarles a reincorporarse a la actividad en el nuevo periodo, con indicación de fecha y condiciones.
- **Llamamiento a la actividad de fijos discontinuos: comunicación (en valenciano)** (`llamamiento-actividad-fijos-discontinuos-comunicacion-45`). Comunicación de la empresa a los trabajadores fijos discontinuos, en valenciano, para llamarles a reincorporarse a la actividad en el nuevo periodo, con indicación de fecha y condiciones.
- **Llamamiento a la actividad del fijo discontinuo: comunicación de la empresa** (`llamamiento-actividad-fijo-discontinuo-comunicacion-32`). Comunicación de la empresa al trabajador fijo discontinuo para llamarle a reincorporarse a la actividad en el inicio de cada periodo, indicando fecha, centro y condiciones de la reincorporación.
- **Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en catalán)** (`prorroga-contrato-trabajo-acogida-real-decreto-37`). Comunicación al trabajador de la prórroga de su contrato de trabajo acogido a un real decreto, en versión en catalán, con los datos del contrato, de la empresa y del trabajador y la nueva duración.
- **Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en euskera)** (`prorroga-contrato-trabajo-acogida-real-decreto-35`). Comunicación al trabajador de la prórroga de su contrato de trabajo acogido a un real decreto, en versión en euskera, con los datos del contrato, de la empresa y del trabajador y la nueva duración.
- **Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en gallego)** (`prorroga-contrato-trabajo-acogida-real-decreto-36`). Comunicación al trabajador de la prórroga de su contrato de trabajo acogido a un real decreto, en versión en gallego, con los datos del contrato, de la empresa y del trabajador y la nueva duración.
- **Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en valenciano)** (`prorroga-contrato-trabajo-acogida-real-decreto-34`). Comunicación al trabajador de la prórroga de su contrato de trabajo acogido a un real decreto, en versión en valenciano, con los datos del contrato, de la empresa y del trabajador y la nueva duración.

### Escritos y solicitudes (3)

- **Pedir información sobre los elementos esenciales de la relación laboral** (`pedir-informacion-sobre-elementos-esenciales-relacion-10`). Escrito del trabajador a su empresa para solicitar que le informe por escrito de los elementos esenciales de su relación laboral y de las condiciones aplicables a su contrato.
- **Pedir que el contrato de trabajo conste por escrito** (`pedir-contrato-trabajo-conste-escrito-237`). Escrito del trabajador para exigir a la empresa que su contrato de trabajo se formalice por escrito, cuando la relación se está desarrollando sin documento firmado o solo de forma verbal.
- **Pedir trabajar a distancia** (`pedir-trabajar-distancia-182`). Solicitud del trabajador a la empresa para pasar a prestar servicios mediante trabajo a distancia, con indicación de las circunstancias y condiciones en que lo pide.

### Documentos, certificados y modelos oficiales (11)

- **Asistencia a formación: hoja de firmas** (`asistencia-formacion-hoja-firmas-202`). Hoja de control en la que la empresa recoge la acción formativa, sus fechas y el formador, y los trabajadores asistentes firman para acreditar que han recibido la formación.
- **Autónomo que contrata a un familiar: declaración jurada** (`autonomo-contrata-familiar-declaracion-jurada-204`). Declaración jurada que firman el autónomo y su familiar ante la Tesorería General de la Seguridad Social para acreditar que el familiar trabaja como asalariado del titular, según su parentesco y convivencia.
- **Currículum anónimo** (`curriculum-anonimo-210`). Modelo de currículum sin datos identificativos del candidato, para que la selección de personal se base solo en la formación y la experiencia y se evite la discriminación.
- **Declaración responsable de cumplimiento de la reserva de empleo para personas con discapacidad** (`declaracion-responsable-cumplimiento-reserva-empleo-247`). Declaración de la empresa de que cumple la obligación de reservar puestos de trabajo para personas con discapacidad, o de que aplica las medidas alternativas previstas, para presentarla donde se le exija.
- **Información al trabajador sobre los elementos esenciales del contrato** (`informacion-trabajador-sobre-elementos-esenciales-1`). Documento informativo que la empresa entrega al trabajador con los elementos esenciales de su contrato, en castellano. Conviene comprobar que recoge todos los extremos que exige la norma vigente.
- **Información al trabajador sobre los elementos esenciales del contrato (en catalán)** (`informacion-trabajador-sobre-elementos-esenciales-5`). Documento informativo que la empresa entrega al trabajador con los elementos esenciales de su contrato, en versión en catalán. Conviene comprobar que recoge todos los extremos que exige la norma vigente.
- **Información al trabajador sobre los elementos esenciales del contrato (en euskera)** (`informacion-trabajador-sobre-elementos-esenciales-3`). Documento informativo que la empresa entrega al trabajador con los elementos esenciales de su contrato, en versión en euskera. Conviene comprobar que recoge todos los extremos que exige la norma vigente.
- **Información al trabajador sobre los elementos esenciales del contrato (en gallego)** (`informacion-trabajador-sobre-elementos-esenciales-4`). Documento informativo que la empresa entrega al trabajador con los elementos esenciales de su contrato, en versión en gallego. Conviene comprobar que recoge todos los extremos que exige la norma vigente.
- **Información al trabajador sobre los elementos esenciales del contrato (en valenciano)** (`informacion-trabajador-sobre-elementos-esenciales-2`). Documento informativo que la empresa entrega al trabajador con los elementos esenciales de su contrato, en versión valenciana. Conviene comprobar que recoge todos los extremos que exige la norma vigente.
- **Memoria sobre la organización de una empresa de trabajo temporal** (`memoria-sobre-organizacion-empresa-trabajo-temporal-258`). Memoria descriptiva de la organización de una empresa de trabajo temporal, con sus medios y estructura, para acompañar a su solicitud de autorización o a los trámites ante la autoridad laboral.
- **Registro de contratos de puesta a disposición (CPD)** (`registro-contratos-puesta-disposicion-cpd-386`). Relación mensual de contratos de puesta a disposición que la empresa de trabajo temporal remite por vía electrónica al registro de la autoridad laboral, por centro de trabajo, aunque no haya habido contratos.
