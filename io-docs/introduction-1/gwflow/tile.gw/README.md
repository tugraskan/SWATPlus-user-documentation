---
description: "This file defines tile drainage settings and the groundwater cells where they apply."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines tile drainage settings and the groundwater cells where they apply.

SWAT+ looks for `tile.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1024) reader.

# tile.gw

After the title, enter common tile depth, drain area, and conductivity on separate lines, followed by the group flag. If grouping is enabled, give the group count and, for each group, a label line, cell count, and one member identifier per line. Follow the tile-flag headings with either structured-grid rows or one flag per unstructured cell; use only the format matching the grid.

## Tile depth

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_depth_val](tile_depth_val.md) | Common tile drain depth | real | — | — | — |

## Drain area

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_drain_area_val](tile_drain_area_val.md) | Common tile drain area | real | — | — | — |

## Tile conductivity

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile_K_val](tile_k_val.md) | Common tile hydraulic conductivity | real | — | — | — |

## Cell-group setting

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_group_flag](gw_tile_group_flag.md) | Flag indicating whether tile cell grouping is active (1 = grouping active; 0 = no grouping) | integer | n/a | — | — |

## Group count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_num_group](gw_tile_num_group.md) | Number of tile groups | integer | n/a | — | — |

## Cells per group

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_tile_cells(i)](num_tile_cells_i.md) | Per-group count of tile cells; the inner loop bound when reading each group's cell membership list | integer | n/a | — | — |

## Group members

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [gw_tile_groups(i,j)](gw_tile_groups_i_j.md) | Cell identifier within a tile cell group | integer | n/a | — | — |

## Structured-grid tile flags

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_int(i,j)](grid_int_i_j.md) | Structured-grid tile flag | integer | n/a | — | — |

## Cell tile flags

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [tile](tile.md) | Per-groundwater-cell tile drainage flag (0 = no tile drainage; 1 = tile drainage present) | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
