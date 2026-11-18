# Videovigilancia, geolocalización y datos de la plantilla · España

> Plugin de Claude Code `modelos-control-empresarial-y-datos-espana` · **11 formularios** · área: Laboral · revisado el 17-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Sirve para controlar la actividad de la plantilla respetando su intimidad: cláusulas de protección de datos, videovigilancia, geolocalización, uso de los medios informáticos de la empresa y códigos de conducta.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el escrito en Word, con las normas comprobadas en el BOE.

## Qué puedes hacer con él

Estos son los tipos de escrito que trae, con algunos ejemplos (la lista completa de los 11 está al final):

- **Contratos, cláusulas y anexos** (4). Por ejemplo: Protección de datos en contratos de trabajo: cláusula; Confidencialidad, control de medios y desconexión digital: cláusula; Protección de datos en contratos con empresa subcontratista: cláusula.
- **Cartas y comunicaciones a la plantilla** (3). Por ejemplo: Aviso emergente sobre el uso laboral de los medios de la empresa; Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores; Aviso al trabajador de videovigilancia, control de jornada o geolocalización.
- **Actas, acuerdos, planes y protocolos** (4). Por ejemplo: Información sobre protección de datos a los empleados; Código de conducta en la relación empresa-trabajador; Vestimenta en la empresa: código.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué escrito necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Cláusula de protección de datos para los contratos de trabajo»
   - «Aviso a los representantes de la instalación de cámaras de videovigilancia»
   - «Normas de uso del sistema informático y del correo de la empresa»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/modelos-control-empresarial-y-datos-espana:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/modelos-control-empresarial-y-datos-espana:proteccion-datos-contratos-trabajo-clausula-172`. Los nombres están en la lista de formularios de abajo.

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
- **Espacio que ocupa:** unos 1.000 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable modelos-control-empresarial-y-datos-espana@plugins-dv`).

## Instalación

Solo la primera vez, añade el catálogo de plugins (sirve para todos). Cambia la ruta por la carpeta donde esté el catálogo (la que contiene `.claude-plugin`); si es un zip, descomprímelo antes en una ruta corta, porque hay nombres de archivo largos:

```bash
claude plugin marketplace add "C:\plugins-dv"
```

Después, instala este plugin:

```bash
claude plugin install modelos-control-empresarial-y-datos-espana@plugins-dv
```

En la pestaña Code de la app de Claude también puedes pedírselo a Claude con esas palabras: «instala el plugin modelos-control-empresarial-y-datos-espana del catálogo plugins-dv que está en C:\plugins-dv». Al terminar, abre una conversación nueva para que aparezcan sus skills.

## Lista de formularios

Para usar uno directamente: `/modelos-control-empresarial-y-datos-espana:<skill>`.

### Contratos, cláusulas y anexos (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 172 | Protección de datos en contratos de trabajo: cláusula | 2020 | `proteccion-datos-contratos-trabajo-clausula-172` |
| 173 | Confidencialidad, control de medios y desconexión digital: cláusula | 2020 | `confidencialidad-control-medios-desconexion-digital-173` |
| 251 | Protección de datos en contratos con empresa subcontratista: cláusula | 2018 | `proteccion-datos-contratos-empresa-subcontratista-251` |
| 252 | Información sobre protección de datos en la geolocalización: cláusula | 2018 | `informacion-sobre-proteccion-datos-geolocalizacion-252` |

### Cartas y comunicaciones a la plantilla (3)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 223 | Aviso emergente sobre el uso laboral de los medios de la empresa | 2019 | `aviso-emergente-sobre-uso-laboral-medios-empresa-223` |
| 253 | Instalación de cámaras de videovigilancia: aviso a la representación de los trabajadores | 2018 | `instalacion-camaras-videovigilancia-aviso-representacion-253` |
| 376 | Aviso al trabajador de videovigilancia, control de jornada o geolocalización | 2016 | `aviso-trabajador-videovigilancia-control-jornada-376` |

### Actas, acuerdos, planes y protocolos (4)

| Nº | Formulario | Año | Skill |
|---|---|---|---|
| 222 | Información sobre protección de datos a los empleados | 2019 | `informacion-sobre-proteccion-datos-empleados-222` |
| 232 | Código de conducta en la relación empresa-trabajador | 2019 | `codigo-conducta-relacion-empresa-trabajador-232` |
| 233 | Vestimenta en la empresa: código | 2019 | `vestimenta-empresa-codigo-233` |
| 239 | Normas de uso del sistema informático y las comunicaciones electrónicas | 2019 | `normas-uso-sistema-informatico-comunicaciones-239` |

## Qué hay dentro de cada skill

- `SKILL.md`: los datos que hay que pedir, las elecciones, los párrafos opcionales, los avisos de la revisión, las normas que hay que comprobar y el flujo;
- `formulario.md`: el texto revisado del formulario;
- `marco.md`: la guía del tema, con las reglas y plazos vigentes comprobados en el BOE.

