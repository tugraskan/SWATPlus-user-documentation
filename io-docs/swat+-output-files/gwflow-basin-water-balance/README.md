# GWFlow Basin Water Balance

This output summarizes groundwater storage and water exchanges across the basin's active GWFlow cells. Water volumes are expressed as equivalent depths over the total basin area, making the exchanges comparable with other basin water-balance results.

The files are `gwflow_basin_wb_day.txt`, `gwflow_basin_wb_mon.txt`, `gwflow_basin_wb_yr.txt`, and `gwflow_basin_wb_aa.txt`. GWFlow must be active. The `gwflow_wb` entry in `print.prt`, when present, overrides the GWFlow output flags from `codes.gw`.

{% tabs %}
{% tab title="Daily" %}

The daily file contains a title, column headings, units, and one basin-wide row per reported day.

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
| [vbef](vbef.md) | Groundwater storage before the daily balance | mm |
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
| [wetland](wetland.md) | Groundwater exchange with wetlands | mm |
| [canal](canal.md) | Groundwater exchange with canals | mm |
| [floodplain](floodplain.md) | Groundwater exchange with floodplains | mm |
| [pond](pond.md) | Recharge-pond seepage to groundwater | mm |
| [phytorem](phytorem.md) | Groundwater uptake by phreatophytes | mm |
| [error](error.md) | Groundwater water-balance closure error | % |
| [sat_frac](sat_frac.md) | Fraction of active cells contributing saturation-excess flow | fraction |
| [wt_depth](wt_depth.md) | Average depth from ground surface to the water table | m |
| [pump_def](pump_def.md) | Unmet groundwater pumping demand | mm |

The model's units row leaves `ts` unspecified; the groundwater time-step setting is in days.

{% endtab %}
{% tab title="Monthly, yearly, and average annual" %}

These three files share a 26-column schema. They report the change in groundwater storage and aggregated exchanges instead of the daily before/after storage and diagnostic fields.

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
| [wetland](wetland.md) | Groundwater exchange with wetlands | mm |
| [canal](canal.md) | Groundwater exchange with canals | mm |
| [floodplain](floodplain.md) | Groundwater exchange with floodplains | mm |
| [pond](pond.md) | Recharge-pond seepage to groundwater | mm |
| [phytorem](phytorem.md) | Groundwater uptake by phreatophytes | mm |
| [pump_def](pump_def.md) | Unmet groundwater pumping demand | mm |

{% endtab %}
{% endtabs %}

Keep the reported signs when comparing gains, losses, and storage change. Positive and negative exchange values must not all be treated as positive additions.
