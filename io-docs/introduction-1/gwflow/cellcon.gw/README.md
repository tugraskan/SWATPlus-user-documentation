---
description: "This file lists the neighboring groundwater cells connected to each cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the neighboring groundwater cells connected to each cell.

SWAT+ looks for `cellcon.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L505) reader.

# cellcon.gw

After the title and column headings, enter one row per groundwater cell in cell-index order. Each row contains the cell identifier, its neighbor count, and that many neighbor identifiers.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Cell identifier | integer | n/a | — | — |
| [ncon](ncon.md) | Number of neighbor cell identifiers that follow in this record | integer | n/a | — | — |
| [neighbor_cell_id](neighbor_cell_id.md) | Identifier of a cell hydraulically connected to the row's cell | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
