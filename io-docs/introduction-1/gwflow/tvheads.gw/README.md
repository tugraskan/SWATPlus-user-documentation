---
description: "This file supplies prescribed groundwater heads that change over time."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies prescribed groundwater heads that change over time.

SWAT+ looks for `tvheads.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1463) reader.

# tvheads.gw

After the title and column headings, enter one cell identifier followed by that cell’s prescribed heads for the configured time periods.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Groundwater cell identifier for this prescribed-head series | integer | n/a | — | — |
| [gw_tvh_vals(i,j)](gw_tvh_vals_i_j.md) | Prescribed head value for cell i and time index j | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
