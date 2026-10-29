# GWFlow Outputs

GWFlow writes basin, cell, observation, pumping, heat, feature, and configured-group reports. These files are produced only when GWFlow and the corresponding output flag are active. GWFlow files are TXT reports; several configured-observation files have dynamic columns.

The basin water-balance schema is documented separately on [GWFlow Basin Water Balance](../gwflow-basin-water-balance/README.md).

## Cell water balance

The files are `gwflow_cell_wb_day.txt`, `gwflow_cell_wb_mon.txt`, `gwflow_cell_wb_yr.txt`, and `gwflow_cell_wb_aa.txt`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Object identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Object name | n/a |
| [head](head.md) | Groundwater head | m |
| [wt_depth](wt_depth.md) | Depth to the water table | m |
| [recharge](recharge.md) | Recharge entering the cell | m3/day |
| [gw_et](gw_et.md) | Groundwater evapotranspiration | m3/day |
| [gw_sw](gw_sw.md) | Groundwater discharge to surface water | m3/day |
| [sw_gw](sw_gw.md) | Surface-water seepage to groundwater | m3/day |
| [sat_excess](sat_excess.md) | Saturation-excess discharge | m3/day |
| [soil](soil.md) | Groundwater transferred to soil | m3/day |
| [lateral](lateral.md) | Net lateral groundwater flow | m3/day |
| [pump_allo](pump_allo.md) | Pumping for allocation demand | m3/day |
| [pump_ext](pump_ext.md) | Specified external pumping | m3/day |
| [tile](tile.md) | Tile-drain discharge | m3/day |
| [reservoir](reservoir.md) | Reservoir-groundwater exchange | m3/day |
| [wetland](wetland.md) | Wetland-groundwater exchange | m3/day |
| [floodplain](floodplain.md) | Floodplain-groundwater exchange | m3/day |
| [canal](canal.md) | Canal-groundwater exchange | m3/day |
| [pond](pond.md) | Recharge-pond seepage | m3/day |
| [phytorem](phytorem.md) | Phreatophyte uptake | m3/day |

Daily rows are daily rates. Monthly, yearly, and average-annual files explicitly report average daily rates for their interval, not interval totals.

## Observation wells

The files `gwflow_obs_day.txt`, `gwflow_obs_mon.txt`, `gwflow_obs_yr.txt`, and `gwflow_obs_aa.txt` use the headings `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, `head`, `wt_depth`, `temperature`, `no3`, and `p`. Units are m, m, degC, mg/L, and mg/L for the final five fields. A value of -99 means that quantity was not simulated.

## HRU pumping

The files `gwflow_hru_pump_day.txt`, `gwflow_hru_pump_mon.txt`, `gwflow_hru_pump_yr.txt`, and `gwflow_hru_pump_aa.txt` use `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, and `pump_allo`. Daily pumping is m3/day, monthly and yearly rows are totals in m3, and average annual is m3/yr.

`gwflow_cell_wb_ppag_obs_day.txt` is a configured observation matrix: the first column is time and each remaining column represents an HRU listed in `gwflow.hru_pump_observe`. Its width and column identity therefore depend on the project configuration.

## Basin heat balance

GWFlow opens `gwflow_basin_heat_day.txt`, `gwflow_basin_heat_yr.txt`, and `gwflow_basin_heat_aa.txt`; there is no monthly heat file in the inspected source.

The daily headings are `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, `ts`, `hbef`, `haft`, `recharge`, `gw_et`, `gw_sw`, `sw_gw`, `sat_excess`, `soil`, `lateral`, `dispersion`, `boundary`, `pump_allo`, `pump_ext`, `tile`, `reservoir`, `wetland`, `canal`, `floodplain`, `pond`, `error`, and `tavg`. Heat terms are MJ, `error` is percent, and `tavg` is degC.

Yearly and average-annual files replace `ts`, `hbef`, and `haft` with `hdel` and omit `error` and `tavg`. Their heat-flux headings are otherwise the same.

## Cell definition

`gwflow_cell_definition.txt` maps groundwater cells to space. Its printed headings are `cell_id`, `row`, `col`, `x_coord`, `y_coord`, `zone`, `status`, and `area`. For an unstructured grid, `row` and `col` are written as zero.

## Canal and recharge-pond reports

`gwflow_canal_wb_day.txt` uses `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, `diversion`, `storage`, `pond_xfer`, and `seepage`; the four water-balance values are m3.

`gwflow_canal_sol_day.txt` uses the same identifiers followed by `solute`, `div_mass`, `storage`, `pond_mass`, and `seep_mass`; mass fields are kg.

`gwflow_pond_wb_day.txt` uses the identifiers followed by `area`, `storage`, `rain`, `div_added`, `evap`, `recharge`, `div_spec`, and `div_unsat`. `area` is m2 and the other values are m3.

`gwflow_pond_sol_day.txt` uses the identifiers followed by `area`, `storage`, `solute`, `mass`, `div_added`, and `recharge`. The last three mass-transfer values are kg. `gwflow_pond_mass_day.txt` and `gwflow_pond_conc_day.txt` are dynamic matrices with one column per configured pond.

## Configured group and observation reports

The files `gwflow_gwsw_group_day.txt`, `gwflow_tile_group_day.txt`, `gwflow_chan_obs_flow_day.txt`, `gwflow_chan_obs_no3_day.txt`, and `gwflow_chan_hydsep_day.txt` depend on configured groups or observation cells. Their titles state the quantity and unit, but their data-column identity comes from the associated GWFlow input configuration. Do not assign a fixed public field list without that project configuration.
