---
description: "Provides tile drainage configuration read into the groundwater flow module when the tile drainage option is enabled (gw_tile_flag == 1). The file supplies a single set of scalar parameters applied across all tile-enabled groundwater cells, an optional group-flag block that defines tile cell groups, and—when the grid is structured—a per-cell tile drainage flag grid."
---

# tile.gw

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides tile drainage configuration read into the groundwater flow module when the tile drainage option is enabled (gw_tile_flag == 1). The file supplies a single set of scalar parameters applied across all tile-enabled groundwater cells, an optional group-flag block that defines tile cell groups, and—when the grid is structured—a per-cell tile drainage flag grid.

SWAT+ uses the literal filename `tile.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1024). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record.

### Additional read at line 1030

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_depth_val](tile_depth_val.md) | Scalar tile drainage depth value copied to the per-cell gw_tile_depth array for all tile-enabled groundwater cells | real | — | — | — |

### Additional read at line 1031

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_drain_area_val](tile_drain_area_val.md) | Scalar tile drain area value copied to the per-cell gw_tile_drain_area array for all tile-enabled groundwater cells | real | — | — | — |

### Additional read at line 1032

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_K_val](tile_k_val.md) | Scalar tile hydraulic conductivity value copied to the per-cell gw_tile_K array for all tile-enabled groundwater cells | real | — | — | — |

### Additional read at line 1045

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_group_flag](gw_tile_group_flag.md) | Flag indicating whether tile cell grouping is active (1 = grouping active; 0 = no grouping) | integer | n/a | — | — |

### Additional read at line 1047

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then > if(gw_tile_group_flag.eq.1) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_num_group](gw_tile_num_group.md) | Number of tile cell groups when grouping is active; also used to size group-related allocations and loop bounds | integer | n/a | — | — |

### Additional read at line 1051

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then > if(gw_tile_group_flag.eq.1) then > do i=1,gw_tile_num_group`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_tile_cells(i)](num_tile_cells_i.md) | Per-group count of tile cells; the inner loop bound when reading each group's cell membership list | integer | n/a | — | — |

### Additional read at line 1053

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then > if(gw_tile_group_flag.eq.1) then > do i=1,gw_tile_num_group > do j=1,num_tile_cells(i)`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_groups(i,j)](gw_tile_groups_i_j.md) | Cell identifier within a tile cell group; the value indexes into groundwater storage and solute arrays during grouped tile drainage summation | integer | n/a | — | — |

### Additional read at line 1065

Source condition/loop: `if(gw_tile_flag == 1) then > if(i_exist) then > if(grid_type == "structured") then > do i=1,grid_nrow`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_int(i,j)](grid_int_i_j.md) | Per-cell integer value read on the structured grid; copied to the groundwater state tile flag (gw_state(cell_id_usg(i,j))%tile) for each structured grid cell | integer | n/a | — | — |

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile](tile.md) | Per-groundwater-cell tile drainage flag (0 = no tile drainage; 1 = tile drainage present) | integer | n/a | — | — |
