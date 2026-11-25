# Basin SD Channel General Output

Use the `basin_sd_cha` row in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md) to select daily, monthly, yearly, or average-annual output. Set `csvout = y` for CSV copies. The files are `basin_sd_cha_day`, `basin_sd_cha_mon`, `basin_sd_cha_yr`, and `basin_sd_cha_aa`. The opener can write headers without SWAT-DEG channels. The reporting loop writes rows when at least one SWAT-DEG channel is present and the skipped years have elapsed. Daily rows also follow the daily print window and interval. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L306), [Skipped-year gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441), [Basin caller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L641)

All eight variants have 65 columns and end at the outflow block's numeric `null` temperature field. The [individual report](sd-channel-general.md) has a 66th column named `water_temp`. [Basin headers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L306), [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L30)

The basin writer sums the records for all SWAT-DEG channels, so water routed through successive channels can contribute multiple times. Storage is the combined state on the reporting date, including the final row. The three `null` fields carry numeric temperatures. The hydrograph operator weights temperature by the flow value in each record and preserves the resulting temperature when dividing a record. [Basin sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L13), [Hydrograph addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337), [Hydrograph division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1478)

The yearly and average-annual area and flux accumulators omit a final partial month. The storage block is still summed from the final-day channel states. [Month transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L44-L60), [yearly and average-annual writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L64-L97).

The basin totals inherit the [daily channel reporting limits](sd-channel-general.md#where-the-daily-water-values-come-from), including the near-zero-length bypass's last-contribution flow values and the zeroed seepage column when GWFlow is enabled.

The basin inlet and outlet masses sum the individual channel records. The [sediment and nutrient calculations](sd-channel-general.md#where-the-sediment-and-nutrient-values-come-from) therefore also apply to the basin totals, including the downstream masses retained after channel withdrawals.

| Fields | Monthly and yearly | Average annual |
| --- | --- | --- |
| `flo_in`, `flo_out` | Sums of daily rates across days and channels. The printed label remains m3/s. | Sum of yearly values divided by `time%yrs_prt`. |
| `area` | Sum of daily areas divided by calendar month length or `time%day_end_yr`. | Sum of daily areas divided by `time%yrs_prt`. |
| `precip`, `evap`, `seep`, incoming and outgoing masses | Period totals. | Sum of yearly values divided by `time%yrs_prt`. |

The monthly and yearly basin flow values have no division by the number of days. Use caution when comparing them with the individual reports, which apply that division. [Monthly basin calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L44), [Yearly and average-annual basin calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sdchannel_output.f90#L64)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-general.md) | Julian Day | n/a |
| [mon](mon-general.md) | Month | n/a |
| [day](day-general.md) | Day of the month | n/a |
| [yr](yr-general.md) | Year | n/a |
| [unit](unit-general.md) | Basin placeholder `1` | n/a |
| [gis_id](gis_id-general.md) | Basin placeholder `1` | n/a |
| [name](name-general.md) | Basin name | n/a |
| [area](area.md) | Combined channel area with period treatment described above | ha |
| [precip](precip.md) | Precipitation on the channel surface | m3 |
| [evap](evap-general.md) | Evaporation from the channel surface | m3 |
| [seep](seep.md) | Seepage out of the channel bottom | m3 |
| [flo_stor](flo_stor.md) | Combined water storage on the reporting date | m3 |
| [sed_stor](sed_stor-general.md) | Sediment storage in the channel | tons |
| [orgn_stor](orgn_stor.md) | Organic nitrogen storage in the channel | kg |
| [sedp_stor](sedp_stor.md) | Sediment phosphorus storage in the channel | kg |
| [no3_stor](no3_stor.md) | Nitrate nitrogen storage in the channel | kg |
| [solp_stor](solp_stor.md) | Soluble phosphorus storage in the channel | kg |
| [chla_stor](chla_stor.md) | Chlorophyll-a storage in the channel | kg |
| [nh3_stor](nh3_stor.md) | Ammonia nitrogen storage in the channel | kg |
| [no2_stor](no2_stor.md) | Nitrite nitrogen storage in the channel | kg |
| [cbod_stor](cbod_stor.md) | Carbonaceous Biochemical Oxygen Demand storage in the channel | kg |
| [dox_stor](dox_stor.md) | Dissolved oxygen storage in the channel | kg |
| [san_stor](san_stor.md) | Sand storage in the channel | tons |
| [sil_stor](sil_stor.md) | Silt storage in the channel | tons |
| [cla_stor](cla_stor.md) | Clay storage in the channel | tons |
| [sag_stor](sag_stor.md) | Small aggregate storage in the channel | tons |
| [lag_stor](lag_stor.md) | Large aggregate storage in the channel | tons |
| [grv_stor](grv_stor.md) | Gravel storage in the channel | tons |
| [null](null.md) | Numeric temperature slot | not printed |
| [flo_in](flo_in-general.md) | Sum of channel inflow rates with period treatment described above | m3/s |
| [sed_in](sed_in-general.md) | Sediment entering the channel  | tons |
| [orgn_in](orgn_in-general.md) | Organic nitrogen entering the channel | kg |
| [sedp_in](sedp_in.md) | Sediment phosphorus entering the channel | kg |
| [no3_in](no3_in-general.md) | Nitrate nitrogen entering the channel | kg |
| [solp_in](solp_in-general.md) | Soluble phosphorus entering the channel | kg |
| [chla_in](chla_in-general.md) | Chlorophyll-a entering the channel  | kg |
| [nh3_in](nh3_in.md) | Ammonia nitrogen entering the channel | kg |
| [no2_in](no2_in-general.md) | Nitrite nitrogen entering the channel | kg |
| [cbod_in](cbod_in-general.md) | Carbonaceous Biochemical Oxygen Demand entering the channel | kg |
| [dox_in](dox_in.md) | Dissolved oxygen entering the channel | kg |
| [san_in](san_in.md) | Sand entering the channel | tons |
| [sil_in](sil_in.md) | Silt entering the channel | tons |
| [cla_in](cla_in.md) | Clay entering the channel | tons |
| [sag_in](sag_in.md) | Small aggregates entering the channel | tons |
| [lag_in](lag_in-general.md) | Large aggregates entering the channel | tons |
| [grv_in](grv_in.md) | Gravel entering the channel | tons |
| [null](null.md) | Numeric temperature slot | not printed |
| [flo_out](flo_out-general.md) | Sum of channel outflow rates with period treatment described above | m3/s |
| [sed_out](sed_out-general.md) | Sediment leaving the channel | tons |
| [orgn_out](orgn_out-general.md) | Organic nitrogen leaving the channel | kg |
| [sedp_out](sedp_out.md) | Sediment phosphorus leaving the channel | kg |
| [no3_out](no3_out-general.md) | Nitrate nitrogen leaving the channel | kg |
| [solp_out](solp_out-general.md) | Soluble phosphorus leaving the channel | kg |
| [chla_out](chla_out-general.md) | Chlorophyll-a leaving the channel | kg |
| [nh3_out](nh3_out.md) | Ammonia nitrogen leaving the channel | kg |
| [no2_out](no2_out-general.md) | Nitrite nitrogen leaving the channel | kg |
| [cbod_out](cbod_out-general.md) | Carbonaceous Biochemical Oxygen Demand leaving the channel | kg |
| [dox_out](dox_out.md) | Dissolved oxygen leaving the channel | kg |
| [san_out](san_out.md) | Sand leaving the channel | tons |
| [sil_out](sil_out.md) | Silt leaving the channel | tons |
| [cla_out](cla_out.md) | Clay leaving the channel | tons |
| [sag_out](sag_out.md) | Small aggregates leaving the channel | tons |
| [lag_out](lag_out-general.md) | Large aggregates leaving the channel | tons |
| [grv_out](grv_out.md) | Gravel leaving the channel | tons |
| [null](null.md) | Numeric temperature slot | not printed |

[Back to the Channel index](README.md).
