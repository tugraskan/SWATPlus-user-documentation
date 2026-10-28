---
description: "This file links recharge ponds to groundwater cells."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links recharge ponds to groundwater cells.

SWAT+ looks for `pond_cell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1980) reader.

# pond_cell.gw

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dum_id](dum_id.md) | Identifier of the pond whose groundwater cell count or cell list is being referenced by this record | integer | n/a | — | — |
| [cell_num](cell_num.md) | Model grid cell number associated with the pond on this record | integer | n/a | — | — |
| [dum4](dum4.md) | Real-valued parameter associated with the pond-cell linkage | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
