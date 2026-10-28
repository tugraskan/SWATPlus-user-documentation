---
description: "This file supplies groundwater property values for aquifer and streambed zones."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies groundwater property values for aquifer and streambed zones.

SWAT+ looks for `zones.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L372) reader.

# zones.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [zone_id](zone_id.md) | Leading label token for the zone record. This parameter-loading loop does not use it to choose the array index | string | n/a | — | — |
| [aquifer_K](aquifer_k.md) | Aquifer hydraulic conductivity for the indexed zone | real | — | — | — |
| [aquifer_Sy](aquifer_sy.md) | Aquifer specific yield for the indexed zone | real | — | — | — |
| [streambed_K](streambed_k.md) | Streambed hydraulic conductivity for the indexed zone | real | — | — | — |
| [streambed_thick](streambed_thick.md) | Streambed thickness for the indexed zone | real | — | — | — |
| [thermal_K](thermal_k.md) | Thermal conductivity for the indexed zone | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
