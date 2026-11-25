---
description: "Groups of cells whose daily water balance is written to output."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This optional file defines groups of cells; each group's daily groundwater balance is written to its own file, `gwflow_group_wb_day_` followed by the group number. It does not change the simulation.

SWAT+ looks for `gwflow.wbgroups` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L135-L179) reader.

# gwflow.wbgroups

Each item is on its own line: a title line, the number of groups, the largest group size, then for each group a label line, its cell count and one cell number per line ([`gwflow_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L139-L166)). The group number in the file name is written in two characters, so groups 1–9 get a leading space (`gwflow_group_wb_day_ 1`) and groups above 99 get `**`.

## Group count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_wb_grp_num](gw_wb_grp_num.md) | Number of groups | integer | n/a | — | 1 to 99 |

## Largest group

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [max_num](max_num.md) | Largest number of cells in any group | integer | n/a | — | — |

## Group size

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_wb_grp_ncell(i)](gw_wb_grp_ncell_i.md) | Number of cells in the group | integer | n/a | — | 1 to max_num |

## Group cells

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [wb_cell](wb_cell.md) | Cell number, one per line | integer | n/a | — | 1 to ncell |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
