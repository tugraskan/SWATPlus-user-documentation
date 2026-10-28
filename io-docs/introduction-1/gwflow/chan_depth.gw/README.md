---
description: "This file supplies daily channel-water depths for the depth zones used by GWFlow."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies daily channel-water depths for the depth zones used by GWFlow.

SWAT+ looks for `chan_depth.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_chan_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_chan_read.f90#L89) reader.

# chan_depth.gw

After the title and column headings, enter daily rows containing two date columns and one depth for each configured depth zone. Keep the rows in simulation order: the date columns do not select or match the simulation day.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [jday](jday.md) | First date column of a time-series row | integer | n/a | — | — |
| [year](year.md) | Second date column of a time-series row | integer | n/a | — | — |
| [depth_by_zone](depth_by_zone.md) | Depth value for each configured depth zone | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
