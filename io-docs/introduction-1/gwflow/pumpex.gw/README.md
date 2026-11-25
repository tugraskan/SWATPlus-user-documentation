---
description: "Specified groundwater pumping rates and periods by cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this filename. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies groundwater pumping from cells for given periods. It is read only when `pumpex` is 1 in [codes.gw](../codes.gw/pumpex.md).

SWAT+ looks for `pumpex.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L952-L1016) reader.

# pumpex.gw

The first two lines are a title and column headings. Each following line is one pumping period. To change the rate over time, add lines for the same cell with other periods. Lines for the same cell must be together: each run of lines with the same cell becomes one pump, and a pump can have at most 1,000 periods ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L961-L1009)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [header](header.md) | Label of the period | string | n/a | — | — |
| [pumpex_cell](pumpex_cell.md) | Groundwater cell number | integer | n/a | — | 1 to ncell |
| [gw_pumpex_rates_tmp](gw_pumpex_rates_tmp.md) | Pumping rate | real | m³/day | — | — |
| [pe_yr_s](pe_yr_s.md) | First year of the period | integer | year | — | — |
| [pe_dy_s](pe_dy_s.md) | First day of year of the period | integer | day | — | 1 to 365 |
| [pe_yr_e](pe_yr_e.md) | Last year of the period | integer | year | — | — |
| [pe_dy_e](pe_dy_e.md) | Last day of year of the period | integer | day | — | 1 to 365 |

## Dates

SWAT+ converts each date to a simulation day number with 365-day years ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L998-L1008)):

$$n = (y - y_{0}) \times 365 + d$$

where $y_{0}$ is the first simulation year. A year before $y_{0}$ gives day 1, whatever the day of year; a period that ended before the simulation started therefore pumps on the first day. Pumping happens on days $n_{s} \le n \le n_{e}$. In leap years the day numbers drift by one day per leap year.

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
