---
description: "Defines each groundwater model cell's geometry, status, material properties, and boundary conditions for the GWFlow solver. One row per configured cell is read after skipping metadata and column-header records; the cell ID must equal its row index, and the initial head is raised to the cell bottom if it falls below."
---

# cells.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines each groundwater model cell's geometry, status, material properties, and boundary conditions for the GWFlow solver. One row per configured cell is read after skipping metadata and column-header records; the cell ID must equal its row index, and the initial head is raised to the cell bottom if it falls below.

SWAT+ uses the literal filename `cells.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L429). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Skip metadata and column-header records, then read one row per configured cell. Columns 1–14 are required; columns 15–23 are optional and accept the literal null sentinel. The cell ID must equal its row index. Initial head below the computed cell bottom is raised to that bottom by the reader.

### Cell record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id_in](cell_id_in.md) | Integer cell identifier that must equal the row index of the cell being read | integer | n/a | — | — |
| [cell_name](cell_name.md) | Character label identifying the cell, typically of the form cellNNNN | string | n/a | — | — |
| [cell_gis_id(i)](cell_gis_id_i.md) | Integer GIS identifier linking the cell to its polygon in the gwflowcells shapefile | integer | n/a | — | — |
| [stat](stat.md) | Integer status flag indicating whether the cell is inactive (0), active (1), or a boundary (2) | integer | n/a | — | — |
| [elev](elev.md) | Real ground surface elevation at the cell, used as the top of the aquifer | real | — | — | — |
| [thck](thck.md) | Real aquifer thickness, used together with surface elevation to compute the aquifer bottom | real | — | — | — |
| [K_zone](k_zone.md) | Integer index selecting the hydraulic conductivity zone assigned to the cell | integer | n/a | — | — |
| [Sy_zone](sy_zone.md) | Integer index selecting the specific yield zone assigned to the cell | integer | n/a | — | — |
| [delay(i)](delay_i.md) | Real delay value associated with the cell, used in cell-level routing or storage computations | real | — | — | — |
| [exdp](exdp.md) | Real depth from the ground surface beyond which groundwater evapotranspiration no longer occurs | real | — | — | — |
| [init](init.md) | Real initial groundwater head at the start of the simulation, raised to the aquifer bottom if below it | real | — | — | — |
| [xcrd](xcrd.md) | Real x-coordinate of the cell centroid in the model projection | real | — | — | — |
| [ycrd](ycrd.md) | Real y-coordinate of the cell centroid in the model projection | real | — | — | — |
| [area](area.md) | Real surface area of the cell, used in storage and flux calculations | real | — | — | — |
| [cell_strK_over(i)](cell_strk_over_i.md) | Optional real saturated hydraulic conductivity assigned to an overlying layer or feature for the cell (optional in this record) | real | — | — | — |
| [cell_strthick_over(i)](cell_strthick_over_i.md) | Optional real thickness of an overlying layer or feature for the cell (optional in this record) | real | — | — | — |
| [bc_type_array(i)](bc_type_array_i.md) | Optional real code identifying the boundary type applied to the cell when it is treated as a boundary cell (optional in this record) | real | — | — | — |
| [cell_tile_depth_over(i)](cell_tile_depth_over_i.md) | Optional real tile drainage depth assigned to the cell (optional in this record) | real | — | — | — |
| [cell_tile_area_over(i)](cell_tile_area_over_i.md) | Optional real tile drainage area assigned to the cell (optional in this record) | real | — | — | — |
| [cell_tile_K_over(i)](cell_tile_k_over_i.md) | Optional real tile drainage hydraulic conductivity assigned to the cell (optional in this record) | real | — | — | — |
| [cell_row(i)](cell_row_i.md) | Optional integer structured-grid row index assigned to the cell for cell-definition output (optional in this record) | integer | n/a | — | — |
| [cell_col(i)](cell_col_i.md) | Optional integer structured-grid column index assigned to the cell for cell-definition output (optional in this record) | integer | n/a | — | — |
| [cell_init_temp(i)](cell_init_temp_i.md) | Optional real initial groundwater temperature assigned to the cell for heat-transport simulations (optional in this record) | real | — | — | — |
