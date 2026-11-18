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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 4.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-jornada-y-conciliacion-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-jornada-y-conciliacion-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-jornada-y-conciliacion-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-jornada-y-conciliacion-espana:<skill>`.

### Contratos, cláusulas y anexos (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 38 | Anexo de horas complementarias (contrato a tiempo parcial) (en valenciano) | 2024 | `anexo-horas-complementarias-contrato-tiempo-parcial-38` |
| 39 | Anexo de horas complementarias (contrato a tiempo parcial) (en euskera) | 2024 | `anexo-horas-complementarias-contrato-tiempo-parcial-39` |
| 40 | Anexo de horas complementarias (contrato a tiempo parcial) (en catalán) | 2024 | `anexo-horas-complementarias-contrato-tiempo-parcial-40` |
| 41 | Anexo de horas complementarias (contrato a tiempo parcial) (en gallego) | 2024 | `anexo-horas-complementarias-contrato-tiempo-parcial-41` |

### Cartas y comunicaciones a la plantilla (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 29 | Propuesta de turnos de guardia al trabajador | 2024 | `propuesta-turnos-guardia-trabajador-29` |
| 48 | Resumen mensual de horas de trabajo: comunicación | 2024 | `resumen-mensual-horas-trabajo-comunicacion-48` |
| 93 | Aviso de ausencia por fuerza mayor ante enfermedad o accidente de un familiar: carta | 2023 | `aviso-ausencia-fuerza-mayor-ante-enfermedad-accidente-93` |
| 130 | Suspensión del contrato por violencia de género o sexual: carta a la empresa | 2022 | `suspension-contrato-violencia-genero-sexual-carta-130` |
| 131 | Suspensión del contrato por nacimiento, adopción o acogimiento: carta a la empresa | 2022 | `suspension-contrato-nacimiento-adopcion-acogimiento-131` |
| 153 | Revertir el trabajo a distancia: comunicación de la decisión | 2021 | `revertir-trabajo-distancia-comunicacion-decision-153` |
| 243 | Reincorporación tras excedencia: comunicación del trabajador | 2019 | `reincorporacion-tras-excedencia-comunicacion-trabajador-243` |
| 334 | Pedir excedencia: carta | 2017 | `pedir-excedencia-carta-334` |
| 347 | Ausentarse o reducir jornada: aviso del trabajador | 2017 | `ausentarse-reducir-jornada-aviso-trabajador-347` |
| 374 | Disfrute de permiso retribuido: comunicación del trabajador | 2016 | `disfrute-permiso-retribuido-comunicacion-trabajador-374` |
| 381 | Distribución irregular de la jornada: carta al trabajador | 2016 | `distribucion-irregular-jornada-carta-trabajador-381` |

### Demandas, papeletas y reclamaciones previas (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 49 | Demanda de adaptación de jornada por conciliación | 2024 | `demanda-adaptacion-jornada-conciliacion-49` |
| 124 | Conciliación laboral, personal y familiar: demanda genérica de derechos | 2022 | `conciliacion-laboral-personal-familiar-demanda-generica-124` |
| 148 | Trabajo a distancia: demanda por acceso, revisión o modificación | 2021 | `trabajo-distancia-demanda-acceso-revision-modificacion-148` |
| 176 | Prórroga de excedencia voluntaria: demanda de reconocimiento | 2020 | `prorroga-excedencia-voluntaria-demanda-reconocimiento-176` |

### Recursos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 147 | Suplicación en procedimiento de acceso, reversión o modificación del trabajo a distancia: recurso | 2021 | `suplicacion-procedimiento-acceso-reversion-modificacion-147` |

### Escritos y solicitudes (14)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 14 | Pedir permiso retribuido por fallecimiento de familiar en incendios forestales | 2026 | `pedir-permiso-retribuido-fallecimiento-familiar-14` |
| 20 | Pedir adaptación de jornada por cuidado de familiares tras la DANA | 2024 | `pedir-adaptacion-jornada-cuidado-familiares-tras-dana-20` |
| 21 | Pedir permiso retribuido por la DANA | 2024 | `pedir-permiso-retribuido-dana-21` |
| 23 | Pedir trabajo a distancia por la DANA | 2024 | `pedir-trabajo-distancia-dana-23` |
| 67 | Pedir permiso por registro de pareja de hecho | 2023 | `pedir-permiso-registro-pareja-hecho-67` |
| 156 | Pedir trabajo a distancia como víctima de violencia de género | 2021 | `pedir-trabajo-distancia-como-victima-violencia-genero-156` |
| 157 | Pedir trabajo a distancia por estudios | 2021 | `pedir-trabajo-distancia-estudios-157` |
| 196 | Pedir adaptación de jornada por conciliación | 2020 | `pedir-adaptacion-jornada-conciliacion-196` |
| 231 | Pedir adaptación de jornada por violencia de género, sexual o terrorismo | 2019 | `pedir-adaptacion-jornada-violencia-genero-sexual-231` |
| 240 | Compensar horas extra con descanso: petición del trabajador | 2019 | `compensar-horas-extra-descanso-peticion-trabajador-240` |
| 245 | Pedir días de vacaciones | 2018 | `pedir-dias-vacaciones-245` |
| 397 | Pedir permiso para informes psicológicos y sociales de adopción | 2015 | `pedir-permiso-informes-psicologicos-sociales-adopcion-397` |
| 398 | Pedir permiso para sesiones informativas previas a la adopción | 2015 | `pedir-permiso-sesiones-informativas-previas-adopcion-398` |
| 400 | Pedir justificante de ausencia al trabajador | 2015 | `pedir-justificante-ausencia-trabajador-400` |

### Actas, acuerdos, planes y protocolos (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 127 | Desconexión digital: protocolo | 2022 | `desconexion-digital-protocolo-127` |
| 230 | Personal de libre disponibilidad y registro de jornada: acuerdo con la representación | 2019 | `personal-libre-disponibilidad-registro-jornada-acuerdo-230` |
| 234 | Distribución irregular de la jornada: acuerdo con la representación | 2019 | `distribucion-irregular-jornada-acuerdo-representacion-234` |
| 236 | Cambio de jornada completa a parcial o al revés: acuerdo | 2019 | `cambio-jornada-completa-parcial-reves-acuerdo-236` |
| 361 | Registro de jornada diaria | 2016 | `registro-jornada-diaria-361` |

### Documentos, certificados y modelos oficiales (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 24 | Declaración del hogar familiar sobre reducción de servicios por la DANA | 2024 | `declaracion-hogar-familiar-sobre-reduccion-servicios-24` |
| 197 | Declaración responsable de trabajadores fuera del permiso retribuido recuperable del RDL 10/2020 | 2020 | `declaracion-responsable-trabajadores-fuera-permiso-197` |

### Otros (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 22 | Respuesta de la empresa al permiso retribuido por la DANA | 2024 | `respuesta-empresa-permiso-retribuido-dana-22` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

