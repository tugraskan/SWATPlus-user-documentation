---
description: "The minerals.gw file specifies the mass fraction of each dissolved salt mineral within groundwater cells, used by the GW flow solute transport module when groundwater solute routing is enabled. It defines how many salt minerals are tracked and provides either a single uniform value or a grid/array of per-cell values for each mineral."
---

# minerals.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The minerals.gw file specifies the mass fraction of each dissolved salt mineral within groundwater cells, used by the GW flow solute transport module when groundwater solute routing is enabled. It defines how many salt minerals are tracked and provides either a single uniform value or a grid/array of per-cell values for each mineral.

SWAT+ uses the literal filename `minerals.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1681). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Record at line 1683

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(gwsol_salt == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_nminl](gw_nminl.md) | the total number of salt minerals to be read and tracked for groundwater solute transport | integer | n/a | — | — |

### Record at line 1695

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(gwsol_salt == 1) then > if(i_exist) then > if(grid_type == "structured") then > do m=1,gw_nminl`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [read_type](read_type.md) | the method used to supply values for each salt mineral, either a single uniform value or an array of per-cell values | string | n/a | — | — |

### Record at line 1697

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(gwsol_salt == 1) then > if(i_exist) then > if(grid_type == "structured") then > do m=1,gw_nminl > if(read_type == "single") then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [single_value](single_value.md) | the uniform mass fraction of a salt mineral applied to all groundwater cells when read_type is set to single | real | — | — | — |

### Record at line 1701

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(gwsol_salt == 1) then > if(i_exist) then > if(grid_type == "structured") then > do m=1,gw_nminl > if(read_type == "single") then / elseif(read_type == "array") then > do i=1,grid_nrow`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_val(i,j)](grid_val_i_j.md) | the per-cell mass fraction of a salt mineral for a structured grid when read_type is set to array, indexed by row and column | real | — | — | — |

### Record at line 1708

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(gwsol_salt == 1) then > if(i_exist) then > if(grid_type == "structured") then / elseif(grid_type == "unstructured") then > do i=1,ncell`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [fract(m)](fract_m.md) | the mass fraction of salt mineral m within a groundwater cell, stored for each mineral and used in solute transport calculations | real | — | — | — |
