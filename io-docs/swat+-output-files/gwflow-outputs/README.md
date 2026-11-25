# GWFlow Outputs

GWFlow writes basin, cell, observation, pumping, heat, canal, pond, and selected-cell reports. The index shows which files have fixed columns and which depend on the model configuration.

## How to produce these files

Set `gwflow` to `1` in [codes.bsn](../../introduction-1/basin-1/codes.bsn/README.md) and supply the GWFlow inputs, including `chancell.gw`. To override report defaults in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), use named rows (`use_obj_lbls = y`). The period columns are daily, monthly, yearly, and average annual. GWFlow writes plain-text files. The diagnostic log, transit files, and selected-cell group files have no `.txt` suffix. [GWFlow activation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L45-L88), [Named rows](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L714-L761)

### Defaults when a print row is absent

| Print row | Behavior when omitted |
| --- | --- |
| `gwflow_wb` | Uses `write_day`, `write_mon`, `write_yr`, and `write_aa` from [codes.gw](../../introduction-1/gwflow/codes.gw/README.md). |
| `gwflow_heat` | Follows the effective daily, yearly, and average-annual water-balance flags. |
| `gwflow_solute` | Follows all four effective water-balance flags. |
| `gwflow_obs` | All four observation periods are on. |
| `gwflow_pump` | The common switch for all four HRU pumping files is on. |
| `gwflow_flux` | The common switch for daily canal, pond, tile, exchange-group, and channel-observation diagnostics is on. A named row enables it with `y` in the daily or yearly column. |

The input and feature requirements in the index still apply. [Default flags](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L9-L26), [Print overrides and inheritance](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L254-L311)

## File index

The [GWFlow Basin Water Balance](../gwflow-basin-water-balance/README.md) page lists `gwflow_basin_wb_{day,mon,yr,aa}.txt`.

| File family | Print setting | Schema |
| --- | --- | --- |
| `gwflow_cell_wb_{day,mon,yr,aa}.txt` | `gwflow_wb` periods | [Cell water balance](cell-water-balance.md) |
| `gwflow_obs_{day,mon,yr,aa}.txt` | `gwflow_obs` periods and `observation_cell` entries in `outputs.gw` for data rows | [Observation wells](observation-wells.md) |
| `gwflow_hru_pump_{day,mon,yr,aa}.txt` | any `gwflow_pump = y` enables all four | [HRU pumping, long format](hru-pumping.md) |
| `gwflow_cell_wb_ppag_obs_day.txt` | `gwflow_pump` plus `hru_pump.gw` selection | [Selected-HRU pumping matrix](selected-hru-pumping-matrix.md) |
| `gwflow_basin_heat_day.txt` | daily `gwflow_heat` and `heat = 1` in `codes.gw` | [Daily basin heat balance](daily-basin-heat-balance.md) |
| `gwflow_basin_heat_{yr,aa}.txt` | yearly/AA `gwflow_heat` and `heat = 1` | [Longer-period basin heat balance](longer-period-basin-heat-balance.md) |
| `gwflow_basin_sol_<solute>_{day,mon,yr,aa}.txt` | `gwflow_solute` periods and `solute = 1` in `codes.gw` | [Basin solute balance](basin-solute-balance.md) |
| `gwflow_cell_definition.txt` | written during initialization | [Cell definition](cell-definition.md) |
| `gwflow_record` | opened when `codes.bsn` requests GWFlow | [GWFlow diagnostic log](gwflow-record.md) |
| `gwflow_canal_wb_day.txt` | daily/yearly `gwflow_flux` switch plus canal configuration | [Canal water balance](canal-water-balance.md) |
| `gwflow_canal_sol_day.txt` | daily/yearly `gwflow_flux` and canal configuration open the file. Configured salts or conservative constituents supply rows | [Canal solute](canal-solute.md) |
| `gwflow_pond_wb_day.txt` | daily/yearly `gwflow_flux` plus recharge-pond configuration. See matrix prerequisite below | [Recharge-pond water balance](recharge-pond-water-balance.md) |
| `gwflow_pond_sol_day.txt` | daily/yearly `gwflow_flux` and pond configuration open the file. Configured GWFlow solutes supply rows | [Recharge-pond solute rows](recharge-pond-solute.md) |
| `gwflow_pond_{mass,conc}_day.txt` | daily/yearly `gwflow_flux` and pond configuration open both files. Initialize GWFlow solutes before using this switch with ponds | [Recharge-pond solute matrices](recharge-pond-solute-matrices.md) |
| `gwflow_gwsw_group_day.txt`, `gwflow_chan_obs_{flow,no3}_day.txt` | `gwflow_flux` plus `sw_group.gw` or flagged `chancell.gw` rows, with `solute = 1` for NO3 | [Configured exchange and observation matrices](configured-exchange-observation-matrices.md) |
| `gwflow_tile_group_day.txt` | tile drainage, tile groups in `tile.gw`, and the `gwflow_flux` switch | [Tile-group matrix](tile-group-matrix.md) |
| `gwflow_group_wb_day_*` | presence of configured `gwflow.wbgroups` | [Selected-cell water-balance groups](selected-cell-water-balance-groups.md) |
| `gwflow_chan_hydsep_day.txt` | daily `gwflow_wb` or `write_day` in `codes.gw` when the row is absent | [Channel separation](channel-separation.md) |
| `gwflow_transit_cell` | structured grid and `transit.gw` | [Groundwater transit tracks](transit-cell-tracks.md) |
| `gwflow_transit_chan`, `gwflow_transit_tile` | structured grid and `transit.gw`, with tile drainage enabled for the tile file | [Groundwater transit times to channels and tiles](transit-channel-tile-times.md) |

## Legacy output selectors

`outputs.gw` still accepts `head_output_time` and `detail_debug_cell`. Matching a head-output date advances an index with no grid dump, and the debug cell ID is stored with no writer using it. For head values, use the [cell water balance](cell-water-balance.md) or select individual cells with `observation_cell` for the [observation files](observation-wells.md). [Input reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L570-L622), [Date handling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L388-L393), [Cell file openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L498-L545)
