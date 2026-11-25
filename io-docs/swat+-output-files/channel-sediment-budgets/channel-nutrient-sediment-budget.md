# Channel Nutrient and Sediment Budget

The `sd_chanbud_*` and `basin_sd_chanbud_*` files share the 37-column table below. Individual rows carry the channel index, GIS ID, and object name. The basin writer adds every SWAT-DEG channel record, including transfers that can be counted at successive channels, and writes `1` for both identifier columns and the basin name. Monthly and yearly records are totals. Average annual divides the accumulated yearly record by the number of printed years. [Individual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_chanbud_output.f90#L13), [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_chanbud_output.f90#L10)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Day of year | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Calendar year | n/a |
| [unit](unit.md) | Object identifier | n/a |
| [gis_id](gis_id.md) | GIS identifier | n/a |
| [name](name.md) | Object name | n/a |
| [in_sed](in_sed.md) | Incoming sediment | tons |
| [out_sed](out_sed.md) | Outgoing sediment | tons |
| [fp_dep](fp_dep.md) | Floodplain sediment deposition | tons |
| [ch_dep](ch_dep.md) | Channel sediment deposition | tons |
| [bank_ero](bank_ero.md) | Bank erosion | tons |
| [bed_ero](bed_ero.md) | Bed erosion | tons |
| [in_no3](in_no3.md) | Incoming nitrate nitrogen | kg |
| [in_orgn](in_orgn.md) | Incoming organic nitrogen | kg |
| [out_no3](out_no3.md) | Outgoing nitrate nitrogen | kg |
| [out_orgn](out_orgn.md) | Outgoing organic nitrogen | kg |
| [fp_no3](fp_no3.md) | Floodplain deposition of nitrate nitrogen | kg |
| [bank_no3](bank_no3.md) | Bank erosion of nitrate nitrogen | kg |
| [bed_no3](bed_no3.md) | Bed erosion of nitrate nitrogen | kg |
| [fp_orgn](fp_orgn.md) | Floodplain deposition of organic nitrogen | kg |
| [ch_orgn](ch_orgn.md) | Channel deposition of organic nitrogen | kg |
| [bank_orgn](bank_orgn.md) | Bank erosion of organic nitrogen | kg |
| [bed_orgn](bed_orgn.md) | Calculated bed organic nitrogen before unit conversion | t × mg/kg |
| [in_solp](in_solp.md) | Incoming soluble phosphorus | kg |
| [in_orgp](in_orgp.md) | Incoming organic phosphorus | kg |
| [out_solp](out_solp.md) | Outgoing soluble phosphorus | kg |
| [out_orgp](out_orgp.md) | Outgoing organic phosphorus | kg |
| [fp_solp](fp_solp.md) | Floodplain deposition of soluble phosphorus | kg |
| [bank_solp](bank_solp.md) | Bank erosion of soluble phosphorus | kg |
| [bed_solp](bed_solp.md) | Calculated bed soluble phosphorus before unit conversion | t × mg/kg |
| [fp_orgp](fp_orgp.md) | Floodplain deposition of organic phosphorus | kg |
| [ch_orgp](ch_orgp.md) | Channel deposition of organic phosphorus | kg |
| [bank_orgp](bank_orgp.md) | Bank erosion of organic phosphorus | kg |
| [bed_orgp](bed_orgp.md) | Calculated bed sediment-associated phosphorus before unit conversion | t × mg/kg |
| [no3_orgn](no3_orgn.md) | Nitrogen transferred from nitrate to organic nitrogen | kg |
| [solp_orgp](solp_orgp.md) | Phosphorus transferred from soluble to organic phosphorus | kg |

{% hint style="warning" %}
At source revision `6f515368`, the printed units row labels nutrient budget columns as `tons`. Most nutrient values follow the kg convention. The three bed nutrient fields shown in t × mg/kg are written without the conversion to kg. Both individual and basin writers preserve those values when aggregating periods. [Budget assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L385-L408), [period operators](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L738-L810).
{% endhint %}

## How the nutrient values are formed

- **Inflow and outflow.** The controller takes the inflow snapshot after applicable water-allocation returns and groundwater exchanges, and before its sediment and nutrient calculations. It takes the outflow values from the release hydrograph after point-of-diversion processing. The near-zero-length channel bypass routes its incoming hydrograph downstream without running the budget producer. [Inflow snapshot](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L78-L167), [outflow snapshot](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L328-L399), [bypass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L375-L408).
- **Deposition.** Floodplain organic N and sediment-associated P deposition use the sediment trapping efficiency and the corresponding enrichment factor. The dissolved floodplain fields `fp_no3` and `fp_solp` are set to zero. In-channel `ch_orgn` and `ch_orgp` use a fraction of the eroded bank load multiplied by the enrichment factor. [Floodplain assignments](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L127-L138), [channel deposition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L267-L271).
- **Bank and bed erosion.** The bank routine divides sediment tons times nutrient concentration in mg/kg by 1,000 to obtain kg. It divides phosphorus into soluble and sediment-associated fractions using `p_bio`. The bed routine uses the same concentrations and split without the divisor, so its three nutrient values are numerically 1,000 times the kg equivalents. The budget records the calculated bed sediment and nutrient values, while the line that would add `bed_ero` to routed flow is commented out. `bank_no3` and `bed_no3` stay at zero. [Concentration declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L39-L41), [bank calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L238-L248), [bed calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L289-L298).
- **Transformations.** `no3_orgn` and `solp_orgp` record the separate transfer calculation that runs when flow is present and `qual2e = 1`. It uses travel time and the current organic or sediment-associated pool, caps the transfer at the available dissolved mass, and overwrites the four corresponding water-quality output values. Otherwise the transfer fields remain zero. [Transfer reset](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L67-L75), [quality and transfer calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L192-L220).

[Back to the Channel Sediment Budgets index](README.md).

The opener assigns unit `4814` to both `sd_chanbud_yr.csv` and `channel_sd_subday.csv` when their options are active. Check the [subdaily SD channel flow page](../channel/subdaily-sd-channel-flow.md) for the source limitation. [Subdaily opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L21), [Yearly budget opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L255)
