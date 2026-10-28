---
description: "Defines groundwater-connected reservoir cells and their hydraulic properties used by the SWAT+ gwflow reservoir routing routines."
---

# rescell.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater-connected reservoir cells and their hydraulic properties used by the SWAT+ gwflow reservoir routing routines.

SWAT+ uses the literal filename `rescell.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1113). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_cell](res_cell.md) | index of the groundwater cell connected to the reservoir | integer | n/a | — | — |
| [res_id](res_id.md) | identifier of the reservoir receiving the groundwater connection | integer | n/a | — | — |
| [res_stage](res_stage.md) | stage height associated with the reservoir connection | real | — | — | — |

### Additional read at line 1141

Source condition/loop: `if(gw_res_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_thick](res_thick.md) | thickness of the reservoir connection used in conductance calculations | real | — | — | — |

### Additional read at line 1142

Source condition/loop: `if(gw_res_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [res_K](res_k.md) | hydraulic conductivity of the reservoir connection material | real | — | — | — |

### Additional read at line 1143

Source condition/loop: `if(gw_res_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_res_cells](num_res_cells.md) | number of groundwater-connected reservoir cells to read | integer | n/a | — | — |
