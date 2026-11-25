---
description: "Daily diversion volumes for each recharge pond."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file gives the volume diverted into each recharge pond each day. Without it, ponds receive no diversions.

SWAT+ looks for `pond_div.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2011-L2020) reader.

# pond_div.gw

The first two lines are a title and column headings. Then give one line per simulated day, from the first day: year, month, day, then one volume per pond in the order of `ponds.gw`. SWAT+ reads one line each day and does not check the dates ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L54-L61)). Reading past the end stops the run.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [year](year.md) | Year; not checked | integer | n/a | — | — |
| [month](month.md) | Month; not checked | integer | n/a | — | — |
| [day](day.md) | Day; not checked | integer | n/a | — | — |
| [div](div.md) | Volume to divert to each pond | real | m³ | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
