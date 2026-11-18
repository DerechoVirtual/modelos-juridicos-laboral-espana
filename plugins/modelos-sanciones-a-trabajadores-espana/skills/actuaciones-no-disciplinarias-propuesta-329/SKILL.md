---
name: actuaciones-no-disciplinarias-propuesta-329
description: "Redacta el escrito «Actuaciones no disciplinarias: propuesta» (formulario 329 de régimen disciplinario laboral, revisado el 17-11-2026): pide los datos, decide las opciones, aplica las correcciones y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Actuaciones no disciplinarias: propuesta

> Formulario 0329 del plugin **Régimen disciplinario laboral** · revisado el 17-11-2026.

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

- [ ] NOMBRE Y APELLIDOS (14 veces)
- [ ] FECHA (4 veces)
- [ ] DESCRIBIR (6 veces)
- [ ] Otros 28 datos sin etiqueta, marcados `[COMPLETAR]`. Su contexto en el formulario: «… disciplinario abierto contra empleado A»; «…iento y encargo efectuado por la empresa»; «…en»; «…ó, y en qué grado, los siguientes hechos»; «…conforme a lo dispuesto en el artículo»; «…Estatuto de los Trabajadores en su letra»; «…ciones y propuso las siguientes pruebas:»; «… En cuanto a las alegaciones, señaló que»; «…a a las pruebas, propuso las siguientes:»; «…ciones y propuso las siguientes pruebas:»; «… En cuanto a las alegaciones, señaló que»; «…a a las pruebas, propuso las siguientes:»; …

## Elecciones que hay que hacer

- muy grave / grave
- Delegado de Personal / Comité de Empresa / Delegado Sindical
- grave / muy grave

## Párrafos opcionales (10)

Inclúyelos solo si encajan en los hechos:

- A propuesta de la empresa: [COMPLETAR]…
- A propuesta de la persona trabajadora interesada:…
- A propuesta de la representación de las personas trabajadoras:…
- Por la empresa se propuso una prueba consistente en [DESCRIBIR], que fue denegada en su práctica por [COMPLETA…
- Por la persona trabajadora interesada se propuso una prueba consistente en [DESCRIBIR], que fue denegada en su…
- Por la representación de las personas trabajadoras se propuso una prueba consistente en [DESCRIBIR], que fue d…
- Por la empresa se propuso una prueba consistente en [DESCRIBIR], que no pudo ser practicada por [COMPLETAR].…
- Por la persona trabajadora interesada se propuso una prueba consistente en [DESCRIBIR], que no pudo ser practi…
- Por la representación de las personas trabajadoras se propuso una prueba consistente en [DESCRIBIR], que no pu…
- - [COMPLETAR].…

## Normas que cita el formulario

Compruébalas **todas** con `buscar_articulo` antes de dejarlas en el escrito. Si una ha cambiado, usa la redacción vigente y dilo:

- artículo 60.2 del Estatuto de los Trabajadores

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

### Formulario 0329 · Actuaciones no disciplinarias: propuesta

- Año del modelo: 2017
- Revisión 17-11-2026: 3 desplegables y casillas convertidos en elección en blanco; 1 párrafos repetibles señalados; 9 párrafos opcionales señalados; 51 campos de relleno marcados en blanco; 1 etiquetas sin dato marcadas en blanco

> Cómo leerlo: [EN MAYÚSCULAS] = dato que hay que rellenar; [ELEGIR: a / b] = elegir una opción y borrar las demás; [OPCIONAL — incluir si procede] = el párrafo siguiente solo si encaja en el caso; [NOTA DE REVISIÓN: …] = corrección o aviso normativo de la revisión, no forma parte del escrito.

---

ANTECEDENTES DE HECHO
PROPUESTA
Firmas

Modelo de propuesta de actuaciones no disciplinarias dictada por el instructor nombrado en el expediente disciplinario abierto contra empleado

A [COMPLETAR].

D./Dña. [NOMBRE Y APELLIDOS], en calidad de Instructor/a del expediente contradictorio y disciplinario abierto y seguido contra la persona trabajadora D./Dña. [NOMBRE Y APELLIDOS], por nombramiento y encargo efectuado por la empresa [COMPLETAR] en [COMPLETAR], hago la propuesta que más adelante detallaré en virtud de los siguientes

ANTECEDENTES DE HECHO

PRIMERO.- La empresa mencionada acordó abrir expediente contradictorio y disciplinario contra la persona trabajadora de la misma D./Dña. [NOMBRE Y APELLIDOS], el día [FECHA], lo que se le comunicó a la persona interesada el día [FECHA].

SEGUNDO.- Se designó por la citada empresa como Instructor/a del mismo a quién firma este escrito-propuesta, D./Dña. [NOMBRE Y APELLIDOS], y como Secretario a quién lo refrenda, D./Dña. [NOMBRE Y APELLIDOS].

TERCERO.- La finalidad del antedicho expediente ha consistido en averiguar si D./Dña. [NOMBRE Y APELLIDOS] cometió, y en qué grado, los siguientes hechos [COMPLETAR], así como la realidad de los mismos.

CUARTO.- Tales hechos, de acreditarse su realidad y la autoría de la persona trabajadora expedientada, darían lugar a la comisión de una falta laboral calificable de [ELEGIR: muy grave / grave] conforme a lo dispuesto en el artículo [COMPLETAR] del Convenio Colectivo y en el artículo 54.2... del Estatuto de los Trabajadores en su letra [COMPLETAR].

QUINTO.- En la tramitación del presente expediente disciplinario se ha dado traslado, por los plazos preceptivos legal y convencionalmente, a fin de que evacuaran los informes correspondientes y/o hicieran las alegaciones que estimaran oportunas y/o presentaran las pruebas que consideraran adecuadas, a las siguientes personas y entidades:

- a la propia persona trabajadora interesada.
- al [ELEGIR: Delegado de Personal / Comité de Empresa / Delegado Sindical].

SEXTO.- Que el día [FECHA], el antedicho interesado efectuó, en esencia, las siguientes alegaciones y propuso las siguientes pruebas: [COMPLETAR].

En cuanto a las alegaciones, señaló que [COMPLETAR].

Por lo que respecta a las pruebas, propuso las siguientes: [COMPLETAR].

SÉPTIMO.- Que el día [FECHA], la representación sindical y/o legal formuló, sustancialmente, las siguientes alegaciones y propuso las siguientes pruebas: [COMPLETAR].

En cuanto a las alegaciones, señaló que [COMPLETAR].

Por lo que respecta a las pruebas, propuso las siguientes: [COMPLETAR].

OCTAVO.- En cuanto a las pruebas y acreditaciones, ha de señalarse lo siguiente:

1. Que se practicaron las siguientes pruebas:

[OPCIONAL — incluir si procede]

A propuesta de la empresa: [COMPLETAR]

[OPCIONAL — incluir si procede]

A propuesta de la persona trabajadora interesada:

[OPCIONAL — incluir si procede]

A propuesta de la representación de las personas trabajadoras:

2. Que se denegaron las siguientes pruebas concretas y por los siguientes motivos:

[OPCIONAL — incluir si procede]

Por la empresa se propuso una prueba consistente en [DESCRIBIR], que fue denegada en su práctica por [COMPLETAR].

[OPCIONAL — incluir si procede]

Por la persona trabajadora interesada se propuso una prueba consistente en [DESCRIBIR], que fue denegada en su práctica por [COMPLETAR].

[OPCIONAL — incluir si procede]

Por la representación de las personas trabajadoras se propuso una prueba consistente en [DESCRIBIR], que fue denegada en su práctica por [COMPLETAR].

3. Que, aún propuestas y admitidas a su práctica, no pudieron practicarse las siguientes pruebas:

[OPCIONAL — incluir si procede]

Por la empresa se propuso una prueba consistente en [DESCRIBIR], que no pudo ser practicada por [COMPLETAR].

[OPCIONAL — incluir si procede]

Por la persona trabajadora interesada se propuso una prueba consistente en [DESCRIBIR], que no pudo ser practicada por [COMPLETAR].

[OPCIONAL — incluir si procede]

Por la representación de las personas trabajadoras se propuso una prueba consistente en [DESCRIBIR], que no pudo ser practicada por [COMPLETAR].

NOVENO.- Que del resultado de cuantas pruebas se propusieron y practicaron y de cuantas alegaciones se realizaron, ha quedado acreditado que los hechos imputados a D./Dña. [NOMBRE Y APELLIDOS] fueron los siguientes:

[OPCIONAL — repetir el párrafo siguiente tantas veces como haga falta]

- [COMPLETAR].

DÉCIMO.- De tales hechos, con independencia de la calificación que, en su posible calidad de falta laboral, es autor D./Dña. [NOMBRE Y APELLIDOS], persona trabajadora interesada en el presente expediente.

UNDÉCIMO.- Además de lo hasta aquí consignado, han de señalarse los siguientes aspectos, que estima este Instructor son de suma transcendencia para una correcta y justa valoración de los hechos acaecidos, así como de importancia decisiva para concluir con la no adopción de medida disciplinaria alguna: [COMPLETAR].

En razón a los antecedentes descritos y a los hechos que se estima quedaron acreditados, así como de su autoría, el Instructor del presente expediente disciplinario formula a la empresa la siguiente:

PROPUESTA

PRIMERO.- Si bien es cierto que los hechos relatados, como se ha indicado con anterioridad en el antecedente correspondiente, podrían ser constitutivos de una falta laboral, que podría ser calificada de [ELEGIR: grave / muy grave], en tanto prevista y castigada en su grado máximo en el artículo [COMPLETAR] del Convenio Colectivo y en el artículo 54.2, letra ... del Estatuto de los Trabajadores [COMPLETAR], también lo es que los acontecimientos y sucesos sobre los que ha de emitirse la presente propuesta reúnen toda una serie de circunstancias subjetivas y objetivas que, como más adelante se detallará y argumentará, aconsejan que no se adopte una medida disciplinaria con la persona interesada en el presente expediente, sino otra de diferente naturaleza.

En efecto, las circunstancias a las que se acaba de hacer referencia son las que se han consignado en los antecedentes de hecho de este informe-propuesta y las mismas aconsejan no tomar medida disciplinaria alguna por las siguientes razones: [COMPLETAR].

SEGUNDO.- La antedicha conducta, con independencia de que este Instructor proponga finalmente la no adopción de medida disciplinaria alguna, en cualquier caso y se calificara finalmente como muy grave, grave o leve, no estaría prescrita, a tenor de lo establecido en el artículo 60.2 del Estatuto de los Trabajadores mencionado.

Su autoría, también en cualquier caso, sería achacable a la persona trabajadora expedientada.

Asimismo, la conducta realizada por la persona expedientada podría ser tenida como punible.

Pero, dadas las circunstancias subjetivas y objetivas que concurren en el presente caso, se estima que la persona trabajadora interesada en el presente expediente no ha de ser corregido disciplinariamente y, por tanto, no ha de hacerse uso por la empresa de la facultad que le reconocen los artículos 20 y 58.1 del citado Estatuto.

TERCERO.- Sobre la base de la antedicha estimación, este Instructor considera que sería más conveniente y adecuado tomar una medida distinta a la meramente disciplinaria, que podría consistir en [COMPLETAR]; y ello por las siguientes razones [COMPLETAR].

CUARTO.- Se han respetado todos los trámites y plazos en el desenvolvimiento y tramitación de este expediente disciplinario.

POR LO DICHO PROPONGO QUE A LA PERSONA TRABAJADORA DE ESTA EMPRESA D./DÑA. [NOMBRE Y APELLIDOS], NO SE LE IMPONGA SANCIÓN DISCIPLINARIA ALGUNA, SINO QUE SE ADOPTE POR LA EMPRESA LA SIGUIENTE MEDIDA NO DISCIPLINARIA: [COMPLETAR].

Firmado que sea el presente informe-propuesta, será comunicado a la Dirección de la empresa a fin de que ésta tome la decisión que estime más adecuada, al no ser la presente propuesta vinculante, dándose, en todo caso y salvo orden legítima en contrario, por concluido el presente expediente disciplinario.

Instructor/a

Secretario/a

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

NOTA: La pongo yo, el Secretario de este expediente contradictorio y disciplinario a fin hacer constar que el día he comunicado a la empresa [COMPLETAR] y a la persona trabajadora interesada el anterior informe-propuesta y la conclusión del expediente mencionado, en prueba de lo cual firman conmigo, dicha persona trabajadora interesada y D./Dña. [NOMBRE Y APELLIDOS], en tanto representante autorizado de la empresa.

Persona trabajadora

Por la empresa

D./Dña. [NOMBRE Y APELLIDOS]

D./Dña. [NOMBRE Y APELLIDOS]

════════════════════════════════════════════════════════════════════════
