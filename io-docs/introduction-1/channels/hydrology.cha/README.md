---
description: "This file contains channel geometry and hydraulic parameters."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains channel geometry and hydraulic parameters.

{% hint style="info" %}
[`proc_cha.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cha.f90#L19-L41) reads `hydrology.cha` and initializes `chan` travel-time coefficients, but daily `case ("chan")` routing in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out. Active channel routing uses [`hyd-sed-lte.cha`](../hyd-sed-lte.cha/).
{% endhint %}

# hydrology.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | default | — |
| [w](w.md) | Average width of the main channel | real | m | 2.0 | — |
| [d](d.md) | Average depth of the main channel | real | m | 0.5 | — |
| [s](s.md) | Average longitudinal slope of the main channel | real | m/m | 0.01 | — |
| [l](l.md) | Length of the main channel within the subbasin | real | km | 0.1 | — |
| [n](n.md) | Manning's n roughness coefficient for the main channel | real | none | 0.05 | 0.01-0.70 |
| [k](k.md) | Effective hydraulic conductivity of the main channel alluvium | real | mm/h | 0.01 | — |
| [wdr](wdr.md) | Ratio of channel width to depth | real | m/m | 6.0 | — |
| [alpha_bnk](alpha_bnk.md) | Alpha factor used in the bank storage recession curve | real | days | 0.03 | — |
| [side](side.md) | Change in horizontal distance per unit of vertical change on the channel side slope | real | none | 0.0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
