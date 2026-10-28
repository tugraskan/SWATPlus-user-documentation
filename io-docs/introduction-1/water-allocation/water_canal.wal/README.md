---
description: "This file defines canals used for water allocation, including their dimensions, outflow settings, and seepage to aquifers."
---

{% hint style="info" %}
Generation of this exact file format has not been verified in SWAT+ Editor. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines canals used for water allocation, including their dimensions, outflow settings, and seepage to aquifers.

SWAT+ looks for `water_canal.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_canal_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_canal_read.f90#L30) reader.

# water_canal.wal

The file contains a title line, a line giving the [number of canals](imax.md), a line of column headings, and one data row per canal. Each canal row contains the fields below. The aquifer loss fractions are additional values at the end of that same row.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Canal record number | integer | n/a | — | — |
| [name](name.md) | Canal name | string | n/a | — | — |
| [w_sta](w_sta.md) | Weather station name | string | n/a | — | — |
| [init](init.md) | Initial concentration-set name | string | n/a | — | — |
| [dtbl](dtbl.md) | Outflow decision-table name | string | n/a | — | — |
| [ddown_days](ddown_days.md) | Storage drawdown time | real | days | — | — |
| [w](w.md) | Canal bottom width | real | m | — | — |
| [d](d.md) | Canal depth | real | m | — | — |
| [l](l.md) | Canal length | real | km | — | — |
| [s](s.md) | Canal slope | real | — | — | — |
| [ss](ss.md) | Canal side slope | real | m/m | — | — |
| [sat_con](sat_con.md) | Canal seepage conductivity | real | mm/day | — | — |
| [evap_co](evap_co.md) | Water fraction retained after evaporation adjustment | real | fraction | — | — |
| [num_aqu](num_aqu.md) | Number of aquifer loss fractions | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | Seepage fraction assigned to each aquifer | real | fraction | — | — |

For example, when `num_aqu` is 2, put two aquifer loss fractions after it. Do not repeat the canal fields on a second row.

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
