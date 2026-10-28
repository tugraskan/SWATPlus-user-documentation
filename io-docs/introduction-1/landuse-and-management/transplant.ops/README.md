---
description: This file contains named transplant parameter sets.
---

# transplant.ops

{% hint style="info" %}
This file is supported by the SWAT+ model, but no exporter was found in the inspected SWAT+ Editor version. It may need to be supplied separately. Editor checkout checked: `1efec55`.

The table below is based on the SWAT+ Fortran source code. Its contents should not be assumed to match the labels, defaults, or options available in SWAT+ Editor. A dash means that no recommended default or range has been established here; it is not a Fortran initialization value.
{% endhint %}

Named transplant parameter sets used by scheduled management operations and land-use decision-table actions. Each record supplies the state used when a transplant operation is executed.

SWAT+ looks directly for the literal filename `transplant.ops` in the simulation working directory; this filename is not selected through `file.cio`. It is read by [plant_transplant_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_transplant_read.f90#L24). If the file is absent, no transplant records are loaded from it.

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
