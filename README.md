# Modelos jurídicos de España para Claude · Laboral

11 plugins de modelos de escritos de Laboral, uno por tema. Cada modelo es una skill que Claude rellena paso a paso con los datos del caso: 427 skills en total, más una skill `indice` por plugin para encontrar el modelo adecuado.

Todas las skills trabajan con **Jurisprudenciator** (https://jurisprudenciator.lexiaipro.org): antes de redactar comprueban que el conector responde, verifican en fuentes oficiales los artículos y la jurisprudencia que se citan y revisan el escrito con `verificar_escrito` antes de entregarlo. Sin Jurisprudenciator conectado, las skills no redactan.

Las demás jurisdicciones están en repositorios propios: [Administrativo](https://github.com/DerechoVirtual/modelos-juridicos-administrativo-espana), [Civil](https://github.com/DerechoVirtual/modelos-juridicos-civil-espana), [Penal](https://github.com/DerechoVirtual/modelos-juridicos-penal-espana).

## Instalación

En Claude Code:

```
/plugin marketplace add DerechoVirtual/modelos-juridicos-laboral-espana
/plugin install modelos-contratos-de-trabajo-espana@modelos-juridicos-laboral-espana
```

Cada plugin ocupa contexto en la conversación, así que conviene instalar solo los de los temas con los que se trabaja.

En Claude (web y escritorio) también se puede subir cada plugin como ZIP desde **Personalizar → Plugins**. Los ZIP están en la página de [versiones](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest): uno por plugin y [Laboral.zip](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/Laboral.zip) con todos.

## Plugins

| Plugin | Contenido | Skills | ZIP |
|---|---|---:|---|
| `modelos-contratos-de-trabajo-espana` | Contratos de trabajo: indefinidos, temporales y formativos · España | 85 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-contratos-de-trabajo-espana.zip) |
| `modelos-control-empresarial-y-datos-espana` | Videovigilancia, geolocalización y datos de la plantilla · España | 12 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-control-empresarial-y-datos-espana.zip) |
| `modelos-despidos-espana` | Cartas de despido y extinción del contrato · España | 37 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-despidos-espana.zip) |
| `modelos-ere-y-erte-espana` | ERE, ERTE y Mecanismo RED · España | 37 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-ere-y-erte-espana.zip) |
| `modelos-inspeccion-de-trabajo-espana` | Alegaciones y recursos ante la Inspección de Trabajo · España | 56 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-inspeccion-de-trabajo-espana.zip) |
| `modelos-jornada-y-conciliacion-espana` | Jornada, permisos, teletrabajo y conciliación · España | 43 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-jornada-y-conciliacion-espana.zip) |
| `modelos-plan-de-igualdad-y-acoso-espana` | Planes de igualdad y protocolos de acoso y LGTBI · España | 36 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-plan-de-igualdad-y-acoso-espana.zip) |
| `modelos-proceso-laboral-espana` | Papeleta, demanda y suplicación en lo social · España | 29 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-proceso-laboral-espana.zip) |
| `modelos-salario-y-condiciones-espana` | Reclamar salarios y modificar condiciones · España | 24 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-salario-y-condiciones-espana.zip) |
| `modelos-sanciones-a-trabajadores-espana` | Cartas de sanción y expediente disciplinario · España | 30 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-sanciones-a-trabajadores-espana.zip) |
| `modelos-seguridad-social-espana` | Incapacidad, jubilación y accidentes de trabajo · España | 38 | [descargar](https://github.com/DerechoVirtual/modelos-juridicos-laboral-espana/releases/latest/download/modelos-seguridad-social-espana.zip) |

## Estructura

```
.claude-plugin/marketplace.json  catálogo del marketplace
plugins/<plugin>/                .claude-plugin/plugin.json, .mcp.json, skills/, README.md, PRIVACY.md, LICENSE
```

## Aviso

Los escritos que se generan son borradores que debe revisar un abogado; no constituyen asesoramiento jurídico. Las skills no guardan datos del cliente y las consultas a Jurisprudenciator describen el problema jurídico, no los datos personales.

Soporte: https://jurisprudenciator.lexiaipro.org/incidencias · Licencia: ver [LICENSE](LICENSE).
