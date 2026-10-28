---
description: "This file contains named transplant parameter sets."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains named transplant parameter sets.

SWAT+ looks for `transplant.ops` in the simulation working directory; it is not selected through `file.cio`. See the [plant_transplant_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_transplant_read.f90#L24) reader.

# transplant.ops

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [lai](lai.md) | Leaf area index | real | m²/m² | — | — |
| [bioms](bioms.md) | Initial biomass | real | kg/ha | — | — |
| [phuacc](phuacc.md) | Heat-unit accumulation fraction | real | fraction | — | — |
| [fr_yrmat](fr_yrmat.md) | Fraction of years to maturity completed | real | fraction | — | — |
| [pop](pop.md) | Plant population | real | plants/m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
