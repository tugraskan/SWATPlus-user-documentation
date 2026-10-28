---
description: "This file supplies daily diversion volumes for recharge ponds."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies daily diversion volumes for recharge ponds.

SWAT+ looks for `pond_div.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2017) reader.

# pond_div.gw

After the title and column headings, enter one row per date: year, month, day, then one diversion volume for each configured pond.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [year](year.md) | Calendar year of the diversion time-series date | integer | n/a | — | — |
| [month](month.md) | Calendar month of the diversion time-series date | integer | n/a | — | — |
| [day](day.md) | Calendar day of the diversion time-series date | integer | n/a | — | — |
| [div](div.md) | Specified diversion volume applied to each pond on the given date, as declared in gw_pond_info(r)%div | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
