---
description: "This file contains the settings that control GWFlow processes and output."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains the settings that control GWFlow processes and output.

SWAT+ looks for `codes.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L225) reader.

# codes.gw

The file contains a title, a row of setting names, and a row of corresponding values. Each value matches the setting name directly above it. The table lists recognized settings; their columns may be reordered together with their values.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_type](grid_type.md) | Grid_type specifies the type of grid used in the groundwater model | string | n/a | — | — |
| [ncell](ncell.md) | Ncell indicates the total number of groundwater flow cells in the model domain | integer | n/a | — | — |
| [cell_size](cell_size.md) | Cell_size defines the size of each grid cell in the groundwater model | real | — | — | — |
| [n_rows](n_rows.md) | N_rows specifies the number of rows in the structured grid used for the groundwater model | integer | n/a | — | — |
| [n_cols](n_cols.md) | N_cols specifies the number of columns in the structured grid used for the groundwater model | integer | n/a | — | — |
| [bc_type](bc_type.md) | Bc_type sets the boundary condition type applied to the groundwater model cells | integer | n/a | — | — |
| [conn_type](conn_type.md) | Conn_type determines the type of connection between the groundwater and the overlying soil | integer | n/a | — | — |
| [gw_soil](gw_soil.md) | A flag indicating whether soil-related groundwater processes are simulated | integer | n/a | — | — |
| [satx](satx.md) | A flag indicating whether root zone soil water saturation excess is calculated for groundwater recharge | integer | n/a | — | — |
| [pumpex](pumpex.md) | A flag indicating whether groundwater pumping is simulated | integer | n/a | — | — |
| [tile](tile.md) | A flag indicating whether tile drainage interactions with groundwater are simulated | integer | n/a | — | — |
| [res](res.md) | A flag indicating whether reservoir-groundwater interactions are simulated | integer | n/a | — | — |
| [wet](wet.md) | A flag indicating whether wetland-groundwater interactions are simulated | integer | n/a | — | — |
| [fp](fp.md) | A flag indicating whether floodplain-groundwater interactions are simulated | integer | n/a | — | — |
| [canal](canal.md) | A flag indicating whether canal-groundwater interactions are simulated | integer | n/a | — | — |
| [solute](solute.md) | A flag indicating whether solute transport in the groundwater is simulated | integer | n/a | — | — |
| [heat](heat.md) | A flag indicating whether heat transport in the groundwater is simulated | integer | n/a | — | — |
| [time_step](time_step.md) | Time_step specifies the time step length in days for the groundwater flow solution | real | — | — | — |
| [write_day](write_day.md) | A flag controlling whether daily mass balance output files are written | integer | n/a | — | — |
| [write_mon](write_mon.md) | A flag controlling whether monthly mass balance output files are written | integer | n/a | — | — |
| [write_yr](write_yr.md) | A flag controlling whether yearly mass balance output files are written | integer | n/a | — | — |
| [write_aa](write_aa.md) | A flag controlling whether average annual mass balance output files are written | integer | n/a | — | — |
| [river_thresh](river_thresh.md) | River_thresh defines the bed elevation change threshold used in river-groundwater exchanges | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
