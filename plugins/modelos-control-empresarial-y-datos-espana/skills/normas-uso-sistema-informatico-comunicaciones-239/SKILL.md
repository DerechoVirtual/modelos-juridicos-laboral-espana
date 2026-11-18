---
name: normas-uso-sistema-informatico-comunicaciones-239
description: "Redacta el escrito «Normas de uso del sistema informático y las comunicaciones electrónicas» (formulario 239 de protección de datos y control empresarial, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Normas de uso del sistema informático y las comunicaciones electrónicas

> Formulario 0239 del plugin **Protección de datos y control empresarial** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

## Qué tienes en esta carpeta

- «Texto del formulario», al final de este fichero: el texto del formulario revisado, con las marcas de la revisión.
- `../indice/marco.md` (en la carpeta de la skill `indice` de este plugin): guía del tema con las reglas y plazos vigentes comprobados en el BOE.

## Datos que hay que pedir al usuario

Pídelos en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez.

- [ ] Otros 8 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…ro que infrinja las Normas de la Empresa»; «…organizaciones. Se prohíbe expresamente:»; «…ación. 6. Uso de Internet El empleado de»; «…rnet desde un equipo o con los medios de»; «…periódicamente. Se prohíbe expresamente:»; «…sunción de obligaciones financieras para»; «…ener la integridad del sistema. Asimismo»; «…l uso abusivo del sistema. El todo caso,»

## Párrafos opcionales (2)

Inclúyelos solo si encajan en los hechos:

- considera todos los mensajes recibidos, enviados o almacenados en el sistema de correo electrónico como mensaj…
- tiene la capacidad de monitorizar el sistema de uso de Internet, y de determinar los tiempos online, los sitio…

## Normas que cita el formulario

No cita artículos concretos. Si añades alguno, compruébalo con `buscar_articulo`.

## Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero el «Texto del formulario» del final de este fichero, con su cabecera, y la parte de `../indice/marco.md` que afecte al caso (plazos, órgano, procedimiento, conciliación o mediación previa, reclamación previa o vía administrativa, según el caso).
3. Pide los datos de la lista. Lo que el usuario no sepa se queda como hueco visible.
4. Decide las elecciones y los párrafos opcionales según los hechos. Redacta las partes que el original no traía.
5. Aplica los avisos y las notas de revisión. Comprueba con `buscar_articulo` cada norma citada y, si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Indica el plazo y el cauce: desde cuándo cuenta, cuándo vence y ante qué órgano se presenta.
7. Antes de entregarlo, pasa `verificar_escrito` con las frases del escrito que citan normas o sentencias y corrige lo que señale.
8. Entrega el escrito en **Word (.docx)** con formato de escrito (usa la skill de Word disponible) y, si es corto, también en el chat.
9. Cierra con: datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator y, si algún dato sale de internet, cuál es y su enlace.

## Texto del formulario

### Formulario 0239 · Normas de uso del sistema informático y las comunicaciones electrónicas

- Año del modelo: 2019
- Revisión 17-11-2026: 2 párrafos opcionales señalados; 6 campos de relleno marcados en blanco; 2 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

Equipos y sistemas de la Empresa
Propiedad de la información
Uso del sistema
Usos prohibidos del sistema
Uso del correo electrónico
Uso de Internet
Control del sistema

Directrices para el uso y manejo de los sistemas informáticos y del correo electrónico de la empresa

La empresaestablece las siguientes directrices para el uso y manejo de los sistemas informáticos y de las comunicaciones electrónicas:

1. Equipos y sistemas de la Empresa

Todos los equipos y sistemas electrónicos instalados y utilizados en la Empresa son propiedad de la misma y están destinados exclusivamente a usos profesionales. La empresa es responsable del sistema informático.

2. Propiedad de la información

Toda la información transmitida y recibida o almacenada en estos sistemas es propiedad de la Empresa, sea mediante ordenadores portátiles, buzones de voz, faxes, etc.

No se considera privada, por tanto, ninguna información almacenada o en circulación por los sistemas y equipos de la empresa.

 dispone de esta información para sus fines y actividad propia y sola la facilitará a terceros en los casos legalmente establecidos a favor de las Administraciones públicas.

3. Uso del sistema

La asignación de equipos y medios electrónicos y las ayudas digitales suministradas al personal tienen por objeto la realización de su trabajo profesional y la mejora de la productividad. Como ocurre con el teléfono, estos medios pueden dar ocasión a su uso para fines personales, pero éste solo está permitido si no interfiere el desempeño laboral propio o de otras personas y si los recursos que consume (tiempo y coste) son insignificantes.

El usuario es el responsable de la seguridad de su equipo y de los sistemas que utiliza. Las contraseñas asignadas no deben revelarse a otras personas. El ordenador no debe permanecer abierto y sin vigilancia.

Se prohíbe expresamente la instalación o descarga de programas informáticos, incluidos los programas de codificación, sin la aprobación del Departamento de Informática (o el Administrador del Sistema).

4. Usos prohibidos del sistema

- Acceder a los archivos e información electrónica de otros empleados, excepto en los casos expresamente autorizados.
- Instalar y desarrollar juegos.
- Usar el sistema para actividades profesionales propias o por cuenta de terceros o con ánimo de lucro.
- Usar el sistema para actividades ilegales.
- Usar el sistema para actividades políticas o de grupos de presión o ideológicos.
- Realizar acciones que puedan causar daños a los sistemas y redes o agotar los recursos del sistema.
- Utilizar el sistema para copiar o transmitir documentos o información protegida por copyright.
- Cualquier otro que infrinja las Normas de la Empresa [COMPLETAR].

5. Uso del correo electrónico

Los mensajes deben ser claros, sin doble sentido. El mensaje debe tratarse como una carta o comunicado escrito, no como una conversación oral. Los mensajes constituyen registros de empresa, no debe decirse en ellos nada que no pueda ser leído por un tercero. No abusar del "urgente". Eliminar el mensaje en cuanto sea posible.

La garantía de confidencialidad de la información, sea de la Empresa o de sus proveedores y clientes, debe cuidarse especialmente en el correo electrónico a causa de la facilidad con que esta información puede ser difundida.

Los usuarios deben asegurarse que la información recibida o transmitida sea apropiada y lícita, es decir que no incumpla normas generales y empresariales y que sea correcta y respetuosa con las personas y las organizaciones.

Se prohíbe expresamente: [COMPLETAR]

- Mensajes de contenido sexual, obscenos o que impliquen acoso sexual, incluidas proposiciones, citas o mensajes amorosos.
- Mensajes de contenido étnico o racial.
- Mensajes discriminatorios o atentatorios a la igualdad básica por razón de sexo, edad, religión, afiliación sindical, minusvalía, nacionalidad, etc.
- Mensajes que tengan el carácter de libelos o que ofendan la dignidad personal o social.
- Mensajes que difundan información personal y reservada sin la debida autorización.

6. Uso de Internet

El empleado de [COMPLETAR] que accede a Internet desde un equipo o con los medios de [COMPLETAR] es responsable de las actividades online resultantes del uso de su login y password. Estos códigos son únicos por usuario, se asignan por el Administrador del sistema y se cambian periódicamente.

Se prohíbe expresamente: [COMPLETAR]

- El acceso a sitios inapropiados, incluidas páginas porno o sexualmente explícitas, difamatorias u ofensivas, raciales, discriminatorias, etc.
- La asunción de obligaciones financieras para [COMPLETAR] por el acceso a sitios comerciales.

7. Control del sistema

[OPCIONAL — incluir si procede]

 considera todos los mensajes recibidos, enviados o almacenados en el sistema de correo electrónico como mensajes de carácter empresarial y por lo tanto, tiene la capacidad para acceder y revisar todos los mensajes del sistema y se reserva el derecho de hacerlo con el fin de comprobar el cumplimiento de las normas establecidas, evaluar el uso debido del sistema por los usuarios, evaluar el rendimiento de los empleados, investigar la salida de información confidencial y mantener la integridad del sistema. Asimismo [COMPLETAR] se reserva el derecho a invalidar las contraseñas o códigos vigentes, ante la sospecha razonable del uso abusivo del sistema. El todo caso, [COMPLETAR] seguirá los criterios o principios de idoneidad y necesidad de la medida para el fin propuesto y de proporcionalidad o ponderación de las circunstancias e intereses en conflicto.

[OPCIONAL — incluir si procede]

 tiene la capacidad de monitorizar el sistema de uso de Internet, y de determinar los tiempos online, los sitios de acceso, la participación en chat y actividades de grupo y la transferencia de programas, y se reserva el derecho de hacerlo con los mismos fines y garantías expresadas respecto al sistema de correo electrónico.

════════════════════════════════════════════════════════════════════════
