---
description: "Defines groundwater water-balance groups, each aggregating one or more model cells for consolidated groundwater water-balance reporting. The file supplies the count of groups, the maximum cell count per group, the per-group cell count, and the cell identifier for each member cell."
---

# gwflow.wbgroups

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater water-balance groups, each aggregating one or more model cells for consolidated groundwater water-balance reporting. The file supplies the count of groups, the maximum cell count per group, the per-group cell count, and the cell identifier for each member cell.

SWAT+ uses the literal filename `gwflow.wbgroups` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_output.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L138). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Record at line 140

Source condition/loop: `if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_wb_grp_num](gw_wb_grp_num.md) | Number of groundwater water-balance groups defined for output aggregation | integer | n/a | — | — |

### Record at line 141

Source condition/loop: `if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [max_num](max_num.md) | Maximum number of cells allocated for any single water-balance group | integer | n/a | — | — |

### Record at line 149

Source condition/loop: `if(i_exist) then > do i=1,gw_wb_grp_num`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_wb_grp_ncell(i)](gw_wb_grp_ncell_i.md) | Number of cells assigned to water-balance group i | integer | n/a | — | — |

### Record at line 152

Source condition/loop: `if(i_exist) then > do i=1,gw_wb_grp_num > do j=1,gw_wb_grp_ncell(i)`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wb_cell](wb_cell.md) | Cell identifier assigned to position j within water-balance group i | integer | n/a | — | — |
