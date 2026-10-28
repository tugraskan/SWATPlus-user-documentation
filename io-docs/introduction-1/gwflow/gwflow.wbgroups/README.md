---
description: "This file groups groundwater cells for water-balance reporting."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file groups groundwater cells for water-balance reporting.

SWAT+ looks for `gwflow.wbgroups` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_output.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L138) reader.

# gwflow.wbgroups

The file starts with one title line, then the number of groups and the maximum cells per group on separate lines. Each group has a label line, its cell count on the next line, and one cell identifier per following line.

## Number of groups

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_wb_grp_num](gw_wb_grp_num.md) | Number of groundwater water-balance groups defined for output aggregation | integer | n/a | — | — |

## Maximum group size

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_num](max_num.md) | Maximum cells in a group | integer | n/a | — | — |

## Cells per group

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_wb_grp_ncell(i)](gw_wb_grp_ncell_i.md) | Number of cells assigned to water-balance group i | integer | n/a | — | — |

## Group members

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wb_cell](wb_cell.md) | Cell identifier assigned to position j within water-balance group i | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
