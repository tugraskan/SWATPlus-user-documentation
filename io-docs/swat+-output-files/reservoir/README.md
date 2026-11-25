# Reservoir

In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), use `reservoir` for individual reports or `basin_res` for basin totals. Set the daily, monthly, yearly, or average-annual columns to `y` and set `csvout` to `y` for CSV copies. Data rows require reservoirs in the model and a year after `nyskip`. Daily rows also follow the daily print window and interval. The basin opener can create headers even when no reservoir rows will be written. [Print settings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L215), [Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L16), [Reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L598)

* reservoir\_day.txt
* reservoir\_mon.txt
* reservoir\_yr.txt
* reservoir\_aa.txt
* basin\_res\_day.txt
* basin\_res\_mon.txt
* basin\_res\_yr.txt
* basin\_res\_aa.txt

At source revision `6f515368`, all 16 TXT and CSV variants share 65 headings and write 65 data values. The first seven fields identify the date and report object. The next four give surface area and water volumes. The final three blocks contain 18 values each for storage, inflow, and outflow. Each `null` heading marks a numeric temperature field whose printed unit is blank. [Individual headers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_reservoir.f90#L14), [Basin headers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L120), [Hydrograph values](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L31)

The basin report sums reservoirs for area, water volumes, and constituent masses. It writes the basin name, a GIS ID placeholder of `1`, and the reservoir loop index after the loop finishes, which is the reservoir count plus one. The basin totals can include water and nutrients that pass through several reservoirs. An internal transfer can appear as outflow from the upstream reservoir and inflow to the downstream reservoir. [Basin aggregation and identifiers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L14-L43).

| Fields | Monthly and yearly rows | Average-annual row |
| --- | --- | --- |
| `area` | Monthly area divides the sum of daily areas by the calendar month length. Yearly area divides the sum of monthly means by 12. | Sum of yearly areas divided by the number of printed years. |
| `precip`, `evap`, `seep`, inflow and outflow volumes and masses | Totals over the reporting period. | Yearly totals summed and divided by the number of printed years. |
| Storage block | Current stored values on the reporting date. | Current stored values at the end of the simulation. |

The individual and basin writers omit a final partial month from the yearly and average-annual area and flux accumulators. The storage block still shows the final-day snapshot. [Individual accumulation and writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L29-L84), [basin accumulation and writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L49-L97).

The hydrograph addition operator weights temperatures by water volume. Dividing a hydrograph by the number of printed years leaves its temperature unchanged. [Individual reporting periods](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L29), [Basin reporting periods](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L30), [Water-body operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L73), [Temperature weighting](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337), [Hydrograph division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1478)

{% hint style="warning" %}
`reservoir_mon.csv` has an extra line containing `RES` and the filename immediately after the units row. The opener sends that line to the monthly CSV file instead of the output registry. [Monthly CSV opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_reservoir.f90#L35)
{% endhint %}

| Field      | Description                                                     | Unit |
| ---------- | --------------------------------------------------------------- | ---- |
| [jday](jday.md)       | Julian Day                                                      | n/a  |
| [mon](mon.md)        | Month                                                           | n/a  |
| [day](day.md)        | Day of the month                                                | n/a  |
| [yr](yr.md)         | Year                                                            | n/a  |
| [unit](unit.md) | Reservoir index or post-loop index for the basin report | n/a |
| [gis\_id](gis_id.md) | Reservoir GIS ID or basin placeholder `1` | n/a |
| [name](name.md)       | Name of the object or SWAT+ setup (basin outputs)               | n/a  |
| [area](area.md)       | Area of the reservoir                                           | ha   |
| [precip](precip.md)     | Precipitation on the reservoir surface                          | m3 |
| [evap](evap.md)       | Evaporation from the reservoir surface                          | m3 |
| [seep](seep.md)       | Seepage out of the reservoir bottom                             | m3 |
| [flo\_stor](flo_stor.md)  | Flow storage in the reservoir                                   | m3   |
| [sed\_stor](sed_stor.md)  | Sediment storage in the reservoir                               | tons |
| [orgn\_stor](orgn_stor.md) | Organic nitrogen storage in the reservoir                       | kg   |
| [sedp\_stor](sedp_stor.md) | Sediment phosphorus storage in the reservoir                    | kg   |
| [no3\_stor](no3_stor.md)  | Nitrate nitrogen storage in the reservoir                       | kg N |
| [solp\_stor](solp_stor.md) | Soluble phosphorus storage in the reservoir                     | kg P |
| [chla\_stor](chla_stor.md) | Chlorophyll-a storage in the reservoir                          | kg   |
| [nh3\_stor](nh3_stor.md)  | Ammonia nitrogen storage in the reservoir                       | kg   |
| [no2\_stor](no2_stor.md)  | Nitrite nitrogen storage in the reservoir                       | kg   |
| [cbod\_stor](cbod_stor.md) | Carbonaceous Biochemical Oxygen Demand storage in the reservoir | kg   |
| [dox\_stor](dox_stor.md)  | Dissolved oxygen storage in the reservoir                       | kg   |
| [san\_stor](san_stor.md)  | Sand storage in the reservoir                                   | tons |
| [sil\_stor](sil_stor.md)  | Silt storage in the reservoir                                   | tons |
| [cla\_stor](cla_stor.md)  | Clay storage in the reservoir                                   | tons |
| [sag\_stor](sag_stor.md)  | Small aggregate storage in the reservoir                        | tons |
| [lag\_stor](lag_stor.md)  | Large aggregate storage in the reservoir                        | tons |
| [grv\_stor](grv_stor.md)  | Gravel storage in the reservoir                                 | tons |
| [null](null.md) | Stored water temperature | deg C |
| [flo\_in](flo_in.md)    | Flow into the reservoir                                         | m3   |
| [sed\_in](sed_in.md)    | Sediment entering the reservoir                                 | tons |
| [orgn\_in](orgn_in.md)   | Organic nitrogen entering the reservoir                         | kg   |
| [sedp\_in](sedp_in.md)   | Sediment phosphorus entering the reservoir                      | kg   |
| [no3\_in](no3_in.md)    | Nitrate nitrogen entering the reservoir                         | kg N |
| [solp\_in](solp_in.md)   | Soluble phosphorus entering the reservoir                       | kg P |
| [chla\_in](chla_in.md)   | Chlorophyll-a entering the reservoir                            | kg   |
| [nh3\_in](nh3_in.md)    | Ammonia nitrogen entering the reservoir                         | kg   |
| [no2\_in](no2_in.md)    | Nitrite nitrogen entering the reservoir                         | kg   |
| [cbod\_in](cbod_in.md)   | Carbonaceous Biochemical Oxygen Demand entering the reservoir   | kg   |
| [dox\_in](dox_in.md)    | Dissolved oxygen entering the reservoir                         | kg   |
| [san\_in](san_in.md)    | Sand entering the reservoir                                     | tons |
| [sil\_in](sil_in.md)    | Silt entering the reservoir                                     | tons |
| [cla\_in](cla_in.md)    | Clay entering the reservoir                                     | tons |
| [sag\_in](sag_in.md)    | Small aggregates entering the reservoir                         | tons |
| [lag\_in](lag_in.md)    | Large aggregates entering the reservoir                         | tons |
| [grv\_in](grv_in.md)    | Gravel entering the reservoir                                   | tons |
| [null](null.md) | Inflow water temperature | deg C |
| [flo\_out](flo_out.md)   | Flow out of the reservoir                                       | m3   |
| [sed\_out](sed_out.md)   | Bulk sediment export calculated before the water-release cap | tons |
| [orgn\_out](orgn_out.md)  | Organic nitrogen leaving the reservoir                          | kg   |
| [sedp\_out](sedp_out.md)  | Sediment phosphorus leaving the reservoir                       | kg   |
| [no3\_out](no3_out.md)   | Nitrate nitrogen leaving the reservoir                          | kg N |
| [solp\_out](solp_out.md)  | Soluble phosphorus leaving the reservoir                        | kg P |
| [chla\_out](chla_out.md)  | Chlorophyll-a leaving the reservoir                             | kg   |
| [nh3\_out](nh3_out.md)   | Ammonia nitrogen leaving the reservoir                          | kg   |
| [no2\_out](no2_out.md)   | Nitrite nitrogen leaving the reservoir                          | kg   |
| [cbod\_out](cbod_out.md)  | Carbonaceous Biochemical Oxygen Demand slot, left at zero by the reservoir controller | kg   |
| [dox\_out](dox_out.md)   | Dissolved oxygen slot, left at zero by the reservoir controller | kg   |
| [san\_out](san_out.md)   | Sand outflow slot, left at zero by the reservoir controller | tons |
| [sil\_out](sil_out.md)   | Silt outflow slot, left at zero by the reservoir controller | tons |
| [cla\_out](cla_out.md)   | Clay outflow slot, left at zero by the reservoir controller | tons |
| [sag\_out](sag_out.md)   | Small aggregates outflow slot, left at zero by the reservoir controller | tons |
| [lag\_out](lag_out.md)   | Large aggregates outflow slot, left at zero by the reservoir controller | tons |
| [grv\_out](grv_out.md)   | Gravel outflow slot, left at zero by the reservoir controller | tons |
| [null](null.md) | Outflow temperature slot, left at zero by the reservoir controller | deg C |

## What the nutrient blocks include

- **Routed inflow.** The controller copies the incoming hydrograph into the daily inflow block for an active reservoir after warm-up. Before the construction month, the controller passes that hydrograph downstream without filling the daily inflow and outflow records. The report writer can still emit a row. [Activation and inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L38-L60), [report records and bypass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L253-L263), [report loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L598-L601).
- **Direct changes to storage.** With GWFlow solutes enabled, groundwater exchange can add or subtract nitrate and soluble phosphorus directly from reservoir storage. Those masses are absent from the routed inflow and outflow blocks. The `seep` column carries water volume. Allocation withdrawals can also remove water and nutrients from storage through a separate delivery hydrograph, leaving that withdrawal outside the release recorded in the outflow block. [Groundwater solutes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L101-L176), [seepage volume](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L210-L215), [allocation withdrawal](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_withdraw.f90#L99-L108).
- **Outflow and storage.** The controller adjusts water volume for release, evaporation, and seepage before calling the nutrient routine. That routine applies settling, then allocates the remaining masses between storage and release. If the remaining water volume is below `1.e-6` m³, it clears the stored record and returns before computing exported nutrients, even if water was released. The outflow CBOD and dissolved oxygen slots stay at their zero defaults on this path. [Water balance and nutrient call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L177-L214), [low-volume guard and export](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_nutrient.f90#L31-L116).

## Sediment and particle sizes

The incoming hydrograph supplies bulk sediment and each of the six size classes. Reservoirs already operating at the start of the simulation take their starting masses from the organic and mineral initialization record. Water allocation can also move sediment-bearing water into or out of storage through separate records. Those transfers are outside the reported reservoir release. [Initial hydrograph](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_initial.f90#L89-L103), [Mass conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1285-L1306), [Incoming hydrograph](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L38-L63), [Allocation withdrawal](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_withdraw.f90#L99-L108), [Allocation return](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L32-L43)

The decision-table branch calculates and smooths water release, then runs the sediment routine before adding precipitation or subtracting release, evaporation, and seepage from water storage. It uses that earlier storage volume to calculate bulk sediment concentration. Above the equilibrium concentration `nsed`, it applies a settling coefficient derived from `d50`, computes export using the smoothed release, deducts that export from the remaining bulk sediment mass with a floor of zero, and clears the six stored size classes. At or below `nsed`, that branch leaves bulk storage as it was and bulk export stays zero. The alternate release branch skips the sediment routine. [Sediment parameters](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L139-L147), [Release and settling order](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L121-L156), [Settling calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L17-L58)

If the water balance later caps the release, the reported bulk sediment load stays at the value computed with the earlier release. The settling routine clears the storage hydrograph and bulk sediment export when volume is below `1.e-6` m³ at the start of settling. A separate low-volume check after the water balance can clear storage while keeping the bulk sediment export already calculated. The release record leaves all six size-class fields at zero in both release branches. The basin report sums these individual masses and clears the individual inflow and outflow records after reading them. [Water balance and sediment export](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L177-L214), [Early low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L24), [Late low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L33-L38), [Basin sums and reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L14-L29)

## Oxygen and temperature values

CBOD and dissolved oxygen in storage come from initialization and hydrographs added to storage. Withdrawals and storage resets can reduce them. The normal release leaves the CBOD and dissolved oxygen fields at zero. The inflow temperature is inherited from the incoming hydrograph, and storage temperature mixes the initialized and incoming values by water volume. The reservoir routine changes water volume through precipitation, evaporation, and seepage without updating stored temperature for those exchanges. GWFlow can track heat exchange on the aquifer side without assigning a temperature to the reservoir hydrograph. The reported release temperature stays at zero. [Hydrograph addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337-L1363), [Release initialization and inflow](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L38-L63), [Water balance](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L168-L207), [GWFlow heat exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L91-L101), [Nutrient export assignments](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_nutrient.f90#L99-L115)
