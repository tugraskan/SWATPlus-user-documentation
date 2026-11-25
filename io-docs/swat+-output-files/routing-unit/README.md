# Routing Unit

In [`print.prt`](../../introduction-1/simulation-settings/print.prt/README.md), set the desired period columns on the `ru` row to `y`. Set `csvout = y` to open the CSV versions. Daily rows follow the daily print window and interval. The writer runs for each routing unit after the `nyskip` warm-up years. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L558-L617), [daily write gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_output.f90#L18-L29), [warm-up gate](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L440).

| Period | TXT | CSV |
| --- | --- | --- |
| Daily | `ru_day.txt` | `ru_day.csv` |
| Monthly | `ru_mon.txt` | `ru_mon.csv` |
| Yearly | `ru_yr.txt` | `ru_yr.csv` |
| Average annual | `ru_aa.txt` | `ru_aa.csv` |

All eight files use 24 headings, a 24-entry units record with six blank identifier positions, and 24 data values. The first line identifies the simulation and program. TXT data writes are list-directed. [Shared headings and units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L902-L970), [row writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_output.f90#L21-L63).

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Julian Day | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of the month | n/a |
| [yr](yr.md) | Year | n/a |
| [name](name.md) | Name of the object | n/a |
| [type](type.md) | Type of the object | n/a |
| [flo](flo.md) | Water volume summed across the included hydrograph slots | m3 |
| [sed](sed.md) | Routing unit sediment | metric tons |
| [orgn](orgn.md) | Routing unit organic nitrogen | kg N |
| [sedp](sedp.md) | Routing unit sediment phosphorus | kg P |
| [no3](no3.md) | Routing unit nitrate nitrogen | kg N |
| [solp](solp.md) | Routing unit soluble phosphorus | kg P |
| [chla](chla.md) | Routing unit Chlorophyll-a | kg |
| [nh3](nh3.md) | Routing unit ammonia nitrogen | kg N |
| [no2](no2.md) | Routing unit nitrite nitrogen | kg N |
| [cbod](cbod.md) | Routing unit carbonaceous biochemical oxygen demand | kg |
| [dox](dox.md) | Routing unit dissolved oxygen | kg |
| [san](san.md) | Routing unit sand | tons |
| [sil](sil.md) | Routing unit silt | tons |
| [cla](cla.md) | Routing unit clay | tons |
| [sag](sag.md) | Routing unit small aggregates | tons |
| [lag](lag.md) | Routing unit large aggregates | tons |
| [grv](grv.md) | Routing unit gravel | tons |
| [null](null.md) | Numeric water-temperature component printed as null | deg C |

## How the values are formed

The yearly and average-annual values omit a final partial month, even if those days appear in the daily report. The writer transfers monthly records only at month end. [Period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_output.f90#L31-L63).

In SWAT+ main `6f515368`, the daily report sums every hydrograph slot that enters the routing-unit element loop. A full HRU has five slots. Slot 1 already contains the sum of surface runoff, lateral flow, and tile flow. The report also adds those three components individually and includes recharge from slot 2. With a common delivery ratio for the total and its components, the full-HRU runoff contribution is counted twice. The recharge slot bypasses the delivery ratio and still uses the element scaling factor. Each loaded field follows the same slot selection. [Routing-unit producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L110-L150), [slot definitions](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L462-L468), [full-HRU total](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_hyds.f90#L165-L169).

The export-coefficient branch (`exc`) computes a hydrograph but skips the accumulation into the report. A routing unit with only `exc` elements therefore leaves its daily record at zero. [Export-coefficient branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L98-L112).

The writer prints the accumulated volume in m3 under the unit label `m^3/s`. Monthly and yearly rows sum daily volumes and masses. The average-annual row divides the accumulated volume and masses by `time%yrs_prt`. `null` contains numeric temperature in degrees Celsius. The hydrograph addition operator weights temperature by the same volumes and returns zero when the combined volume is at or below `1.e-6` m3. Division by years leaves temperature unchanged. [Hydrograph record](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L31-L50), [addition operator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337-L1363), [period writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_output.f90#L18-L63).
