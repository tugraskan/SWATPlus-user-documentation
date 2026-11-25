---
description: "This file contains named transplant parameter sets."
---

# transplant.ops

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains named transplant parameter sets applied during `plnt` or `plant` operations in [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L1-L61). SWAT+ looks for `transplant.ops` in the simulation working directory (loaded in [`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L15) via [`plant_transplant_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L24-L45)); it is not selected through `file.cio`.

The first two lines contain a title and column headings. Each following row contains the fields below, in this order. In SWAT+ main (`6f515368`), [lai](lai.md) is parsed into memory but is not used in simulation calculations.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [lai](lai.md) | Leaf area index (read but not used in main 6f515368) | real | m^2/m^2 | — | — |
| [bioms](bioms.md) | Initial biomass | real | kg/ha | — | — |
| [phuacc](phuacc.md) | Heat-unit accumulation fraction | real | fraction | — | — |
| [fr\_yrmat](fr_yrmat.md) | Fraction of years to maturity completed | real | fraction | — | — |
| [pop](pop.md) | Plant population | real | plants/m^2 | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
