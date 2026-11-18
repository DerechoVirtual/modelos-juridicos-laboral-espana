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

- **Dónde funciona:** en Claude Code, en la terminal o en la pestaña Code de la app de Claude. Desde esta carpeta no se puede instalar en el chat ni en Cowork: para eso habría que publicarlo en un repositorio de GitHub.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él, igual que los plugins de Jurisprudenciator del directorio de Claude. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 2.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-salario-y-condiciones-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-salario-y-condiciones-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-salario-y-condiciones-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-salario-y-condiciones-espana:<skill>`.

### Contratos, cláusulas y anexos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 346 | Préstamo de la empresa al trabajador: contrato | 2017 | `prestamo-empresa-trabajador-contrato-346` |

### Cartas y comunicaciones a la plantilla (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 101 | Modificación sustancial: comunicación de los miembros de la comisión negociadora | 2023 | `modificacion-sustancial-comunicacion-miembros-comision-101` |
| 356 | Sucesión en la contrata: aviso de la empresa a la representación de los trabajadores | 2013 | `sucesion-contrata-aviso-empresa-representacion-356` |
| 357 | Sucesión de empresa: aviso al trabajador | 2017 | `sucesion-empresa-aviso-trabajador-357` |
| 379 | Compensación y absorción sin subida de salario: aviso al trabajador | 2016 | `compensacion-absorcion-sin-subida-salario-aviso-379` |

### Demandas, papeletas y reclamaciones previas (10)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 28 | Demanda de traslado por violencia de género, sexual o terrorismo, salud o traslado del cónyuge | 2024 | `demanda-traslado-violencia-genero-sexual-terrorismo-28` |
| 31 | Reclamación de cantidad de la empresa al trabajador: demanda | 2024 | `reclamacion-cantidad-empresa-trabajador-demanda-31` |
| 120 | Extinguir el contrato por modificación sustancial de condiciones: demanda | 2023 | `extinguir-contrato-modificacion-sustancial-condiciones-120` |
| 145 | Daños en vehículo de empresa: demanda de indemnización | 2022 | `danos-vehiculo-empresa-demanda-indemnizacion-145` |
| 189 | Cambio de titularidad de la contrata: demanda de reconocimiento laboral | 2020 | `cambio-titularidad-contrata-demanda-reconocimiento-189` |
| 368 | Despido disciplinario o reclamación de cantidad: papeleta de conciliación en el SMAC | 2016 | `despido-disciplinario-reclamacion-cantidad-papeleta-368` |
| 371 | Reclamación de cantidad: demanda | 2016 | `reclamacion-cantidad-demanda-371` |
| 387 | Salarios contra grupo laboral de empresas: demanda | 2015 | `salarios-contra-grupo-laboral-empresas-demanda-387` |
| 405 | TRADE: demanda de reclamación de cantidad a la empresa cliente | 2015 | `trade-demanda-reclamacion-cantidad-empresa-cliente-405` |
| 407 | Negativa a la subrogación empresarial: demanda de extinción del trabajador | 2015 | `negativa-subrogacion-empresarial-demanda-extincion-407` |

### Escritos y solicitudes (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 102 | Modificación sustancial colectiva: petición de la empresa para constituir comisión negociadora | 2023 | `modificacion-sustancial-colectiva-peticion-empresa-102` |
| 171 | Pedir anticipo de salario | 2020 | `pedir-anticipo-salario-171` |
| 417 | Ascenso de categoría y diferencias salariales por funciones superiores: solicitud | 2014 | `ascenso-categoria-diferencias-salariales-funciones-417` |

### Actas, acuerdos, planes y protocolos (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 100 | Designación de trabajadores para negociar una modificación sustancial colectiva: acta | 2023 | `designacion-trabajadores-negociar-modificacion-100` |
| 174 | Reconocimiento de deuda de la empresa al trabajador: acuerdo | 2020 | `reconocimiento-deuda-empresa-trabajador-acuerdo-174` |
| 175 | Reconocimiento de deuda del trabajador a la empresa: acuerdo | 2020 | `reconocimiento-deuda-trabajador-empresa-acuerdo-175` |
| 183 | Cesión de vivienda al trabajador: acuerdo de uso | 2020 | `cesion-vivienda-trabajador-acuerdo-uso-183` |

### Otros (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 416 | Negativa de la empresa tras modificación sustancial de condiciones: resolución | 2014 | `negativa-empresa-tras-modificacion-sustancial-416` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

## Uso interno

Plugin de uso interno. Antes de venderlo o dárselo a alumnos, hay que sustituir los textos por plantillas de redacción propia.
