---
description: "Tile-drain properties, optional output groups and the tiled cells."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file sets tile-drain properties and marks the cells that have tile drains. It is read only when `tile` is 1 in [codes.gw](../codes.gw/tile.md).

SWAT+ looks for `tile.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1020-L1079) reader.

# tile.gw

Each value is on its own line, in this order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1024-L1078)):

1. a title line;
2. `tile_depth_val`, `tile_drain_area_val`, `tile_K_val`;
3. `gw_tile_group_flag`;
4. if the flag is 1: `gw_tile_num_group`, then for each group a label line, `num_tile_cells(i)` and one cell number per line;
5. one heading line;
6. the tile flags: one `tile` value per line for all `ncell` cells (unstructured grid), or `n_rows` lines of `n_cols` values (structured grid).

The structured layout cannot be read in this source: the arrays it uses are never allocated ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1063-L1073)). This is listed in `MODEL_ISSUES.md`.

## Tile properties

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [tile_depth_val](tile_depth_val.md) | Tile depth below ground | real | m | — | — |
| [tile_drain_area_val](tile_drain_area_val.md) | Drain area per cell | real | m² | — | — |
| [tile_K_val](tile_k_val.md) | Tile conductivity | real | — | — | — |

## Output groups

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [gw_tile_group_flag](gw_tile_group_flag.md) | 1 = groups follow | integer | n/a | 0 | 0 or 1 |
| [gw_tile_num_group](gw_tile_num_group.md) | Number of groups | integer | n/a | — | 1 to 50 |
| [num_tile_cells(i)](num_tile_cells_i.md) | Number of cells in the group | integer | n/a | — | 1 to 5000 |
| [gw_tile_groups(i,j)](gw_tile_groups_i_j.md) | Cell number in the group, one per line | integer | n/a | — | 1 to ncell |

## Tile flags

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [tile](tile.md) | Tile flag per cell, one per line (unstructured grid) | integer | n/a | 0 | 0 or 1 |
| [grid_int(i,j)](grid_int_i_j.md) | Tile flags by row and column (structured grid) | integer | n/a | 0 | 0 or 1 |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
