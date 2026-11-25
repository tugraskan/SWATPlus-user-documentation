# GWFlow Cell Water Balance

The files `gwflow_cell_wb_day.txt`, `gwflow_cell_wb_mon.txt`, `gwflow_cell_wb_yr.txt`, and `gwflow_cell_wb_aa.txt` share this 25-column schema. Enable the desired periods on `gwflow_wb` or use the [`codes.gw` fallback flags](README.md#defaults-when-a-print-row-is-absent).

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
| [gw_sw](gw_sw.md) | Daily groundwater discharge; longer-period net channel exchange | m3/day |
| [sw_gw](sw_gw.md) | Daily seepage; longer-period cell accumulation missing | m3/day |
| [sat_excess](sat_excess.md) | Saturation-excess discharge | m3/day |
| [soil](soil.md) | Groundwater transferred to soil | m3/day |
| [lateral](lateral.md) | Net lateral flow; monthly cell accumulation missing | m3/day |
| [pump_allo](pump_allo.md) | Pumping for allocation demand | m3/day |
| [pump_ext](pump_ext.md) | Specified external pumping | m3/day |
| [tile](tile.md) | Tile-drain discharge | m3/day |
| [reservoir](reservoir.md) | Reservoir-groundwater exchange | m3/day |
| [wetland](wetland.md) | Groundwater discharge to wetlands | m3/day |
| [floodplain](floodplain.md) | Floodplain-groundwater exchange | m3/day |
| [canal](canal.md) | Canal-groundwater exchange | m3/day |
| [pond](pond.md) | Recharge-pond seepage | m3/day |
| [phytorem](phytorem.md) | Phreatophyte uptake | m3/day |

All four files include only active (`stat == 1`) cells. `unit` is the cell index, `gis_id` is `cell_gis_id(i)`, and `name` is `cell_name(i)`.

Daily flux fields are daily diagnostics. Monthly values divide their separate cell arrays by `time%day_mo`; yearly values divide by `time%day_end_yr`. Average annual sums the yearly daily means and divides by `real(time%nbyr)`, giving equal weight to yearly means. Head follows the same averaging structure; depth is elevation minus the corresponding head. Flux units remain m3/day, rather than basin-normalized mm or interval totals ([writers and monthly treatment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1223); [yearly/AA accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1593)).

The source has period-specific gaps: the monthly/yearly cell `gw_sw` arrays accumulate both signed channel-exchange directions, while no accumulating producer was identified for cell `sw_gw`. Monthly cell `lateral` likewise lacks the yearly producer's accumulation. These are separate arrays from the basin totals; a default zero is not evidence of zero physical exchange ([channel accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L89); [lateral accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L138)). Daily pumping, saturation-excess, and tile diagnostics can also be replaced by repeated calls while their period arrays accumulate events. Wetland flow is groundwater discharge to wetlands, not a two-way net exchange.

## Configuration and the reported cell values

- With `conn_type = 1`, the reader tries `hrucell.gw` first and falls back to `lsucell.gw`. With `conn_type = 2`, it tries the files in reverse order. Both paths that use LSU connections disable groundwater-to-soil and groundwater-to-wetland exchanges, even when their feature switches were on. If both files are absent with either recognized setting, the later connection reader reaches the `hrucell.gw` open and read. [Connection selection](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L327-L368), [Connection reads](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2051-L2059), [HRU fallback opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2124-L2130)
- The solver gives zero lateral water flow across faces to inactive neighbors and to status-2 boundary neighbors with boundary type 2. For the latter, a non-null per-cell boundary value in `cells.gw` replaces the default from `codes.gw`. The basin balance and cell water-balance rows use interior cells. [Default boundary type](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L321-L325), [Per-cell override](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L466-L477), [Flow branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L45-L70)
- The solver runs `int(1 / time_step)` flow steps per simulated day without a remainder step. For example, a setting of 0.4 days yields two flow steps covering 0.8 days. Each flow step calls the heat solver when enabled and invokes the solute solver when enabled. The solute solver splits a flow step into the configured transport substeps. [Flow-step count and loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L30-L48), [Heat and solute calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L163-L179), [Solute substep](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_solute.f90#L38-L46)

## Partial reporting periods

- **Start partway through the month or year.** The first monthly row divides by the full calendar month's length. The first yearly row divides by the last simulated day of that year counted from January 1. Both sums start on the first simulated day. For example, if head is 100 m every day from a July 16 start through July 31, the July row reports `100 × 16 / 31`, or about 51.61 m. The reported depth uses that same head. The day counts also affect the fluxes with period accumulators. [Simulation calendar](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L129-L164), [daily head accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L360-L372), [monthly divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1292-L1299), [yearly divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1560-L1567).
- **End before month-end.** The final partial month produces no monthly row. The last days still contribute to the yearly and average annual values through the separate yearly accumulators. If the final year began on January 1, its divisor counts the days actually simulated that year. [Calendar flags](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L175-L190), [report call order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L459-L474).
- **Skip warm-up output in `print.prt`.** The `nyskip` setting does not suppress these GWFlow cell reports. Enabled reports can include warm-up rows, and the average annual values include warm-up years. Each year's mean is accumulated even when the yearly file is disabled. [GWFlow dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L293-L298), [general output gate](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/command.f90#L439-L443), [yearly write and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1615-L1657).

[Back to the GWFlow Outputs index](README.md).
