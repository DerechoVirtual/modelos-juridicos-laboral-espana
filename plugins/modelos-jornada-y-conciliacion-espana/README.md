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

## Lista completa de formularios

Cada formulario es una skill. Puedes pedirlo con tus palabras o llamarlo por su nombre (`/modelos-jornada-y-conciliacion-espana:<skill>`). Son 42, agrupados por tipo de escrito:

- **Índice del plugin** (`indice`): te ayuda a elegir el formulario adecuado cuando no sabes cuál usar; le cuentas el caso y te propone uno, o dos o tres para que elijas.

### Contratos, cláusulas y anexos (4)

- **Anexo de horas complementarias (contrato a tiempo parcial) (en catalán)** (`anexo-horas-complementarias-contrato-tiempo-parcial-40`). Anexo al contrato a tiempo parcial, en catalán, para pactar con el trabajador las horas complementarias: su número, su distribución y el preaviso con que la empresa podrá exigirlas.
- **Anexo de horas complementarias (contrato a tiempo parcial) (en euskera)** (`anexo-horas-complementarias-contrato-tiempo-parcial-39`). Anexo al contrato a tiempo parcial, en euskera, para pactar con el trabajador las horas complementarias: su número, su distribución y el preaviso con que la empresa podrá exigirlas.
- **Anexo de horas complementarias (contrato a tiempo parcial) (en gallego)** (`anexo-horas-complementarias-contrato-tiempo-parcial-41`). Anexo al contrato a tiempo parcial, en gallego, para pactar con el trabajador las horas complementarias: su número, su distribución y el preaviso con que la empresa podrá exigirlas.
- **Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano)** (`anexo-horas-complementarias-contrato-tiempo-parcial-38`). Anexo al contrato a tiempo parcial, en valenciano, para pactar con el trabajador las horas complementarias: su número, su distribución y el preaviso con que la empresa podrá exigirlas.

### Cartas y comunicaciones a la plantilla (11)

- **Ausentarse o reducir jornada: aviso del trabajador** (`ausentarse-reducir-jornada-aviso-trabajador-347`). Aviso del trabajador a la empresa de que se ausenta o reduce su jornada por un motivo legal, con las fechas y la forma de disfrute, para que quede constancia y se organice el trabajo.
- **Aviso de ausencia por fuerza mayor ante enfermedad o accidente de un familiar: carta** (`aviso-ausencia-fuerza-mayor-ante-enfermedad-accidente-93`). Carta del trabajador a la empresa avisando de que se ausenta por fuerza mayor ante la enfermedad o el accidente de un familiar, para justificar su falta y solicitar el permiso correspondiente.
- **Disfrute de permiso retribuido: comunicación del trabajador** (`disfrute-permiso-retribuido-comunicacion-trabajador-374`). Comunicación del trabajador a la empresa para avisar de que va a disfrutar un permiso retribuido, indicando el motivo, las fechas y la documentación que lo justifica.
- **Distribución irregular de la jornada: carta al trabajador** (`distribucion-irregular-jornada-carta-trabajador-381`). Carta de la empresa al trabajador para comunicarle la distribución irregular de su jornada a lo largo del año, con el preaviso, el reparto de horas y las condiciones de aplicación.
- **Pedir excedencia: carta** (`pedir-excedencia-carta-334`). Carta del trabajador a la empresa para pedir una excedencia, indicando su clase, la fecha de inicio y la duración que solicita, para que la empresa la conceda o conteste.
- **Propuesta de turnos de guardia al trabajador** (`propuesta-turnos-guardia-trabajador-29`). Carta de la empresa al trabajador para proponerle los turnos de guardia que deberá cubrir, indicando su régimen, fechas y condiciones, y pidiéndole su conformidad.
- **Reincorporación tras excedencia: comunicación del trabajador** (`reincorporacion-tras-excedencia-comunicacion-trabajador-243`). Comunicación del trabajador a la empresa para solicitar su reincorporación al terminar la excedencia, indicando la fecha en que quiere volver y reclamando el puesto o vacante que le corresponda.
- **Resumen mensual de horas de trabajo: comunicación** (`resumen-mensual-horas-trabajo-comunicacion-48`). Comunicación de la empresa al trabajador con el resumen mensual de las horas de trabajo registradas, para que conozca la jornada computada y pueda comprobarla o formular observaciones.
- **Revertir el trabajo a distancia: comunicación de la decisión** (`revertir-trabajo-distancia-comunicacion-decision-153`). Comunicación de la empresa al trabajador por la que le informa de la decisión de revertir su trabajo a distancia y de volver a la prestación presencial, con la fecha y las condiciones del cambio.
- **Suspensión del contrato por nacimiento, adopción o acogimiento: carta a la empresa** (`suspension-contrato-nacimiento-adopcion-acogimiento-131`). Carta del trabajador a la empresa para comunicar que suspende su contrato por nacimiento, adopción o acogimiento, con las fechas de inicio y fin del periodo de suspensión que va a disfrutar.
- **Suspensión del contrato por violencia de género o sexual: carta a la empresa** (`suspension-contrato-violencia-genero-sexual-carta-130`). Carta de la trabajadora o el trabajador a la empresa para comunicar la suspensión de su contrato por ser víctima de violencia de género o sexual, indicando la fecha de inicio y la duración prevista.

### Demandas, papeletas y reclamaciones previas (4)

- **Conciliación laboral, personal y familiar: demanda genérica de derechos** (`conciliacion-laboral-personal-familiar-demanda-generica-124`). Demanda genérica del trabajador ante la Sección de lo Social del Tribunal de Instancia para reclamar derechos de conciliación de la vida laboral, personal y familiar que la empresa le ha negado.
- **Demanda de adaptación de jornada por conciliación** (`demanda-adaptacion-jornada-conciliacion-49`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia para que se reconozca su derecho a adaptar la jornada por motivos de conciliación, frente a la negativa de la empresa.
- **Prórroga de excedencia voluntaria: demanda de reconocimiento** (`prorroga-excedencia-voluntaria-demanda-reconocimiento-176`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia para que se reconozca su derecho a prorrogar la excedencia voluntaria que disfruta, frente a la negativa de la empresa.
- **Trabajo a distancia: demanda por acceso, revisión o modificación** (`trabajo-distancia-demanda-acceso-revision-modificacion-148`). Demanda del trabajador ante la Sección de lo Social del Tribunal de Instancia para que se reconozca su derecho a acceder al trabajo a distancia, o a revisarlo o modificarlo, frente a la negativa de la empresa.

### Recursos (1)

- **Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso** (`suplicacion-procedimiento-acceso-reversion-modificacion-147`). Recurso de suplicación contra la sentencia dictada en un proceso sobre acceso, reversión o modificación del trabajo a distancia, para que el tribunal superior revise la resolución y estime la pretensión.

### Escritos y solicitudes (14)

- **Compensar horas extra con descanso: petición del trabajador** (`compensar-horas-extra-descanso-peticion-trabajador-240`). Petición del trabajador a la empresa para compensar con tiempo de descanso las horas extraordinarias realizadas, en lugar de cobrarlas, indicando las horas y los días de descanso que solicita.
- **Pedir adaptación de jornada por conciliación** (`pedir-adaptacion-jornada-conciliacion-196`). Solicitud del trabajador a la empresa para adaptar su jornada por motivos de conciliación, con la propuesta concreta de horario, la justificación y el periodo de la adaptación.
- **Pedir adaptación de jornada por cuidado de familiares tras la DANA** (`pedir-adaptacion-jornada-cuidado-familiares-tras-dana-20`). Solicitud del trabajador a la empresa para adaptar su jornada y atender al cuidado de familiares tras la DANA, en el marco de las medidas excepcionales aprobadas para los afectados.
- **Pedir adaptación de jornada por violencia de género, sexual o terrorismo** (`pedir-adaptacion-jornada-violencia-genero-sexual-231`). Solicitud de la persona trabajadora víctima de violencia de género, violencia sexual o terrorismo para que la empresa adapte su jornada o su horario como medida de protección y atención.
- **Pedir días de vacaciones** (`pedir-dias-vacaciones-245`). Solicitud del trabajador a la empresa para disfrutar de días de vacaciones en las fechas que propone, para que se las conceda o proponga alternativas dentro del calendario de la empresa.
- **Pedir justificante de ausencia al trabajador** (`pedir-justificante-ausencia-trabajador-400`). Requerimiento de la empresa al trabajador para que justifique una ausencia al trabajo, aportando el justificante o explicando el motivo en el plazo que se le conceda.
- **Pedir permiso para informes psicológicos y sociales de adopción** (`pedir-permiso-informes-psicologicos-sociales-adopcion-397`). Solicitud del trabajador a la empresa de un permiso para asistir a los informes psicológicos y sociales necesarios en un procedimiento de adopción, con el justificante de las citaciones.
- **Pedir permiso para sesiones informativas previas a la adopción** (`pedir-permiso-sesiones-informativas-previas-adopcion-398`). Solicitud del trabajador a la empresa de un permiso para asistir a las sesiones informativas previas a la adopción, indicando las fechas y aportando el justificante de la convocatoria.
- **Pedir permiso por registro de pareja de hecho** (`pedir-permiso-registro-pareja-hecho-67`). Solicitud del trabajador a la empresa del permiso retribuido por registro de pareja de hecho, indicando la fecha del registro y los días que quiere disfrutar, con la documentación acreditativa.
- **Pedir permiso retribuido por fallecimiento de familiar en incendios forestales** (`pedir-permiso-retribuido-fallecimiento-familiar-14`). Solicitud del trabajador a la empresa de un permiso retribuido por el fallecimiento de un familiar a causa de los incendios forestales, al amparo de la norma excepcional dictada para los afectados.
- **Pedir permiso retribuido por la DANA** (`pedir-permiso-retribuido-dana-21`). Solicitud del trabajador a la empresa de un permiso retribuido para atender las consecuencias de la DANA, en el marco de las medidas excepcionales aprobadas para los afectados.
- **Pedir trabajo a distancia como víctima de violencia de género** (`pedir-trabajo-distancia-como-victima-violencia-genero-156`). Solicitud de la trabajadora víctima de violencia de género para que la empresa le permita trabajar a distancia, como medida de protección, indicando la situación y las condiciones que propone.
- **Pedir trabajo a distancia por estudios** (`pedir-trabajo-distancia-estudios-157`). Solicitud del trabajador a la empresa para trabajar a distancia por motivos de estudios, con la justificación de los estudios que cursa y la propuesta de las condiciones del trabajo remoto.
- **Pedir trabajo a distancia por la DANA** (`pedir-trabajo-distancia-dana-23`). Solicitud del trabajador a la empresa para pasar a trabajar a distancia como consecuencia de la DANA, en el marco de las medidas excepcionales aprobadas para los afectados.

### Actas, acuerdos, planes y protocolos (5)

- **Cambio de jornada completa a parcial o al revés: acuerdo** (`cambio-jornada-completa-parcial-reves-acuerdo-236`). Acuerdo entre la empresa y el trabajador para cambiar su jornada de completa a parcial, o de parcial a completa, fijando la nueva jornada, el horario y la fecha de efectos.
- **Desconexión digital: protocolo** (`desconexion-digital-protocolo-127`). Protocolo que la empresa aprueba para garantizar el derecho a la desconexión digital de la plantilla fuera del tiempo de trabajo, con las pautas de uso de medios digitales y las medidas de aplicación.
- **Distribución irregular de la jornada: acuerdo con la representación** (`distribucion-irregular-jornada-acuerdo-representacion-234`). Acuerdo entre la empresa y la representación de los trabajadores para distribuir de forma irregular la jornada a lo largo del año, fijando el porcentaje, los límites y el preaviso aplicables.
- **Personal de libre disponibilidad y registro de jornada: acuerdo con la representación** (`personal-libre-disponibilidad-registro-jornada-acuerdo-230`). Acuerdo entre la empresa y la representación de los trabajadores sobre el personal de libre disponibilidad y el modo de registrar su jornada, para dejar fijado el sistema aplicable.
- **Registro de jornada diaria** (`registro-jornada-diaria-361`). Registro diario de jornada en el que se anotan la hora de inicio y fin de la prestación de cada trabajador, para cumplir la obligación de la empresa de registrar la jornada.

### Documentos, certificados y modelos oficiales (2)

- **Declaración del hogar familiar sobre reducción de servicios por la DANA** (`declaracion-hogar-familiar-sobre-reduccion-servicios-24`). Declaración del hogar familiar sobre la reducción de servicios por la DANA, que acredita la situación del empleado de hogar o de su entorno para justificar las medidas excepcionales aplicables.
- **Declaración responsable de trabajadores fuera del permiso retribuido recuperable del RDL 10/2020** (`declaracion-responsable-trabajadores-fuera-permiso-197`). Declaración responsable del trabajador de que no estaba incluido en el permiso retribuido recuperable previsto en el RDL 10/2020, norma excepcional de 2020 sin aplicación actual; sirve como modelo histórico.

### Otros (1)

- **Respuesta de la empresa al permiso retribuido por la DANA** (`respuesta-empresa-permiso-retribuido-dana-22`). Respuesta de la empresa a la solicitud de permiso retribuido por la DANA presentada por un trabajador, en la que comunica si lo concede y en qué condiciones, o razona su negativa.
