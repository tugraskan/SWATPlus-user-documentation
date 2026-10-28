---
description: "This file specifies groundwater pumping volumes and the dates when pumping occurs in each groundwater cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this filename. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies groundwater pumping volumes and the dates when pumping occurs in each groundwater cell.

SWAT+ looks for `pumpex.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L958) reader.

# pumpex.gw

The first two lines contain a title and column headings. Each following row defines one pumping period. To change the pumping volume over time, add another row for the same cell with a different period. Keep rows for the same cell together.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [header](header.md) | Pumping-period label | string | n/a | — | — |
| [pumpex_cell](pumpex_cell.md) | Groundwater cell identifier | integer | n/a | — | — |
| [gw_pumpex_rates_tmp](gw_pumpex_rates_tmp.md) | Daily groundwater pumping volume | real | m³/day | — | — |
| [pe_yr_s](pe_yr_s.md) | Starting calendar year | integer | year | — | — |
| [pe_dy_s](pe_dy_s.md) | Starting day of year | integer | day | — | — |
| [pe_yr_e](pe_yr_e.md) | Ending calendar year | integer | year | — | — |
| [pe_dy_e](pe_dy_e.md) | Ending day of year | integer | day | — | — |

Pumping must also be enabled in the GWFlow settings. Dates use a calendar year and day of year, rather than month and day. The current date conversion uses 365 days per year.

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
