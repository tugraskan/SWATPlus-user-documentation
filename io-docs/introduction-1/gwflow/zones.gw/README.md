---
description: "Aquifer, streambed and thermal properties by zone."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies aquifer, streambed and thermal properties by zone. Cells point to zones through `K_zone` and `Sy_zone` in [cells.gw](../cells.gw/README.md); channel connections point to zones through `chan_zone` in [chancell.gw](../chancell.gw/README.md).

SWAT+ looks for `zones.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L372-L405) reader.

# zones.gw

The first two lines are a title and column headings. Each following line is one zone; fields are separated by spaces. The zone number is the line's position: the first data line is zone 1. Do not leave blank lines between zones: the count skips them, but the values are read line by line ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L376-L404)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [zone_id](zone_id.md) | Zone label; not read | integer | n/a | — | — |
| [aquifer_K](aquifer_k.md) | Aquifer hydraulic conductivity | real | m/day | — | — |
| [aquifer_Sy](aquifer_sy.md) | Aquifer specific yield | real | fraction | — | 0 to 1 |
| [streambed_K](streambed_k.md) | Streambed hydraulic conductivity | real | m/day | — | — |
| [streambed_thick](streambed_thick.md) | Streambed thickness | real | m | — | — |
| [thermal_K](thermal_k.md) | Thermal conductivity (optional; `null` = 0) | real | J/(day·m·°C) | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
