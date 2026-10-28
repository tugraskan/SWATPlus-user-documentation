# GWFlow Basin Water Balance

This output summarizes groundwater storage and water exchanges across the basin's active GWFlow cells. Water volumes are expressed as equivalent depths over the total basin area, making the exchanges comparable with other basin water-balance results.

The files are `gwflow_basin_wb_day.txt`, `gwflow_basin_wb_mon.txt`, `gwflow_basin_wb_yr.txt`, and `gwflow_basin_wb_aa.txt`. GWFlow must be active. The `gwflow_wb` entry in `print.prt`, when present, overrides the GWFlow output flags from `codes.gw`.

{% tabs %}
{% tab title="Daily" %}

The daily file contains a title, column headings, units, and one basin-wide row per reported day.

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year | n/a |
| mon | Month | n/a |
| day | Day of month | n/a |
| yr | Calendar year | n/a |
| unit | Basin identifier, printed as 1 | n/a |
| gis_id | Basin placeholder, printed as 1 | n/a |
| name | Basin name | n/a |
| ts | Groundwater flow-solution time step | days |
| vbef | Groundwater storage before the daily balance | mm |
| vaft | Groundwater storage after the daily balance | mm |
| recharge | Recharge entering groundwater | mm |
| gw_et | Groundwater evapotranspiration | mm |
| gw_sw | Groundwater discharge to channels | mm |
| sw_gw | Channel seepage to groundwater | mm |
| sat_excess | Saturation-excess groundwater discharge | mm |
| soil | Groundwater transferred to the soil profile | mm |
| lateral | Net lateral flow between groundwater cells | mm |
| boundary | Groundwater exchange across model boundaries | mm |
| pump_allo | Groundwater pumping for allocation demand | mm |
| pump_ext | Specified external groundwater pumping | mm |
| tile | Groundwater discharge through tile drains | mm |
| reservoir | Groundwater exchange with reservoirs | mm |
| wetland | Groundwater exchange with wetlands | mm |
| canal | Groundwater exchange with canals | mm |
| floodplain | Groundwater exchange with floodplains | mm |
| pond | Recharge-pond seepage to groundwater | mm |
| phytorem | Groundwater uptake by phreatophytes | mm |
| error | Groundwater water-balance closure error | % |
| sat_frac | Fraction of active cells contributing saturation-excess flow | fraction |
| wt_depth | Average depth from ground surface to the water table | m |
| pump_def | Unmet groundwater pumping demand | mm |

The model's units row leaves `ts` unspecified; the groundwater time-step setting is in days.

{% endtab %}
{% tab title="Monthly, yearly, and average annual" %}

These three files share a 26-column schema. They report the change in groundwater storage and aggregated exchanges instead of the daily before/after storage and diagnostic fields.

| Field | Description | Unit |
| --- | --- | --- |
| jday | Day of year at the reporting boundary | n/a |
| mon | Month at the reporting boundary | n/a |
| day | Day of month at the reporting boundary | n/a |
| yr | Calendar year | n/a |
| unit | Basin identifier, printed as 1 | n/a |
| gis_id | Basin placeholder, printed as 1 | n/a |
| name | Basin name | n/a |
| dvol | Change in groundwater storage during the reporting period | mm |
| recharge | Recharge entering groundwater | mm |
| gw_et | Groundwater evapotranspiration | mm |
| gw_sw | Groundwater discharge to channels | mm |
| sw_gw | Channel seepage to groundwater | mm |
| sat_excess | Saturation-excess groundwater discharge | mm |
| soil | Groundwater transferred to the soil profile | mm |
| lateral | Net lateral flow between groundwater cells | mm |
| boundary | Groundwater exchange across model boundaries | mm |
| pump_allo | Groundwater pumping for allocation demand | mm |
| pump_ext | Specified external groundwater pumping | mm |
| tile | Groundwater discharge through tile drains | mm |
| reservoir | Groundwater exchange with reservoirs | mm |
| wetland | Groundwater exchange with wetlands | mm |
| canal | Groundwater exchange with canals | mm |
| floodplain | Groundwater exchange with floodplains | mm |
| pond | Recharge-pond seepage to groundwater | mm |
| phytorem | Groundwater uptake by phreatophytes | mm |
| pump_def | Unmet groundwater pumping demand | mm |

{% endtab %}
{% endtabs %}

Keep the reported signs when comparing gains, losses, and storage change. Positive and negative exchange values must not all be treated as positive additions.
