# GWFlow Basin Water Balance

This output summarizes groundwater storage and water exchanges across the basin's active GWFlow cells. Water volumes are expressed as equivalent depths over the total basin area, making the exchanges comparable with other basin water-balance results.

The files are `gwflow_basin_wb_day.txt`, `gwflow_basin_wb_mon.txt`, `gwflow_basin_wb_yr.txt`, and `gwflow_basin_wb_aa.txt`. GWFlow must be active. The `gwflow_wb` entry in `print.prt`, when present, overrides the GWFlow output flags from `codes.gw`.

{% tabs %}
{% tab title="Daily" %}

The daily file contains a title, column headings, units, and one basin-wide row per reported day.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](gwflow-basin-water-balance/jday.md) | Day of year | n/a |
| [mon](gwflow-basin-water-balance/mon.md) | Month | n/a |
| [day](gwflow-basin-water-balance/day.md) | Day of month | n/a |
| [yr](gwflow-basin-water-balance/yr.md) | Calendar year | n/a |
| [unit](gwflow-basin-water-balance/unit.md) | Basin identifier, printed as 1 | n/a |
| [gis_id](gwflow-basin-water-balance/gis_id.md) | Basin placeholder, printed as 1 | n/a |
| [name](gwflow-basin-water-balance/name.md) | Basin name | n/a |
| [ts](gwflow-basin-water-balance/ts.md) | Groundwater flow-solution time step | days |
| [vbef](gwflow-basin-water-balance/vbef.md) | Groundwater storage before the daily balance | mm |
| [vaft](gwflow-basin-water-balance/vaft.md) | Groundwater storage after the daily balance | mm |
| [recharge](gwflow-basin-water-balance/recharge.md) | Recharge entering groundwater | mm |
| [gw_et](gwflow-basin-water-balance/gw_et.md) | Groundwater evapotranspiration | mm |
| [gw_sw](gwflow-basin-water-balance/gw_sw.md) | Groundwater discharge to channels | mm |
| [sw_gw](gwflow-basin-water-balance/sw_gw.md) | Channel seepage to groundwater | mm |
| [sat_excess](gwflow-basin-water-balance/sat_excess.md) | Saturation-excess groundwater discharge | mm |
| [soil](gwflow-basin-water-balance/soil.md) | Groundwater transferred to the soil profile | mm |
| [lateral](gwflow-basin-water-balance/lateral.md) | Net lateral flow between groundwater cells | mm |
| [boundary](gwflow-basin-water-balance/boundary.md) | Groundwater exchange across model boundaries | mm |
| [pump_allo](gwflow-basin-water-balance/pump_allo.md) | Groundwater pumping for allocation demand | mm |
| [pump_ext](gwflow-basin-water-balance/pump_ext.md) | Specified external groundwater pumping | mm |
| [tile](gwflow-basin-water-balance/tile.md) | Groundwater discharge through tile drains | mm |
| [reservoir](gwflow-basin-water-balance/reservoir.md) | Groundwater exchange with reservoirs | mm |
| [wetland](gwflow-basin-water-balance/wetland.md) | Groundwater exchange with wetlands | mm |
| [canal](gwflow-basin-water-balance/canal.md) | Groundwater exchange with canals | mm |
| [floodplain](gwflow-basin-water-balance/floodplain.md) | Groundwater exchange with floodplains | mm |
| [pond](gwflow-basin-water-balance/pond.md) | Recharge-pond seepage to groundwater | mm |
| [phytorem](gwflow-basin-water-balance/phytorem.md) | Groundwater uptake by phreatophytes | mm |
| [error](gwflow-basin-water-balance/error.md) | Groundwater water-balance closure error | % |
| [sat_frac](gwflow-basin-water-balance/sat_frac.md) | Fraction of active cells contributing saturation-excess flow | fraction |
| [wt_depth](gwflow-basin-water-balance/wt_depth.md) | Average depth from ground surface to the water table | m |
| [pump_def](gwflow-basin-water-balance/pump_def.md) | Unmet groundwater pumping demand | mm |

The model's units row leaves `ts` unspecified; the groundwater time-step setting is in days.

{% endtab %}
{% tab title="Monthly, yearly, and average annual" %}

These three files share a 26-column schema. They report the change in groundwater storage and aggregated exchanges instead of the daily before/after storage and diagnostic fields.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](gwflow-basin-water-balance/jday.md) | Day of year at the reporting boundary | n/a |
| [mon](gwflow-basin-water-balance/mon.md) | Month at the reporting boundary | n/a |
| [day](gwflow-basin-water-balance/day.md) | Day of month at the reporting boundary | n/a |
| [yr](gwflow-basin-water-balance/yr.md) | Calendar year | n/a |
| [unit](gwflow-basin-water-balance/unit.md) | Basin identifier, printed as 1 | n/a |
| [gis_id](gwflow-basin-water-balance/gis_id.md) | Basin placeholder, printed as 1 | n/a |
| [name](gwflow-basin-water-balance/name.md) | Basin name | n/a |
| [dvol](gwflow-basin-water-balance/dvol.md) | Change in groundwater storage during the reporting period | mm |
| [recharge](gwflow-basin-water-balance/recharge.md) | Recharge entering groundwater | mm |
| [gw_et](gwflow-basin-water-balance/gw_et.md) | Groundwater evapotranspiration | mm |
| [gw_sw](gwflow-basin-water-balance/gw_sw.md) | Groundwater discharge to channels | mm |
| [sw_gw](gwflow-basin-water-balance/sw_gw.md) | Channel seepage to groundwater | mm |
| [sat_excess](gwflow-basin-water-balance/sat_excess.md) | Saturation-excess groundwater discharge | mm |
| [soil](gwflow-basin-water-balance/soil.md) | Groundwater transferred to the soil profile | mm |
| [lateral](gwflow-basin-water-balance/lateral.md) | Net lateral flow between groundwater cells | mm |
| [boundary](gwflow-basin-water-balance/boundary.md) | Groundwater exchange across model boundaries | mm |
| [pump_allo](gwflow-basin-water-balance/pump_allo.md) | Groundwater pumping for allocation demand | mm |
| [pump_ext](gwflow-basin-water-balance/pump_ext.md) | Specified external groundwater pumping | mm |
| [tile](gwflow-basin-water-balance/tile.md) | Groundwater discharge through tile drains | mm |
| [reservoir](gwflow-basin-water-balance/reservoir.md) | Groundwater exchange with reservoirs | mm |
| [wetland](gwflow-basin-water-balance/wetland.md) | Groundwater exchange with wetlands | mm |
| [canal](gwflow-basin-water-balance/canal.md) | Groundwater exchange with canals | mm |
| [floodplain](gwflow-basin-water-balance/floodplain.md) | Groundwater exchange with floodplains | mm |
| [pond](gwflow-basin-water-balance/pond.md) | Recharge-pond seepage to groundwater | mm |
| [phytorem](gwflow-basin-water-balance/phytorem.md) | Groundwater uptake by phreatophytes | mm |
| [pump_def](gwflow-basin-water-balance/pump_def.md) | Unmet groundwater pumping demand | mm |

{% endtab %}
{% endtabs %}

Keep the reported signs when comparing gains, losses, and storage change. Positive and negative exchange values must not all be treated as positive additions.
