---
description: "Geometry, property zones, initial heads and optional overrides for each groundwater cell."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines each groundwater cell: its status, geometry, property zones and initial head, plus optional per-cell overrides.

SWAT+ looks for `cells.gw` in the simulation working directory; it is not selected through `file.cio`. See the [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L429-L500) reader.

# cells.gw

The first two lines are a title and column headings. Then give one line per cell, `ncell` lines in cell order, with fields separated by spaces. The first 14 columns are required; a line with fewer stops the run with a message in the GWFlow record file. Columns 15–23 are optional and positional: to give a later column, fill the ones before it, using `null` where there is no value ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L432-L498)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [cell_id_in](cell_id_in.md) | Cell number; must equal the line's position | integer | n/a | — | 1 to ncell |
| [cell_name](cell_name.md) | Cell name for output (16 characters) | string | n/a | — | — |
| [cell_gis_id(i)](cell_gis_id_i.md) | GIS identifier written to per-cell output | integer | n/a | — | — |
| [stat](stat.md) | Status: 0 inactive, 1 active, 2 boundary | integer | n/a | — | 0, 1, 2 |
| [elev](elev.md) | Ground-surface elevation | real | m | — | — |
| [thck](thck.md) | Aquifer thickness | real | m | — | — |
| [K_zone](k_zone.md) | Zone for hydraulic and thermal conductivity | integer | n/a | — | rows of zones.gw |
| [Sy_zone](sy_zone.md) | Zone for specific yield | integer | n/a | — | rows of zones.gw |
| [delay(i)](delay_i.md) | Recharge delay | real | day | — | — |
| [exdp](exdp.md) | Groundwater ET extinction depth | real | m | — | — |
| [init](init.md) | Initial head | real | m | — | — |
| [xcrd](xcrd.md) | x coordinate of the cell centroid | real | m | — | — |
| [ycrd](ycrd.md) | y coordinate of the cell centroid | real | m | — | — |
| [area](area.md) | Cell area | real | m² | — | — |
| [cell_strK_over(i)](cell_strk_over_i.md) | Streambed conductivity for channels in this cell. Optional; `null` or a missing column keeps the default. | real | m/day | — | — |
| [cell_strthick_over(i)](cell_strthick_over_i.md) | Streambed thickness for channels in this cell. Optional; `null` or a missing column keeps the default. | real | m | — | — |
| [bc_type_array(i)](bc_type_array_i.md) | Boundary type for this cell. Optional; `null` or a missing column keeps the default. | real | n/a | — | — |
| [cell_tile_depth_over(i)](cell_tile_depth_over_i.md) | Tile depth for this cell. Optional; `null` or a missing column keeps the default. | real | m | — | — |
| [cell_tile_area_over(i)](cell_tile_area_over_i.md) | Tile drain area for this cell. Optional; `null` or a missing column keeps the default. | real | m² | — | — |
| [cell_tile_K_over(i)](cell_tile_k_over_i.md) | Tile conductivity for this cell. Optional; `null` or a missing column keeps the default. | real | — | — | — |
| [cell_row(i)](cell_row_i.md) | Structured-grid row, for output only. Optional; `null` or a missing column keeps the default. | integer | n/a | 0 | — |
| [cell_col(i)](cell_col_i.md) | Structured-grid column, for output only. Optional; `null` or a missing column keeps the default. | integer | n/a | 0 | — |
| [cell_init_temp(i)](cell_init_temp_i.md) | Initial groundwater temperature. Optional; `null` or a missing column keeps the default. | real | °C | 0 | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
