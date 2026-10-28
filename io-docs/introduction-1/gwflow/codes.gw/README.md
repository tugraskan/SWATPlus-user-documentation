---
description: "The codes.gw file is a GWFlow configuration file that defines key-value pairs for governing the behavior of the groundwater flow simulation within SWAT+. It contains three records: a metadata line, a row of key names, and a corresponding row of values. The reader matches each header key with its value; the table lists recognized keys rather than requiring a fixed key order. Unknown keys have no matching SELECT CASE branch."
---

# codes.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

The codes.gw file is a GWFlow configuration file that defines key-value pairs for governing the behavior of the groundwater flow simulation within SWAT+. It contains three records: a metadata line, a row of key names, and a corresponding row of values. The reader matches each header key with its value; the table lists recognized keys rather than requiring a fixed key order. Unknown keys have no matching SELECT CASE branch.

SWAT+ uses the literal filename `codes.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L225). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Three records: a metadata line, a row of key names, and the corresponding row of values. The reader matches each header key with its value; the table lists recognized keys rather than requiring a fixed key order. Unknown keys have no matching SELECT CASE branch. print.prt may override output flags separately.

### Configuration keys

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [grid_type](grid_type.md) | grid_type specifies the type of grid used in the groundwater model, either "structured" or "unstructured" (USG) | string | n/a | — | — |
| [ncell](ncell.md) | ncell indicates the total number of groundwater flow cells in the model domain | integer | n/a | — | — |
| [cell_size](cell_size.md) | cell_size defines the size of each grid cell in the groundwater model | real | — | — | — |
| [n_rows](n_rows.md) | n_rows specifies the number of rows in the structured grid used for the groundwater model | integer | n/a | — | — |
| [n_cols](n_cols.md) | n_cols specifies the number of columns in the structured grid used for the groundwater model | integer | n/a | — | — |
| [bc_type](bc_type.md) | bc_type sets the boundary condition type applied to the groundwater model cells | integer | n/a | — | — |
| [conn_type](conn_type.md) | conn_type determines the type of connection between the groundwater and the overlying soil, either HRU (1) or LSU (2) | integer | n/a | — | — |
| [gw_soil](gw_soil.md) | gw_soil is a flag indicating whether soil-related groundwater processes are simulated | integer | n/a | — | — |
| [satx](satx.md) | satx is a flag indicating whether root zone soil water saturation excess is calculated for groundwater recharge | integer | n/a | — | — |
| [pumpex](pumpex.md) | pumpex is a flag indicating whether groundwater pumping is simulated | integer | n/a | — | — |
| [tile](tile.md) | tile is a flag indicating whether tile drainage interactions with groundwater are simulated | integer | n/a | — | — |
| [res](res.md) | res is a flag indicating whether reservoir-groundwater interactions are simulated | integer | n/a | — | — |
| [wet](wet.md) | wet is a flag indicating whether wetland-groundwater interactions are simulated | integer | n/a | — | — |
| [fp](fp.md) | fp is a flag indicating whether floodplain-groundwater interactions are simulated | integer | n/a | — | — |
| [canal](canal.md) | canal is a flag indicating whether canal-groundwater interactions are simulated | integer | n/a | — | — |
| [solute](solute.md) | solute is a flag indicating whether solute transport in the groundwater is simulated | integer | n/a | — | — |
| [heat](heat.md) | heat is a flag indicating whether heat transport in the groundwater is simulated | integer | n/a | — | — |
| [time_step](time_step.md) | time_step specifies the time step length in days for the groundwater flow solution | real | — | — | — |
| [write_day](write_day.md) | write_day is a flag controlling whether daily mass balance output files are written | integer | n/a | — | — |
| [write_mon](write_mon.md) | write_mon is a flag controlling whether monthly mass balance output files are written | integer | n/a | — | — |
| [write_yr](write_yr.md) | write_yr is a flag controlling whether yearly mass balance output files are written | integer | n/a | — | — |
| [write_aa](write_aa.md) | write_aa is a flag controlling whether average annual mass balance output files are written | integer | n/a | — | — |
| [river_thresh](river_thresh.md) | river_thresh defines the bed elevation change threshold used in river-groundwater exchanges | real | — | — | — |
