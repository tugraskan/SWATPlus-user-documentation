---
description: "This file defines groundwater cells, including their geometry, property zones, initial heads, and boundary settings."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines groundwater cells, including their geometry, property zones, initial heads, and boundary settings.

SWAT+ looks for `cells.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L429) reader.

# cells.gw

After the title and column headings, enter one row per groundwater cell in cell-index order. The first 14 columns are required. Columns 15–23 are optional; use `null` for an optional value that is not supplied.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id_in](cell_id_in.md) | Cell identifier that must equal the row index of the cell being read | integer | n/a | — | — |
| [cell_name](cell_name.md) | Label identifying the cell, typically of the form cellNNNN | string | n/a | — | — |
| [cell_gis_id(i)](cell_gis_id_i.md) | GIS identifier linking the cell to its polygon in the gwflowcells shapefile | integer | n/a | — | — |
| [stat](stat.md) | Status flag indicating whether the cell is inactive (0), active (1), or a boundary (2) | integer | n/a | — | — |
| [elev](elev.md) | Ground surface elevation at the cell | real | — | — | — |
| [thck](thck.md) | Aquifer thickness | real | — | — | — |
| [K_zone](k_zone.md) | Index selecting the hydraulic conductivity zone assigned to the cell | integer | n/a | — | — |
| [Sy_zone](sy_zone.md) | Index selecting the specific yield zone assigned to the cell | integer | n/a | — | — |
| [delay(i)](delay_i.md) | Delay value associated with the cell | real | — | — | — |
| [exdp](exdp.md) | Depth from the ground surface beyond which groundwater evapotranspiration no longer occurs | real | — | — | — |
| [init](init.md) | Initial groundwater head at the start of the simulation, raised to the aquifer bottom if below it | real | — | — | — |
| [xcrd](xcrd.md) | X-coordinate of the cell centroid in the model projection | real | — | — | — |
| [ycrd](ycrd.md) | Y-coordinate of the cell centroid in the model projection | real | — | — | — |
| [area](area.md) | Surface area of the cell | real | — | — | — |
| [cell_strK_over(i)](cell_strk_over_i.md) | Saturated hydraulic conductivity assigned to an overlying layer or feature for the cell | real | — | — | — |
| [cell_strthick_over(i)](cell_strthick_over_i.md) | Thickness of an overlying layer or feature for the cell | real | — | — | — |
| [bc_type_array(i)](bc_type_array_i.md) | Code identifying the boundary type applied to the cell when it is treated as a boundary cell | real | — | — | — |
| [cell_tile_depth_over(i)](cell_tile_depth_over_i.md) | Tile drainage depth assigned to the cell | real | — | — | — |
| [cell_tile_area_over(i)](cell_tile_area_over_i.md) | Tile drainage area assigned to the cell | real | — | — | — |
| [cell_tile_K_over(i)](cell_tile_k_over_i.md) | Tile drainage hydraulic conductivity assigned to the cell | real | — | — | — |
| [cell_row(i)](cell_row_i.md) | Structured-grid row index assigned to the cell for cell-definition output | integer | n/a | — | — |
| [cell_col(i)](cell_col_i.md) | Structured-grid column index assigned to the cell for cell-definition output | integer | n/a | — | — |
| [cell_init_temp(i)](cell_init_temp_i.md) | Initial groundwater temperature assigned to the cell for heat-transport simulations | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
