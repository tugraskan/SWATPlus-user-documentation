---
description: "This file contains channel geometry and hydraulic parameters."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains channel geometry and hydraulic parameters.

# hydrology.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [w](w.md) | Average width of the main channel | real | — | — | — |
| [d](d.md) | Average depth of the main channel | real | — | — | — |
| [s](s.md) | Average longitudinal slope of the main channel | real | — | — | — |
| [l](l.md) | Length of the main channel within the subbasin | real | — | — | — |
| [n](n.md) | Manning's n roughness coefficient for the main channel | real | — | — | — |
| [k](k.md) | Record number | real | — | — | — |
| [wdr](wdr.md) | Ratio of channel width to depth | real | — | — | — |
| [alpha_bnk](alpha_bnk.md) | Alpha factor used in the bank storage recession curve | real | — | — | — |
| [side](side.md) | Change in horizontal distance per unit of vertical change on the channel side slope | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
