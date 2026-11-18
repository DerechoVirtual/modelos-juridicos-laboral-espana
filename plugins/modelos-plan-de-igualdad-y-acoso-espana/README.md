# Planes de igualdad y protocolos de acoso y LGTBI · España

> Plugin de Claude Code `modelos-plan-de-igualdad-y-acoso-espana` · **35 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para cumplir en igualdad y prevenir el acoso: plan de igualdad y su comisión negociadora, protocolos de acoso sexual y por razón de sexo, plan y protocolo LGTBI, y canal de denuncias.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 35 está al final):

- **Contratos, cláusulas y anexos** (1). Por ejemplo: Compromiso con el plan de igualdad en el convenio colectivo: cláusula.
- **Cartas y comunicaciones a la plantilla** (7). Por ejemplo: Aviso a la plantilla de la implantación del canal de denuncias; Carta para constituir la comisión negociadora del plan de igualdad; Criterios de selección de la empresa usuaria: comunicación a la empresa externa.
- **Demandas, papeletas y reclamaciones previas** (1). Por ejemplo: Acoso laboral (mobbing): demanda por infracción de la normativa de prevención.
- **Escritos y solicitudes** (2). Por ejemplo: Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso; Denuncia de acoso sexual o por razón de sexo.
- **Expediente disciplinario** (1). Por ejemplo: Cargos por acoso sexual: pliego.
- **Actas, acuerdos, planes y protocolos** (16). Por ejemplo: Impulso por la empresa de la negociación del plan de igualdad o del plan LGTBI; Protocolo contra el acoso y la violencia hacia personas LGTBI; Acuerdo con la representación de los trabajadores sobre medidas de igualdad LGTBI.
- **Documentos, certificados y modelos oficiales** (7). Por ejemplo: Evaluación para la comisión de seguimiento: cuestionario; Cuestionario de evaluación del plan dirigido a la plantilla; Cuestionario de evaluación dirigido a la dirección.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Protocolo contra el acoso sexual y por razón de sexo»
   - «Acta de constitución de la comisión negociadora del plan de igualdad»
   - «Protocolo contra el acoso y la violencia hacia las personas LGTBI»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-plan-de-igualdad-y-acoso-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-plan-de-igualdad-y-acoso-espana:evaluacion-comision-seguimiento-cuestionario-51`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 3.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-plan-de-igualdad-y-acoso-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-plan-de-igualdad-y-acoso-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-plan-de-igualdad-y-acoso-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-plan-de-igualdad-y-acoso-espana:<skill>`.

### Contratos, cláusulas y anexos (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 219 | Compromiso con el plan de igualdad en el convenio colectivo: cláusula | 2019 | `compromiso-plan-igualdad-convenio-colectivo-clausula-219` |

### Cartas y comunicaciones a la plantilla (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 95 | Aviso a la plantilla de la implantación del canal de denuncias | 2023 | `aviso-plantilla-implantacion-canal-denuncias-95` |
| 161 | Carta para constituir la comisión negociadora del plan de igualdad | 2021 | `carta-constituir-comision-negociadora-plan-igualdad-161` |
| 206 | Criterios de selección de la empresa usuaria: comunicación a la empresa externa | 2019 | `criterios-seleccion-empresa-usuaria-comunicacion-empresa-206` |
| 212 | Reunión con perspectiva de igualdad: convocatoria | 2019 | `reunion-perspectiva-igualdad-convocatoria-212` |
| 213 | Aviso a la plantilla del inicio del Plan de Igualdad | 2019 | `aviso-plantilla-inicio-plan-igualdad-213` |
| 214 | Compromiso de la empresa con la igualdad: carta | 2019 | `compromiso-empresa-igualdad-carta-214` |
| 316 | Sanción por acoso: carta | 2017 | `sancion-acoso-carta-316` |

### Demandas, papeletas y reclamaciones previas (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 162 | Acoso laboral (mobbing): demanda por infracción de la normativa de prevención | 2021 | `acoso-laboral-mobbing-demanda-infraccion-normativa-162` |

### Escritos y solicitudes (2)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 165 | Autorizar los trámites de inscripción del plan de igualdad o del protocolo de acoso | 2021 | `autorizar-tramites-inscripcion-plan-igualdad-protocolo-165` |
| 217 | Denuncia de acoso sexual o por razón de sexo | 2019 | `denuncia-acoso-sexual-razon-sexo-217` |

### Expediente disciplinario (1)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 326 | Cargos por acoso sexual: pliego | 2017 | `cargos-acoso-sexual-pliego-326` |

### Actas, acuerdos, planes y protocolos (16)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 54 | Impulso por la empresa de la negociación del plan de igualdad o del plan LGTBI | 2023 | `impulso-empresa-negociacion-plan-igualdad-plan-lgtbi-54` |
| 108 | Protocolo contra el acoso y la violencia hacia personas LGTBI | 2023 | `protocolo-contra-acoso-violencia-hacia-personas-lgtbi-108` |
| 118 | Acuerdo con la representación de los trabajadores sobre medidas de igualdad LGTBI | 2023 | `acuerdo-representacion-trabajadores-sobre-medidas-118` |
| 136 | Reglamento de la Comisión de seguimiento y evaluación | 2022 | `reglamento-comision-seguimiento-evaluacion-136` |
| 141 | Acta de reunión de la Comisión de seguimiento del Plan de Igualdad | 2022 | `acta-reunion-comision-seguimiento-plan-igualdad-141` |
| 146 | Acta de constitución de la Comisión de seguimiento del plan de igualdad o plan LGTBI | 2022 | `acta-constitucion-comision-seguimiento-plan-igualdad-146` |
| 158 | Acta de aprobación del protocolo contra el acoso sexual o por razón de sexo | 2021 | `acta-aprobacion-protocolo-contra-acoso-sexual-razon-sexo-158` |
| 160 | Diagnóstico del Plan de Igualdad: acta de aprobación | 2021 | `diagnostico-plan-igualdad-acta-aprobacion-160` |
| 164 | Acta de aprobación del plan de igualdad o del plan LGTBI | 2021 | `acta-aprobacion-plan-igualdad-plan-lgtbi-164` |
| 177 | Impulso por la representación de los trabajadores de la negociación del plan de igualdad | 2020 | `impulso-representacion-trabajadores-negociacion-plan-177` |
| 208 | Compromisos de la organización en selección y promoción | 2019 | `compromisos-organizacion-seleccion-promocion-208` |
| 209 | Comisión negociadora del plan de igualdad: acta de reunión | 2019 | `comision-negociadora-plan-igualdad-acta-reunion-209` |
| 211 | Acta de constitución de la comisión negociadora del plan de igualdad o plan LGTBI | 2019 | `acta-constitucion-comision-negociadora-plan-igualdad-211` |
| 215 | Compromiso de la organización contra el acoso sexual y por razón de sexo | 2019 | `compromiso-organizacion-contra-acoso-sexual-razon-sexo-215` |
| 216 | Protocolo contra el acoso sexual y por razón de sexo en el trabajo | 2019 | `protocolo-contra-acoso-sexual-razon-sexo-trabajo-216` |
| 220 | Confidencialidad en la tramitación de denuncias de acoso: compromiso | 2019 | `confidencialidad-tramitacion-denuncias-acoso-compromiso-220` |

### Documentos, certificados y modelos oficiales (7)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 50 | Evaluación del Plan de Igualdad: informe |  | `evaluacion-plan-igualdad-informe-50` |
| 51 | Evaluación para la comisión de seguimiento: cuestionario | 2023 | `evaluacion-comision-seguimiento-cuestionario-51` |
| 52 | Cuestionario de evaluación del plan dirigido a la plantilla | 2023 | `cuestionario-evaluacion-plan-dirigido-plantilla-52` |
| 53 | Cuestionario de evaluación dirigido a la dirección | 2023 | `cuestionario-evaluacion-dirigido-direccion-53` |
| 169 | Plan de igualdad: hoja estadística | 2021 | `plan-igualdad-hoja-estadistica-169` |
| 203 | Cuestionario de igualdad para la plantilla | 2020 | `cuestionario-igualdad-plantilla-203` |
| 205 | Cuestionario de igualdad para la dirección | 2019 | `cuestionario-igualdad-direccion-205` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- al final de ese mismo `SKILL.md`, el texto revisado del formulario.

La guía del tema, con las reglas y plazos vigentes comprobados en el BOE, es común a todas las skills del plugin y está en `skills/indice/marco.md`.

