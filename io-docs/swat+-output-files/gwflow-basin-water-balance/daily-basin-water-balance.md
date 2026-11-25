# Daily GWFlow Basin Water Balance

`gwflow_basin_wb_day.txt` contains a title, column headings, units, and one 31-column basin-wide row per reported day. See the [GWFlow Basin Water Balance index](README.md#how-to-produce-these-files) for activation and print settings.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Basin identifier, printed as 1 | n/a |
| [gis_id](gis_id.md) | Basin placeholder, printed as 1 | n/a |
| [name](name.md) | Basin name | n/a |
| [ts](ts.md) | Groundwater flow-solution time step | days |
| [vbef](vbef.md) | Groundwater storage at the before-solution checkpoint | mm |
| [vaft](vaft.md) | Groundwater storage after the daily balance | mm |
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
| [error](error.md) | Balance residual relative to ending storage | % |
| [sat_frac](sat_frac.md) | Saturation-excess connection-event count divided by the number of active and boundary cells | fraction |
| [wt_depth](wt_depth.md) | Average depth from ground surface to the water table | m |
| [pump_def](pump_def.md) | Unmet groundwater pumping demand | mm |

The model's units row leaves `ts` unspecified; the groundwater time-step setting is in days.

## Signs, normalization, and daily diagnostic limits

Positive exchange values add groundwater and negative values remove it. In particular, `gw_sw`, `gw_et`, `sat_excess`, `soil`, pumping, tile drainage, wetland discharge, and phreatophyte uptake are removal terms in their inspected producers. `sw_gw`, recharge, and pond seepage add groundwater. Reservoir, canal, floodplain, boundary, and lateral exchanges retain their signed directions. `pump_def` is unmet demand, not an additional withdrawal. The wetland component records groundwater entering wetlands, not a two-way net wetland exchange; seepage into groundwater can follow other source components.

Daily storage and exchange volumes are summed only for `gw_state%stat == 1`, divided by the full `bsn%area_tot_ha * 10000` basin area, and multiplied by 1000 to obtain mm. The denominator is not the sum of active-cell areas.

The daily error is exactly `100 * (1 - (vbef + sum_of_signed_fluxes) / vaft)`, calculated before conversion to mm. Its denominator is ending storage. The flux sum excludes unmet pumping demand. There is no zero-denominator guard at this formula; the percentage is undefined at zero ending storage ([error calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L863)).

Several source details limit stronger interpretations:

- `vbef` is computed at the start of the lateral-solution section, after some exchange routines can already have changed heads. The before/after values follow those checkpoints rather than establishing untouched start-of-day storage ([checkpoint](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L305)).
- Daily per-cell allocation-pumping and deficit diagnostics are assigned rather than accumulated. Repeated requests for one cell replace earlier values ([pumping assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_allo.f90#L94)).
- Saturation-excess and tile diagnostics also use per-cell assignment rather than accumulation; repeated qualifying calls replace earlier values ([saturation excess](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L55); [tile](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_tile.f90#L59)).
- `sat_frac` divides the count of qualifying active channel-cell connection events by the number of cells with status greater than zero, which includes boundary cells. A cell can count more than once, and the ratio can exceed 1 if events outnumber cells in the denominator. [Event counter](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_satexcess.f90#L38), [Denominator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L531)

Channel exchange changes cell head and storage directly. For exchange recorded before the `vbef` checkpoint, the checkpoint already reflects the head change. The solver excludes `gw_sw` and `sw_gw` from its source/sink sum, while the printed error formula includes both. This can make the error nonzero even when the remaining terms close between the two storage checkpoints. [Head and storage update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L101), [Solver source/sink sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L214), [Printed error formula](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L863)

The [soil](soil.md), [reservoir](reservoir.md), [wetland](wetland.md), [canal](canal.md), [floodplain](floodplain.md), and [pond](pond.md) pages trace each exchange to its source. In particular, `canal` combines exchanges from three routines, and `pond` measures bed seepage from stored pond water after rainfall and evaporation.

These are static source findings. Numerical effects and comparisons with cell/group reports have not been validated by a model run.

[Back to the GWFlow Basin Water Balance index](README.md).
