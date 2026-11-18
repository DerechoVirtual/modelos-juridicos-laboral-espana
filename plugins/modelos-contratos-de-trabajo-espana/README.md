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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 7.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-contratos-de-trabajo-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-contratos-de-trabajo-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-contratos-de-trabajo-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-contratos-de-trabajo-espana:<skill>`.

### Contratos, cláusulas y anexos (59)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 46 | Novación de fijo discontinuo a indefinido ordinario: acuerdo | 2024 | `novacion-fijo-discontinuo-indefinido-ordinario-acuerdo-46` |
| 66 | Contrato indefinido del Plan de Recuperación (en valenciano) | 2023 | `contrato-indefinido-plan-recuperacion-valenciano-66` |
| 68 | Contrato de trabajo de pescadores (en inglés) | 2023 | `contrato-trabajo-pescadores-ingles-68` |
| 69 | Contrato de trabajo de pescadores (en euskera) | 2023 | `contrato-trabajo-pescadores-euskera-69` |
| 70 | Contrato de trabajo de pescadores (en catalán) | 2023 | `contrato-trabajo-pescadores-catalan-70` |
| 71 | Contrato de trabajo de pescadores (en gallego) | 2023 | `contrato-trabajo-pescadores-gallego-71` |
| 72 | Contrato de trabajo de pescadores (en valenciano) | 2023 | `contrato-trabajo-pescadores-valenciano-72` |
| 74 | Contrato indefinido del Plan de Recuperación (en catalán) | 2023 | `contrato-indefinido-plan-recuperacion-catalan-74` |
| 75 | Contrato indefinido del Plan de Recuperación (en euskera) | 2023 | `contrato-indefinido-plan-recuperacion-euskera-75` |
| 76 | Contrato indefinido del Plan de Recuperación (en gallego) | 2023 | `contrato-indefinido-plan-recuperacion-gallego-76` |
| 77 | Contrato indefinido del Plan de Recuperación | 2023 | `contrato-indefinido-plan-recuperacion-77` |
| 78 | Contrato de formación en alternancia del Plan de Recuperación (en valenciano) | 2023 | `contrato-formacion-alternancia-plan-recuperacion-78` |
| 79 | Contrato formativo de práctica profesional del Plan de Recuperación (en valenciano) | 2023 | `contrato-formativo-practica-profesional-plan-79` |
| 80 | Contrato formativo de práctica profesional del Plan de Recuperación (en catalán) | 2023 | `contrato-formativo-practica-profesional-plan-80` |
| 81 | Contrato de formación en alternancia del Plan de Recuperación (en euskera) | 2023 | `contrato-formacion-alternancia-plan-recuperacion-euskera-81` |
| 82 | Contrato de formación en alternancia del Plan de Recuperación (en catalán) | 2023 | `contrato-formacion-alternancia-plan-recuperacion-catalan-82` |
| 83 | Contrato de formación en alternancia del Plan de Recuperación (en gallego) | 2023 | `contrato-formacion-alternancia-plan-recuperacion-gallego-83` |
| 84 | Contrato formativo de práctica profesional del Plan de Recuperación (en euskera) | 2023 | `contrato-formativo-practica-profesional-plan-84` |
| 85 | Contrato formativo de práctica profesional del Plan de Recuperación (en gallego) | 2023 | `contrato-formativo-practica-profesional-plan-85` |
| 86 | Contrato formativo de práctica profesional del Plan de Recuperación | 2023 | `contrato-formativo-practica-profesional-plan-86` |
| 87 | Contrato de formación en alternancia del Plan de Recuperación | 2023 | `contrato-formacion-alternancia-plan-recuperacion-87` |
| 88 | Contrato temporal del Plan de Recuperación (en valenciano) | 2023 | `contrato-temporal-plan-recuperacion-valenciano-88` |
| 89 | Contrato temporal del Plan de Recuperación (en gallego) | 2023 | `contrato-temporal-plan-recuperacion-gallego-89` |
| 90 | Contrato temporal del Plan de Recuperación (en euskera) | 2023 | `contrato-temporal-plan-recuperacion-euskera-90` |
| 91 | Contrato temporal del Plan de Recuperación (en catalán) | 2023 | `contrato-temporal-plan-recuperacion-catalan-91` |
| 92 | Contrato temporal del Plan de Recuperación | 2023 | `contrato-temporal-plan-recuperacion-92` |
| 96 | Contrato formativo para la práctica profesional (en valenciano) | 2023 | `contrato-formativo-practica-profesional-valenciano-96` |
| 97 | Contrato formativo para la práctica profesional (en catalán) | 2023 | `contrato-formativo-practica-profesional-catalan-97` |
| 98 | Contrato formativo para la práctica profesional (en gallego) | 2023 | `contrato-formativo-practica-profesional-gallego-98` |
| 99 | Contrato formativo para la práctica profesional (en euskera) | 2023 | `contrato-formativo-practica-profesional-euskera-99` |
| 103 | Contrato formativo en alternancia (en catalán) | 2023 | `contrato-formativo-alternancia-catalan-103` |
| 104 | Contrato formativo en alternancia (en gallego) | 2023 | `contrato-formativo-alternancia-gallego-104` |
| 105 | Contrato formativo en alternancia (en euskera) | 2023 | `contrato-formativo-alternancia-euskera-105` |
| 106 | Contrato formativo en alternancia (en valenciano) | 2023 | `contrato-formativo-alternancia-valenciano-106` |
| 109 | Contrato laboral temporal (en valenciano) | 2023 | `contrato-laboral-temporal-valenciano-109` |
| 110 | Contrato laboral temporal (en gallego) | 2023 | `contrato-laboral-temporal-gallego-110` |
| 111 | Contrato laboral temporal (en euskera) | 2023 | `contrato-laboral-temporal-euskera-111` |
| 112 | Contrato laboral temporal (en catalán) | 2023 | `contrato-laboral-temporal-catalan-112` |
| 113 | Contrato laboral indefinido (en gallego) | 2023 | `contrato-laboral-indefinido-gallego-113` |
| 114 | Contrato laboral indefinido (en euskera) | 2023 | `contrato-laboral-indefinido-euskera-114` |
| 115 | Contrato laboral indefinido (en valenciano) | 2023 | `contrato-laboral-indefinido-valenciano-115` |
| 116 | Contrato laboral indefinido (en catalán) | 2023 | `contrato-laboral-indefinido-catalan-116` |
| 132 | Contrato de actuación de toreros, novilleros y rejoneadores | 2022 | `contrato-actuacion-toreros-novilleros-rejoneadores-132` |
| 133 | Contrato laboral de colaboración para formar una cuadrilla | 2022 | `contrato-laboral-colaboracion-formar-cuadrilla-133` |
| 135 | Plan individual de formación | 2022 | `plan-individual-formacion-135` |
| 137 | Contrato de artistas de duración determinada (relación laboral especial) | 2022 | `contrato-artistas-duracion-determinada-relacion-laboral-137` |
| 138 | Contrato de personal técnico y auxiliar artístico de duración determinada | 2022 | `contrato-personal-tecnico-auxiliar-artistico-duracion-138` |
| 144 | Contrato de servicios profesionales | 2022 | `contrato-servicios-profesionales-144` |
| 178 | Contrato de trabajo de pescadores | 2020 | `contrato-trabajo-pescadores-178` |
| 207 | Plan formativo | 2019 | `plan-formativo-207` |
| 229 | Cláusulas adicionales del contrato de grupo | 2019 | `clausulas-adicionales-contrato-grupo-229` |
| 248 | Contrato del autónomo económicamente dependiente (TRADE) | 2018 | `contrato-autonomo-economicamente-dependiente-trade-248` |
| 342 | Cláusulas adicionales del contrato de trabajo | 2017 | `clausulas-adicionales-contrato-trabajo-342` |
| 378 | Contrato de patrón de embarcaciones de recreo | 2016 | `contrato-patron-embarcaciones-recreo-378` |
| 385 | Puesta a disposición: contrato | 2015 | `puesta-disposicion-contrato-385` |
| 412 | Acuerdo con voluntarios | 2015 | `acuerdo-voluntarios-412` |
| 413 | Contrato de interinidad de profesor de religión | 2015 | `contrato-interinidad-profesor-religion-413` |
| 414 | Contrato indefinido de profesor de religión | 2015 | `contrato-indefinido-profesor-religion-414` |
| 415 | Contrato de personal civil de establecimientos militares | 2015 | `contrato-personal-civil-establecimientos-militares-415` |

### Cartas y comunicaciones a la plantilla (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 9 | Información al trabajador sobre los elementos esenciales del contrato: carta | 2026 | `informacion-trabajador-sobre-elementos-esenciales-9` |
| 32 | Llamamiento a la actividad del fijo discontinuo: comunicación de la empresa | 2024 | `llamamiento-actividad-fijo-discontinuo-comunicacion-32` |
| 34 | Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en valenciano) | 2024 | `prorroga-contrato-trabajo-acogida-real-decreto-34` |
| 35 | Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en euskera) | 2024 | `prorroga-contrato-trabajo-acogida-real-decreto-35` |
| 36 | Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en gallego) | 2024 | `prorroga-contrato-trabajo-acogida-real-decreto-36` |
| 37 | Prórroga del contrato de trabajo acogida al Real Decreto: comunicación (en catalán) | 2024 | `prorroga-contrato-trabajo-acogida-real-decreto-37` |
| 42 | Llamamiento a la actividad de fijos discontinuos: comunicación (en catalán) | 2024 | `llamamiento-actividad-fijos-discontinuos-comunicacion-42` |
| 43 | Llamamiento a la actividad de fijos discontinuos: comunicación (en gallego) | 2024 | `llamamiento-actividad-fijos-discontinuos-comunicacion-43` |
| 44 | Llamamiento a la actividad de fijos discontinuos: comunicación (en euskera) | 2024 | `llamamiento-actividad-fijos-discontinuos-comunicacion-44` |
| 45 | Llamamiento a la actividad de fijos discontinuos: comunicación (en valenciano) | 2024 | `llamamiento-actividad-fijos-discontinuos-comunicacion-45` |
| 353 | Interrupción de actividad del TRADE: comunicación | 2017 | `interrupcion-actividad-trade-comunicacion-353` |

### Escritos y solicitudes (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 10 | Pedir información sobre los elementos esenciales de la relación laboral | 2026 | `pedir-informacion-sobre-elementos-esenciales-relacion-10` |
| 182 | Pedir trabajar a distancia | 2020 | `pedir-trabajar-distancia-182` |
| 237 | Pedir que el contrato de trabajo conste por escrito | 2019 | `pedir-contrato-trabajo-conste-escrito-237` |

### Documentos, certificados y modelos oficiales (11)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 1 | Información al trabajador sobre los elementos esenciales del contrato | 2026 | `informacion-trabajador-sobre-elementos-esenciales-1` |
| 2 | Información al trabajador sobre los elementos esenciales del contrato (en valenciano) | 2026 | `informacion-trabajador-sobre-elementos-esenciales-2` |
| 3 | Información al trabajador sobre los elementos esenciales del contrato (en euskera) | 2026 | `informacion-trabajador-sobre-elementos-esenciales-3` |
| 4 | Información al trabajador sobre los elementos esenciales del contrato (en gallego) | 2026 | `informacion-trabajador-sobre-elementos-esenciales-4` |
| 5 | Información al trabajador sobre los elementos esenciales del contrato (en catalán) | 2026 | `informacion-trabajador-sobre-elementos-esenciales-5` |
| 202 | Asistencia a formación: hoja de firmas | 2020 | `asistencia-formacion-hoja-firmas-202` |
| 204 | Autónomo que contrata a un familiar: declaración jurada | 2019 | `autonomo-contrata-familiar-declaracion-jurada-204` |
| 210 | Currículum anónimo | 2019 | `curriculum-anonimo-210` |
| 247 | Declaración responsable de cumplimiento de la reserva de empleo para personas con discapacidad | 2018 | `declaracion-responsable-cumplimiento-reserva-empleo-247` |
| 258 | Memoria sobre la organización de una empresa de trabajo temporal | 2017 | `memoria-sobre-organizacion-empresa-trabajo-temporal-258` |
| 386 | Registro de contratos de puesta a disposición (CPD) | 2015 | `registro-contratos-puesta-disposicion-cpd-386` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

