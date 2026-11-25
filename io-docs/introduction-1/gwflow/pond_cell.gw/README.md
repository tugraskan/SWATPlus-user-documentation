---
description: "Cells under each recharge pond and their connection areas."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file lists the cells under each recharge pond. It is read when [ponds.gw](../ponds.gw/README.md) exists.

SWAT+ looks for `pond_cell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1978-L2010) reader.

# pond_cell.gw

The first two lines are a title and column headings. Then give one line per pond–cell connection, in any order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1998-L2009)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dum_id](dum_id.md) | Pond number | integer | n/a | — | — |
| [cell_num](cell_num.md) | Cell under the pond | integer | n/a | — | 1 to ncell |
| [dum4](dum4.md) | Connection area | real | m² | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
