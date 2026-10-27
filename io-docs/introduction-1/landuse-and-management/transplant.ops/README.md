# transplant.ops

Named transplant parameter sets used by scheduled management operations and land-use decision-table actions. Each record supplies the state used when a transplant operation is executed.

SWAT+ looks directly for the literal filename `transplant.ops` in the simulation working directory; this filename is not selected through `file.cio`. If the file is absent, no transplant records are loaded.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Transplant parameter-set name | string | n/a | — | — |
| [lai](lai.md) | Leaf area index | real | m²/m² | — | — |
| [bioms](bioms.md) | Initial biomass | real | kg/ha | — | — |
| [phuacc](phuacc.md) | Heat-unit accumulation fraction | real | fraction | — | — |
| [fr_yrmat](fr_yrmat.md) | Fraction of years to maturity completed | real | fraction | — | — |
| [pop](pop.md) | Plant population | real | plants/m² | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.
