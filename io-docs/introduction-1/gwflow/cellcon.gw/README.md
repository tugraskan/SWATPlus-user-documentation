---
description: "Neighboring cells connected to each groundwater cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists, for each groundwater cell, the neighboring cells it exchanges water with.

SWAT+ looks for `cellcon.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L505-L526) reader.

# cellcon.gw

The first two lines are a title and column headings. Then give one line per cell, `ncell` lines in cell order: the cell number, the number of neighbors, and that many neighbor numbers, separated by spaces. A line has room for 40 values, so a cell can have at most 38 neighbors. A line with fewer than two values, or with a cell number that does not match its position, stops the run with a message in the GWFlow record file ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L508-L525)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_id](cell_id.md) | Cell number; must equal the line's position | integer | n/a | — | 1 to ncell |
| [ncon](ncon.md) | Number of neighbors that follow | integer | n/a | — | 0 to 38 |
| [neighbor_cell_id](neighbor_cell_id.md) | Neighbor cell number, repeated `ncon` times | integer | n/a | — | 1 to ncell |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
