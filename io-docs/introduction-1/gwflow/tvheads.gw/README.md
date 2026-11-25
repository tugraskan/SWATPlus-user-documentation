---
description: "Yearly heads for boundary cells; not used by the model."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file gives one head per simulation year for selected cells, intended as time-varying boundary heads.

SWAT+ looks for `tvheads.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1459-L1486) reader.

The values are read but never used: boundary cells keep their initial head for the whole run ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L155-L157)). This is listed in `MODEL_ISSUES.md`.

# tvheads.gw

The first two lines are a title and column headings. Then give one line per cell: the cell number and one head per simulation year ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1478-L1485)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_id](cell_id.md) | Cell number | integer | n/a | — | 1 to ncell |
| [gw_tvh_vals(i,j)](gw_tvh_vals_i_j.md) | Head for each simulation year | real | m | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
