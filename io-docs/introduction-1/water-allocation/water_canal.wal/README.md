---
description: "This file defines canals used for water allocation, including their dimensions, outflow settings, and seepage to aquifers."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L29-L66), the outer `do ... end do` loop lacks an `exit` statement after reading `imax` records. Note also that [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L61-L63) leaves weather-station, initial-concentration, and decision-table crosswalks unimplemented (`!!` comments only).
{% endhint %}

This file defines canals used for water allocation, including their dimensions, outflow settings, and seepage to aquifers.

SWAT+ looks for `water_canal.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L30) reader.

# water_canal.wal

The file contains a title line, the canal count, column headings, and one data row per canal with `num_aqu` trailing aquifer loss fractions.

## Number of records

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of canal records | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [i](i.md) | Canal record number | integer | n/a | — | — |
| [name](name.md) | Canal name | string | n/a | — | — |
| [w_sta](w_sta.md) | Weather station name | string | n/a | — | — |
| [init](init.md) | Initial concentration-set name | string | n/a | — | — |
| [dtbl](dtbl.md) | Outflow decision-table name (`null` for drawdown-day outflow) | string | n/a | — | — |
| [ddown_days](ddown_days.md) | Storage drawdown time | real | days | — | > 0 |
| [w](w.md) | Canal bottom width | real | m | — | — |
| [d](d.md) | Canal depth | real | m | — | — |
| [l](l.md) | Canal length | real | km | — | — |
| [s](s.md) | Canal slope | real | m | — | — |
| [ss](ss.md) | Canal side slope (horizontal/vertical) | real | m/m | — | — |
| [sat_con](sat_con.md) | Canal seepage conductivity | real | mm/day | — | — |
| [evap_co](evap_co.md) | Storage retention multiplier after evaporation | real | fraction | — | 0–1 |
| [num_aqu](num_aqu.md) | Number of aquifer loss fractions | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | Seepage fraction assigned to each aquifer | real | fraction | — | 0–1 |

For example, when `num_aqu` is `2`, append two aquifer loss fractions at the end of the same canal row.

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
