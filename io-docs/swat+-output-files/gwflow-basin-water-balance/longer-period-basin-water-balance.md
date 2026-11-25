# Longer-Period GWFlow Basin Water Balance

`gwflow_basin_wb_mon.txt`, `gwflow_basin_wb_yr.txt`, and `gwflow_basin_wb_aa.txt` share a 26-column schema. They report the change in groundwater storage and aggregated exchanges instead of the daily before/after storage and diagnostic fields. See the [GWFlow Basin Water Balance index](README.md#how-to-produce-these-files) for activation and print settings.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year at the reporting boundary | n/a |
| [mon](mon.md) | Month at the reporting boundary | n/a |
| [day](day.md) | Day of month at the reporting boundary | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Basin identifier, printed as 1 | n/a |
| [gis_id](gis_id.md) | Basin placeholder, printed as 1 | n/a |
| [name](name.md) | Basin name | n/a |
| [dvol](dvol.md) | Change in groundwater storage during the reporting period | mm |
| [recharge](recharge.md) | Recharge entering groundwater | mm |
| [gw_et](gw_et.md) | Groundwater evapotranspiration | mm |
| [gw_sw](gw_sw.md) | Groundwater discharge to channels | mm |
| [sw_gw](sw_gw.md) | Channel seepage to groundwater | mm |
| [sat_excess](sat_excess.md) | Saturation-excess groundwater discharge | mm |
| [soil](soil.md) | Groundwater transferred to the soil profile | mm |
| [lateral](lateral.md) | Net lateral flow between groundwater cells | mm |
| [boundary](boundary.md) | Groundwater exchange across model boundaries | mm |
| [pump_allo](pump_allo.md) | Groundwater pumping for allocation demand | mm |
| [pump_ext](pump_ext.md) | Specified external groundwater pumping | mm |
| [tile](tile.md) | Groundwater discharge through tile drains | mm |
| [reservoir](reservoir.md) | Groundwater exchange with reservoirs | mm |
| [wetland](wetland.md) | Groundwater discharge to wetlands | mm |
| [canal](canal.md) | Groundwater exchange with canals | mm |
| [floodplain](floodplain.md) | Groundwater exchange with floodplains | mm |
| [pond](pond.md) | Recharge-pond seepage to groundwater | mm |
| [phytorem](phytorem.md) | Groundwater uptake by phreatophytes | mm |
| [pump_def](pump_def.md) | Unmet groundwater pumping demand | mm |

## Signs, periods, and limitations

Positive exchange values add groundwater and negative values remove it. `pump_def` is unmet demand, not an additional withdrawal. The wetland component records groundwater entering wetlands, not a two-way net wetland exchange.

The basin records sum normalized daily diagnostics. Daily values are divided by the full `bsn%area_tot_ha * 10000` basin area and multiplied by 1000 before accumulation; the denominator is not the sum of active-cell areas. Monthly and yearly accumulators reset at their reporting boundaries. Accumulation runs even when daily file output is disabled ([daily aggregation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L818); [monthly reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1462); [yearly reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1841)).

Average annual divides the simulation accumulators by `real(time%nbyr)`, the configured simulation-year count. It does not use `time%yrs_prt` or an independently counted number of printed years. That distinction matters when comparing it with other report families ([divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985); [basin division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2050)).

The daily routine adds all 19 numeric terms directly to the yearly and average-annual accumulators. Both include a final partial month. A monthly row requires calendar month end, so the available monthly rows omit those days when summed. [Daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L900-L959) · [Period dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L459-L474)

The longer-period totals inherit daily assignment limitations: repeated per-cell allocation-pumping, deficit, saturation-excess, and tile events can replace earlier daily values before the basin accumulators receive them. The storage change follows the source's before/after checkpoints rather than an untouched start-of-day state.

These are static source findings. Numerical effects and comparisons with cell/group reports have not been validated by a model run.

[Back to the GWFlow Basin Water Balance index](README.md).
