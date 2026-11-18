---
name: plan-igualdad-hoja-estadistica-169
description: "Redacta el escrito «Plan de igualdad: hoja estadística» (formulario 169 de igualdad y acoso laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Plan de igualdad: hoja estadística

> Formulario 0169 del plugin **Igualdad y acoso laboral** · revisado el 17-11-2026.

## Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Convenio colectivo aplicable** (salario, jornada, categorías, faltas y sanciones) → `buscar_convenio` → `leer_convenio`; si sigue vigente o está denunciado, `vigencia_convenio`.

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

- [ ] Nº
- [ ] Otros 20 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «…les de la empresa 1.1 Ámbito Geográfico:»; «…1.2 Datos de la comisión negociadora:»; «…tribución de la plantilla. A la fecha de»; «…ca ningún convenio. Actividad económica:»; «…tribución de la plantilla. A la fecha de»; «…ca ningún convenio. Actividad económica:»; «…2.4 Vigencia del plan de igualdad: Desde»; «…Hasta»; «…constitución de la comisión negociadora:»; «…3.2 Fecha de firma del plan de igualdad:»; «…Sí:»; «…re mujeres y hombres?: [ELEGIR: SI / NO]»; …

## Elecciones que hay que hacer

- Privada / Pública estatal / Pública autonómica / Pública municipal
- Obligatorio: Por disposición legal / Obligatorio: Por convenio colectivo aplicable / Obligatorio: Por sustitución de sanciones accesorias
- Sí, con la mayoría / Sí, pero solo con una parte minoritaria de la misma / No, el plan no ha sido pactado
- Sí / No
- Las secciones sindicales de la empresa / El comité de empresa / los delegados de personal / La comisión sindical
- SI / NO
- SI: de organizaciones empresariales / SI: de consultoría externa / SI: de la Administración Pública / SI: del Servicio de Asesoramiento para Planes y medidas de Igualdad del Instituto de la mujer / SI: de otras administraciones / NO
- SI: a los órganos de solución autónoma de conflictos laborales / SI: a la comisión paritaria del convenio y a los órganos de solución autónoma de conflictos laborales / NO
- Un informe de conclusiones / El diagnóstico completo
- Se flexibiliza su uso / Se amplía el permiso / Se pactan nuevos permisos

## Partes que tienes que redactar tú

El original solo traía los rótulos de estas opciones o varias alternativas seguidas. Redacta la que corresponda con la norma vigente y los hechos, y avísalo al entregar:

- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS
- ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS

## Párrafos opcionales (14)

Inclúyelos solo si encajan en los hechos:

- [OPCIONAL — incluir si procede]…
- No se aplica ningún convenio.…
- 1.5 Nombre o razón social de la empresa:…
- [OPCIONAL — incluir si procede]…
- No se aplica ningún convenio.…
- 1. Salud laboral desde una perspectiva de género.…
- 2. Violencia de género.…
- 3. Lenguaje y comunicación no sexista.…
- 4..…
- Estas medidas se dirigen a corregir: [COMPLETAR]…
- [ELEGIR: Se flexibiliza su uso / Se amplía el permiso / Se pactan nuevos permisos].…
- a) Tipos de acoso contemplados expresamente en el protocolo:…
- – Cuantitativos.…
- – Cualitativos.…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 46.2 de la Ley Orgánica 3/2007

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

### Formulario 0169 · Plan de igualdad: hoja estadística

- Año del modelo: 2021
- Revisión 17-11-2026: 63 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 4 desplegables convertidos en elección en blanco; 1 bloques de opciones sin texto dejados en blanco con sus rótulos; 6 bloques de alternativas señalados; 13 párrafos opcionales señalados; 14 campos de relleno marcados en blanco; 8 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

1. Datos registrales de la empresa

1.1 Ámbito Geográfico:

[COMPLETAR]

1.2 Datos de la comisión negociadora:

[COMPLETAR]

1.3 Titularidad de la empresa:

[ELEGIR: Privada / Pública estatal / Pública autonómica / Pública municipal].

1.4 Ámbito Funcional:

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Empresa

1.5 Nombre o razón social de la empresa:

1.6 NIF de la empresa:

1.7 CNAE de la empresa a 4 dígitos:

1.8 Distribución de la plantilla. A la fecha de [COMPLETAR]

Sexo	Número de personas trabajadoras por tipo de contrato
Indefinido	Temporal	De puesta a disposición en una empresa usuaria	Total
Hombres.
Mujeres.
Total.
Sexo	Número de personas trabajadoras por puesto de trabajo
Órganos de dirección	Mandos intermedios	Resto de la plantilla	Total
Hombres.
Mujeres.
Total.

1.9 Códigos de los convenios de aplicación en la empresa:

[OPCIONAL — incluir si procede]

[OPCIONAL — incluir si procede]

No se aplica ningún convenio.

Actividad económica: [COMPLETAR]

Grupo de empresa

Nº [Nº] de empresas que incluye el plan:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

1.5 Nombre o razón social de la empresa:

1.6 NIF de la empresa:

1.7 CNAE de la empresa a 4 dígitos:

1.8 Distribución de la plantilla. A la fecha de [COMPLETAR]

Sexo	Número de personas trabajadoras por tipo de contrato
Indefinido	Temporal	De puesta a disposición en una empresa usuaria	Total
Hombres.
Mujeres.
Total.
Sexo	Número de personas trabajadoras por puesto de trabajo
Órganos de dirección	Mandos intermedios	Resto de la plantilla	Total
Hombres.
Mujeres.
Total.

1.9 Códigos de los convenios de aplicación en la empresa:

[OPCIONAL — incluir si procede]

[OPCIONAL — incluir si procede]

No se aplica ningún convenio.

Actividad económica: [COMPLETAR]

2. Datos del Plan de Igualdad

2.1 El plan de igualdad es:

Voluntario [ELEGIR: Obligatorio: Por disposición legal / Obligatorio: Por convenio colectivo aplicable / Obligatorio: Por sustitución de sanciones accesorias].

2.2 ¿El Plan se ha pactado con la representación de las personas trabajadoras?

Sí, con la totalidad [ELEGIR: Sí, con la mayoría / Sí, pero solo con una parte minoritaria de la misma / No, el plan no ha sido pactado].

2.3 ¿Es el primer plan de igualdad? [ELEGIR: Sí / No].

2.4 Vigencia del plan de igualdad:

Desde [COMPLETAR] Hasta [COMPLETAR].

2.5 ¿Se ha pactado el procedimiento de revisión del plan? [ELEGIR: Sí / No].

3. Datos de la comisión negociadora

3.1 Fecha de constitución de la comisión negociadora: [COMPLETAR].

3.2 Fecha de firma del plan de igualdad: [COMPLETAR].

3.3 En representación de las personas trabajadoras ha negociado: [ELEGIR: Las secciones sindicales de la empresa / El comité de empresa / los delegados de personal / La comisión sindical].

3.4.1 Composición de la representación de las personas trabajadoras:

Afiliación de los/las representantes y/o centrales sindicales intervinientes	N.º total de representantes	N.º de mujeres	N.º de hombres

3.4.2 Composición de la representación empresarial:

Cargo en la empresa	N.º total de representantes	N.º de mujeres	N.º de hombres

3.5 ¿Han suscrito el plan todos los participantes en la negociación?

[ELEGIR: SI / NO]

Organizaciones que no han firmado	Número de representantes	Mujeres	Hombres

3.6 ¿Tienen formación y/o experiencia en materia de igualdad entre mujeres y hombres en el ámbito laboral las personas que integran la comisión negociadora? [ELEGIR: SI / NO].

3.7 ¿Las personas integrantes de la comisión negociadora han recibido formación en materia de igualdad entre hombres y mujeres en el ámbito laboral, por parte de la empresa, con carácter previo a la realización del diagnóstico y a la negociación del plan de igualdad? [ELEGIR: SI / NO].

3.8 La comisión negociadora ¿ha contado con apoyo y asesoramiento externo especializado en materia de igualdad entre mujeres y hombres en el ámbito laboral?

SI: de organizaciones sindicales [ELEGIR: SI: de organizaciones empresariales / SI: de consultoría externa / SI: de la Administración Pública / SI: del Servicio de Asesoramiento para Planes y medidas de Igualdad del Instituto de la mujer / SI: de otras administraciones / NO].

3.9 ¿Durante el proceso de negociación del plan se ha acudido a la comisión paritaria del convenio o a órganos de solución autónoma de conflictos laborales para resolver las discrepancias existentes?

SI: a la comisión paritaria del convenio [ELEGIR: SI: a los órganos de solución autónoma de conflictos laborales / SI: a la comisión paritaria del convenio y a los órganos de solución autónoma de conflictos laborales / NO].

4. Datos relativos al diagnóstico de situación

4.1 ¿Se han incorporado en el diagnóstico materias adicionales a las recogidas en el artículo 46.2 de la Ley Orgánica 3/2007, de 22 de marzo, para la igualdad efectiva de mujeres y hombres?

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

Sí: [COMPLETAR]

[OPCIONAL — incluir si procede]

1. Salud laboral desde una perspectiva de género.

[OPCIONAL — incluir si procede]

2. Violencia de género.

[OPCIONAL — incluir si procede]

3. Lenguaje y comunicación no sexista.

[OPCIONAL — incluir si procede]

4..

NO

4.2 Para realizar el diagnóstico en materia salarial, la comisión negociadora ha contado con:

La auditoría salarial de la empresa: [ELEGIR: SI / NO].

El registro salarial: [ELEGIR: SI / NO].

4.3 ¿Se alcanzó consenso entre las partes en el diagnóstico de situación? [ELEGIR: SI / NO].

4.4 Indíquese a continuación cuáles de las siguientes materias han sido objeto de negociación en base al resultado del diagnóstico realizado, y en relación con cuáles de ellas se han adoptado medidas en el plan:

Materias	Negociadas	Adopción de medidas
Proceso de selección y contratación.
Clasificación profesional.
Formación.
Promoción profesional.
Tiempo de trabajo / Medidas de conciliación.
Ejercicio corresponsable de los derechos de conciliación de la vida personal, familiar y laboral.
Infrarrepresentación femenina.
Retribuciones.
Prevención del acoso sexual.
Prevención del acoso por razón de sexo.
Salud laboral desde una perspectiva de género.
Violencia de género.
Otras ().
Otras ().

4.5 El informe de diagnóstico que incorpora el plan es: [ELEGIR: Un informe de conclusiones / El diagnóstico completo].

5. Contenido del plan de igualdad

5.1 Medidas de selección y contratación:

5.1.1 ¿Se incluye la implantación de sistemas objetivos de selección de personal y contratación? [ELEGIR: SI / NO].

5.1.2 ¿Se establece la participación de la representación de las personas trabajadoras en los procesos de selección de personal? [ELEGIR: SI / NO].

5.1.3 En los procesos de selección de nuevo personal ¿está previsto que en idénticas condiciones de idoneidad se tenga en cuenta a las personas del sexo infrarrepresentado en el grupo profesional o puesto que se vaya a cubrir? [ELEGIR: SI / NO].

5.1.4 ¿Se incorpora alguna medida de acción positiva para que, en idénticas condiciones de idoneidad, tengan preferencia las personas del sexo infrarrepresentado para el acceso a la jornada a tiempo completo o a la contratación indefinida? [ELEGIR: SI / NO].

– ¿En la conversión de contratos a tiempo parcial en jornada completa? [ELEGIR: SI / NO].
– ¿En la transformación de contratos temporales en indefinidos? [ELEGIR: SI / NO].

5.2 Clasificación profesional:

5.2.1 ¿Se establece como objetivo en el plan de igualdad la presencia equilibrada de mujeres y hombres en todos los niveles de la empresa? [ELEGIR: SI / NO].

5.2.2 ¿El plan incorpora medidas frente a la segregación laboral entre mujeres y hombres?: [ELEGIR: SI / NO]
[COMPLETAR]

[OPCIONAL — incluir si procede]

Estas medidas se dirigen a corregir: [COMPLETAR]

- La segregación ocupacional: [ELEGIR: SI / NO].
- La segregación vertical: [ELEGIR: SI / NO].

5.2.3 ¿Se incorporan medidas correctoras en la valoración de puestos de trabajo para garantizar un sistema de clasificación profesional neutro, libre de sesgos de género? [ELEGIR: SI / NO].

5.2.4 ¿Se pacta la implantación de sistemas objetivos de valoración del trabajo que permitan la evaluación periódica del encuadramiento profesional? [ELEGIR: SI / NO].

5.3 Formación:

5.3.1 ¿El plan de igualdad contempla una formación específica para el personal directivo y de mandos intermedios en materia de igualdad? [ELEGIR: SI / NO].

5.3.2 ¿Se planifica la formación en la empresa desde la perspectiva de género? [ELEGIR: SI / NO].

5.3.3 ¿Se incluyen en las acciones formativas módulos específicos de igualdad de género? [ELEGIR: SI / NO].

5.3.4 ¿Se establece el acceso prioritario de las trabajadoras a acciones formativas que fomenten su inserción en áreas de trabajo masculinizadas?: [ELEGIR: SI / NO]
[COMPLETAR]

5.3.5 ¿Se establece que la formación será impartida dentro de la jornada laboral? [ELEGIR: SI / NO].

5.3.6 ¿Se prevé en el Plan de igualdad la adaptación del horario de las acciones formativas para garantizar la asistencia de las personas trabajadoras con reducción de jornada? [ELEGIR: SI / NO].

5.4 Promoción profesional:

5.4.1 ¿Se incluye en el plan la implantación de sistemas objetivos de promoción profesional? [ELEGIR: SI / NO].

5.4.2 En los procesos de promoción profesional, ¿está previsto que en idénticas condiciones de idoneidad tengan preferencia las trabajadoras para cubrir puesto en áreas o grupos masculinizados? [ELEGIR: SI / NO].

5.4.3 ¿Se proponen medidas en el plan en aras a promover que haya candidaturas femeninas en los procesos de promoción profesional, para fomentar la representación equilibrada de mujeres y hombres en la empresa? [ELEGIR: SI / NO].

5.4.4 ¿Se establecen medidas específicas para promocionar a mujeres en puestos de:

– Mandos intermedios. [ELEGIR: SI / NO].
– Dirección. [ELEGIR: SI / NO].

5.5 Ejercicio corresponsable de los derechos de la vida personal, familiar y laboral:

5.5.1 ¿Se prevé en el plan la implantación de puestos de trabajo que se desarrollen a distancia o existen ya en la empresa esta modalidad? [ELEGIR: SI / NO].

En caso afirmativo, ¿se ha previsto en el plan alguna medida que tenga por objetivo, en relación al trabajo a distancia, evitar la perpetuación de roles o fomentar la corresponsabilidad entre mujeres y hombres? [ELEGIR: SI / NO].

5.5.2 ¿Se han previsto en el plan medidas para garantizar el derecho a la desconexión digital? [ELEGIR: SI / NO].

5.5.3 ¿Contempla medidas de flexibilidad horaria en la entrada, salida o durante el tiempo de comida, que faciliten la conciliación? [ELEGIR: SI / NO].

5.5.4 ¿Se establece una bolsa horaria o días personales de libre disposición? [ELEGIR: SI / NO].

5.5.5 ¿Se mejora la regulación de los permisos retribuidos respecto a la normativa vigente para facilitar la conciliación?: [ELEGIR: SI / NO]
[COMPLETAR]

[OPCIONAL — incluir si procede]

[ELEGIR: Se flexibiliza su uso / Se amplía el permiso / Se pactan nuevos permisos].

5.5.6 ¿Se incorporan medidas que fomenten la corresponsabilidad de los trabajadores varones?

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

SI: [COMPLETAR]

NO

5.6 Retribuciones:

5.6.1 ¿Se prevé revisar los complementos salariales, extrasalariales, incentivos, beneficios sociales, etc. para que respondan a criterios objetivos y neutros y se garantice el principio de igualdad retributiva? [ELEGIR: SI / NO].

5.6.2 ¿Se incorporan medidas de acción positiva para reducir o eliminar la brecha salarial de género?

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

SI: [COMPLETAR]

NO

5.7 Prevención del acoso sexual o por razón de sexo:

5.7.1 ¿El plan incluye un protocolo de actuación en materia de acoso en el trabajo?: [ELEGIR: SI / NO]
[COMPLETAR]

[OPCIONAL — incluir si procede]

a) Tipos de acoso contemplados expresamente en el protocolo:

– Acoso sexual. [ELEGIR: SI / NO].
– Acoso por razón de género. [ELEGIR: SI / NO].

b) ¿Garantiza el procedimiento establecido en el protocolo la intimidad, confidencialidad y dignidad de las personas afectadas por el acoso? [ELEGIR: SI / NO].

c) ¿Se crea un órgano paritario para tratar los casos de acoso contemplados? [ELEGIR: SI / NO].

d) ¿Se prevé asesoramiento o apoyo profesional psicológico y/o médico a las víctimas de acoso? [ELEGIR: SI / NO].

5.8 Derechos laborales de las víctimas de violencia de género:

5.8.1 ¿Se establecen medidas de sensibilización sobre violencia de género? [ELEGIR: SI / NO].

5.8.2 ¿Existe una formación específica para el personal de recursos humanos sobre los derechos de las víctimas de la violencia de género? [ELEGIR: SI / NO].

5.8.3 ¿Se establecen los términos para el ejercicio de los derechos de reducción de jornada, reordenación del tiempo de trabajo, la aplicación del horario flexible o de otras formas de ordenación del tiempo de trabajo, reconocidos legalmente, a las víctimas de violencia de género? [ELEGIR: SI / NO].

5.8.4 ¿Se prevé asesoramiento o apoyo profesional psicológico y/o médico a las víctimas de violencia de género? [ELEGIR: SI / NO].

5.8.5 ¿Se amplían los derechos laborales legalmente establecidos para las víctimas de violencia de género? [ELEGIR: SI / NO].

5.8.6 ¿Se incorporan otras medidas, adicionales a las que contempla la normativa vigente?

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

SI: [COMPLETAR]

NO

5.9 Comunicación, información y sensibilización:

5.9.1 ¿Se establecen medidas específicas sobre comunicación no sexista e inclusiva? [ELEGIR: SI / NO].

5.9.2 ¿Se han definido medidas de difusión e información a la plantilla sobre el Plan de Igualdad? [ELEGIR: SI / NO].

5.9.3 ¿Se han definido acciones de sensibilización a la plantilla en materia de igualdad entre mujeres y hombres? [ELEGIR: SI / NO].

6. Seguimiento y evaluación del Plan

6.1 ¿Se fija un calendario a seguir para la implantación de cada medida del plan? [ELEGIR: SI / NO].

6.2 ¿Se fijan objetivos concretos a conseguir con las medidas del plan? [ELEGIR: SI / NO].

6.3 ¿Se incorpora un sistema de indicadores para realizar el seguimiento?

[ELEGIR UNA DE LAS ALTERNATIVAS QUE SIGUEN Y SUPRIMIR LAS DEMÁS]

SI.

Estos indicadores son: [COMPLETAR]

[OPCIONAL — incluir si procede]

– Cuantitativos.

[OPCIONAL — incluir si procede]

– Cualitativos.

NO

6.4 ¿Se establecen específicamente las personas/puestos/niveles jerárquicos responsables de la implantación y seguimiento del plan? [ELEGIR: SI / NO].

6.5 ¿Se prevén la composición y atribuciones del órgano paritario de vigilancia y seguimiento del plan? [ELEGIR: SI / NO].

6.6 ¿Se prevé el recurso a los correspondientes sistemas de solución de conflictos laborales en caso de discrepancia sobre el cumplimiento o en caso incumplimiento de las medidas contempladas en el plan? [ELEGIR: SI / NO].

6.7 ¿Se contempla un procedimiento específico para la revisión de las medidas, en función de los resultados de las evaluaciones, para facilitar el cumplimiento de los objetivos? [ELEGIR: SI / NO].

6.8 ¿Se prevé la realización de informes de seguimiento? [ELEGIR: SI / NO].

════════════════════════════════════════════════════════════════════════
