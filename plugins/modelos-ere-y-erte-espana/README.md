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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-ere-y-erte-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-ere-y-erte-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-ere-y-erte-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-ere-y-erte-espana:<skill>`.

### Cartas y comunicaciones a la plantilla (17)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 55 | Mecanismo RED: inicio del procedimiento comunicado a la representación de los trabajadores | 2023 | `mecanismo-red-inicio-procedimiento-comunicado-55` |
| 57 | Mecanismo RED: decisión sin acuerdo comunicada a la autoridad laboral | 2023 | `mecanismo-red-decision-sin-acuerdo-comunicada-autoridad-57` |
| 58 | Mecanismo RED: acuerdo comunicado a la autoridad laboral | 2023 | `mecanismo-red-acuerdo-comunicado-autoridad-laboral-58` |
| 60 | Mecanismo RED: inicio del periodo de consultas comunicado a la autoridad laboral | 2023 | `mecanismo-red-inicio-periodo-consultas-comunicado-60` |
| 61 | Mecanismo RED: apertura del periodo de consultas comunicada a la plantilla | 2023 | `mecanismo-red-apertura-periodo-consultas-comunicada-61` |
| 63 | Mecanismo RED: designación de miembros de la comisión negociadora comunicada a la empresa | 2023 | `mecanismo-red-designacion-miembros-comision-negociadora-63` |
| 73 | Cierre de centro en un despido colectivo: aviso a la autoridad laboral | 2023 | `cierre-centro-despido-colectivo-aviso-autoridad-laboral-73` |
| 180 | Prórroga de la suspensión o reducción de jornada por ETOP (ERTE): aviso al trabajador | 2020 | `prorroga-suspension-reduccion-jornada-etop-erte-aviso-180` |
| 185 | Despido colectivo: miembros de la comisión negociadora comunicados a la empresa | 2020 | `despido-colectivo-miembros-comision-negociadora-185` |
| 186 | Despido colectivo: carta a la plantilla para nombrar la comisión negociadora | 2020 | `despido-colectivo-carta-plantilla-nombrar-comision-186` |
| 194 | Fin del ERTE y reincorporación al trabajo: carta al trabajador | 2020 | `fin-erte-reincorporacion-trabajo-carta-trabajador-194` |
| 195 | Fin de las medidas de ERTE: comunicación a la autoridad laboral | 2020 | `fin-medidas-erte-comunicacion-autoridad-laboral-195` |
| 200 | ERTE por fuerza mayor temporal: comunicación al trabajador | 2020 | `erte-fuerza-mayor-temporal-comunicacion-trabajador-200` |
| 250 | ERTE por ETOP: apertura del periodo de consultas comunicada a los trabajadores | 2012 | `erte-etop-apertura-periodo-consultas-comunicada-250` |
| 335 | ERTE por ETOP: suspensión o reducción de jornada comunicada al trabajador | 2017 | `erte-etop-suspension-reduccion-jornada-comunicada-335` |
| 420 | Despido colectivo: inicio del periodo de consultas comunicado a la autoridad laboral | 2014 | `despido-colectivo-inicio-periodo-consultas-comunicado-420` |
| 421 | Reducción de jornada o suspensión de contratos sin representantes: aviso a todos los trabajadores | 2014 | `reduccion-jornada-suspension-contratos-sin-421` |

### Demandas, papeletas y reclamaciones previas (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 179 | Demanda contra la denegación de ERTE por fuerza mayor temporal o Mecanismo RED | 2020 | `demanda-contra-denegacion-erte-fuerza-mayor-temporal-179` |
| 249 | Despido colectivo por fuerza mayor sin resolución administrativa: demanda | 2012 | `despido-colectivo-fuerza-mayor-sin-resolucion-249` |
| 375 | Despido colectivo en grupo mercantil sin cuentas consolidadas: nulidad por falta de documentación | 2015 | `despido-colectivo-grupo-mercantil-sin-cuentas-375` |
| 388 | Despido colectivo: demanda de nulidad por falta de documentación | 2015 | `despido-colectivo-demanda-nulidad-falta-documentacion-388` |
| 389 | Despido colectivo en grupo mercantil con cuentas consolidadas: nulidad por falta de documentación | 2015 | `despido-colectivo-grupo-mercantil-cuentas-consolidadas-389` |
| 391 | Despido colectivo con acuerdo: demanda de sindicatos que no lo firmaron | 2015 | `despido-colectivo-acuerdo-demanda-sindicatos-no-lo-391` |
| 392 | Despido colectivo en grupo laboral: nulidad por tramitarse solo en una empresa | 2015 | `despido-colectivo-grupo-laboral-nulidad-tramitarse-solo-392` |

### Escritos y solicitudes (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 64 | Mecanismo RED: petición de la empresa para constituir la comisión negociadora | 2023 | `mecanismo-red-peticion-empresa-constituir-comision-64` |

### Actas, acuerdos, planes y protocolos (8)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 56 | Mecanismo RED: acta final del periodo de consultas | 2023 | `mecanismo-red-acta-final-periodo-consultas-56` |
| 59 | Mecanismo RED: acuerdo en el periodo de consultas con la representación de los trabajadores | 2023 | `mecanismo-red-acuerdo-periodo-consultas-representacion-59` |
| 62 | Mecanismo RED: acta de designación de la comisión ad hoc | 2023 | `mecanismo-red-acta-designacion-comision-ad-hoc-62` |
| 184 | Despido colectivo: acta de constitución de la comisión negociadora | 2020 | `despido-colectivo-acta-constitucion-comision-negociadora-184` |
| 193 | ERTE por ETOP: acta de designación de la comisión ad hoc | 2020 | `erte-etop-acta-designacion-comision-ad-hoc-193` |
| 198 | Calendario del expediente de regulación de empleo | 2020 | `calendario-expediente-regulacion-empleo-198` |
| 201 | ERTE suspensivo por fuerza mayor temporal: acta de reunión con la representación | 2020 | `erte-suspensivo-fuerza-mayor-temporal-acta-reunion-201` |
| 418 | Acta de consultas del despido colectivo | 2014 | `acta-consultas-despido-colectivo-418` |

### Documentos, certificados y modelos oficiales (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 192 | Declaración responsable de exención de cuotas en ERTE y Mecanismo RED | 2020 | `declaracion-responsable-exencion-cuotas-erte-mecanismo-192` |
| 199 | Lista de trabajadores afectados por expedientes de regulación de empleo | 2020 | `lista-trabajadores-afectados-expedientes-regulacion-199` |
| 419 | Memoria de ejemplo sobre causa productiva en un despido colectivo | 2014 | `memoria-ejemplo-sobre-causa-productiva-despido-colectivo-419` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

