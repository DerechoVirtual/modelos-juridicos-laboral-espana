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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-proceso-laboral-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-proceso-laboral-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-proceso-laboral-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-proceso-laboral-espana:<skill>`.

### Demandas, papeletas y reclamaciones previas (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 47 | Monitorio laboral: escrito del demandante tras la oposición de la empresa | 2024 | `monitorio-laboral-escrito-demandante-tras-oposicion-47` |
| 117 | Falso autónomo: demanda de reconocimiento de relación laboral | 2023 | `falso-autonomo-demanda-reconocimiento-relacion-laboral-117` |
| 181 | Falso autónomo: papeleta de conciliación previa en el SMAC | 2020 | `falso-autonomo-papeleta-conciliacion-previa-smac-181` |
| 187 | Revisión y declaración de error judicial: demanda | 2020 | `revision-declaracion-error-judicial-demanda-187` |
| 244 | Incumplimiento de precontrato de trabajo: demanda de daños y perjuicios | 2018 | `incumplimiento-precontrato-trabajo-demanda-danos-244` |
| 303 | Reconocimiento de relación laboral con una entidad pública: demanda | 2017 | `reconocimiento-relacion-laboral-entidad-publica-demanda-303` |
| 304 | Personal laboral temporal irregular de entidades públicas: demanda para ser fijo | 2017 | `personal-laboral-temporal-irregular-entidades-publicas-304` |

### Recursos (5)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 188 | Revisión contra decretos del LAJ: recurso | 2020 | `revision-contra-decretos-laj-recurso-188` |
| 351 | Suplicación: formalización del recurso | 2017 | `suplicacion-formalizacion-recurso-351` |
| 367 | Anunciar recurso de suplicación | 2016 | `anunciar-recurso-suplicacion-367` |
| 401 | Reposición contra la acumulación indebida de acciones: recurso | 2015 | `reposicion-contra-acumulacion-indebida-acciones-recurso-401` |
| 404 | Reposición contra la acumulación de procesos: recurso | 2015 | `reposicion-contra-acumulacion-procesos-recurso-404` |

### Escritos y solicitudes (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 17 | Pedir la conciliación anticipada ante el tribunal | 2025 | `pedir-conciliacion-anticipada-ante-tribunal-17` |
| 18 | Reiniciar la ejecución laboral: escrito | 2025 | `reiniciar-ejecucion-laboral-escrito-18` |
| 122 | Embargo preventivo de bienes tras la demanda: medida cautelar | 2022 | `embargo-preventivo-bienes-tras-demanda-medida-cautelar-122` |
| 163 | Impugnar la liquidación de intereses en la ejecución laboral | 2021 | `impugnar-liquidacion-intereses-ejecucion-laboral-163` |
| 254 | Ejecución del acuerdo de conciliación judicial (decreto del LAJ) | 2018 | `ejecucion-acuerdo-conciliacion-judicial-decreto-laj-254` |
| 260 | Conclusiones complementarias sucintas | 2017 | `conclusiones-complementarias-sucintas-260` |
| 359 | Pedir embargo | 2017 | `pedir-embargo-359` |
| 360 | Cambio de partes en la ejecución por sucesión empresarial: escrito | 2016 | `cambio-partes-ejecucion-sucesion-empresarial-escrito-360` |
| 362 | Pedir declaración de insolvencia | 2016 | `pedir-declaracion-insolvencia-362` |
| 363 | Pedir apremio pecuniario o multa coercitiva | 2016 | `pedir-apremio-pecuniario-multa-coercitiva-363` |
| 364 | Pedir suspensión o aplazamiento de la ejecución | 2016 | `pedir-suspension-aplazamiento-ejecucion-364` |
| 365 | Ejecución de sentencia o acta de conciliación firme: solicitud | 2016 | `ejecucion-sentencia-acta-conciliacion-firme-solicitud-365` |
| 366 | Ejecución provisional de sentencia: solicitud | 2016 | `ejecucion-provisional-sentencia-solicitud-366` |
| 372 | Pedir acumulación de procesos ante el mismo o distinto tribunal | 2016 | `pedir-acumulacion-procesos-ante-mismo-distinto-tribunal-372` |
| 373 | Pedir actos preparatorios o prueba anticipada | 2016 | `pedir-actos-preparatorios-prueba-anticipada-373` |
| 411 | Multas coercitivas a terceros por incumplir en la ejecución de sentencia laboral: solicitud | 2015 | `multas-coercitivas-terceros-incumplir-ejecucion-411` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

