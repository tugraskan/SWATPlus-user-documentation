---
description: "Groups of cells whose daily groundwater-channel exchange is written to output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file defines groups of cells; the daily groundwater–channel exchange of each group is written to `gwflow_gwsw_group_day.txt`. It does not change the simulation.

SWAT+ looks for `sw_group.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2302-L2344) reader.

# sw_group.gw

The first two lines are a title and column headings. Then give one group per line: a label, the number of cells and the cell numbers, separated by spaces. A line holds at most 40 values, so a group can have at most 38 cells. Groups are numbered by line order. Do not leave blank lines between groups: the count skips them, but the groups are read line by line ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2313-L2338)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [group_id](group_id.md) | Group label; not read | string | n/a | — | — |
| [ncell](ncell.md) | Number of cells in the group | integer | n/a | — | 1 to 38 |
| [cell_id](cell_id.md) | Cell number, repeated `ncell` times | integer | n/a | — | 1 to ncell |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
