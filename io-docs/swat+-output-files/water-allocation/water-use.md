# Water-Use Diagnostics

The `wallo_use_day`, `wallo_use_mon`, `wallo_use_yr`, and `wallo_use_aa` TXT and CSV files report water-use diagnostics. See the [Water Allocation index](README.md#how-to-produce-these-files) for the shared `water_allo` print setting.

{% hint style="warning" %}
All variants print 24 headings. Daily TXT writes 24 values, but all CSV and monthly/yearly/AA TXT write only 23 because jday is omitted. Read the actual prefix and 18-value tail, not the printed headings alone.
{% endhint %}

| Report variant | Actual prefix before the 18-component hydrograph | Total values |
| --- | --- | ---: |
| Daily use TXT | jday, mon, day, yr, name, iuse | 24 |
| Monthly/yearly/AA use TXT | mon, day, yr, name, iuse | 23 |
| All use CSV | mon, day, yr, name, iuse | 23 |

The table preserves the printed heading order. In 23-value rows, the tail begins at position 6 instead of 7: the printed `flo` position contains sediment, and the final numeric temperature is at position 23 under `grv`, with no value corresponding to the terminal heading `null`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-water-use-and-treatment.md) | Day of year; omitted in 23-value rows | n/a |
| [mon](mon-water-use-and-treatment.md) | Reporting month | n/a |
| [day](day-water-use-and-treatment.md) | Reporting day of month | n/a |
| [yr](yr-water-use-and-treatment.md) | Reporting calendar year | n/a |
| [name](name.md) | Water-use name | n/a |
| [use](use.md) | Water-use index | n/a |
| [flo](flo.md) | Water-volume change/removal | m3 |
| [sed](sed.md) | Sediment-mass change/removal | tons |
| [orgn](orgn.md) | Organic-nitrogen change/removal | kg N |
| [sedp](sedp.md) | Organic-phosphorus change/removal | kg P |
| [no3](no3.md) | Nitrate-nitrogen change/removal | kg N |
| [solp](solp.md) | Soluble-phosphorus change/removal | kg P |
| [chla](chla.md) | Chlorophyll-a change/removal | kg |
| [nh3](nh3.md) | Ammonia-nitrogen change/removal | kg N |
| [no2](no2.md) | Nitrite-nitrogen change/removal | kg N |
| [cbod](cbod.md) | Carbonaceous oxygen-demand change/removal | kg |
| [dox](dox.md) | Dissolved-oxygen change/removal | kg |
| [san](san.md) | Sand-mass change/removal | tons |
| [sil](sil.md) | Silt-mass change/removal | tons |
| [cla](cla.md) | Clay-mass change/removal | tons |
| [sag](sag.md) | Small-aggregate mass change/removal | tons |
| [lag](lag.md) | Large-aggregate mass change/removal | tons |
| [grv](grv.md) | Gravel-mass change/removal | tons |
| [null](null.md) | Numeric temperature component | deg C |

## Diagnostic meaning and periods

The [use producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use.f90#L68) assigns `wal_use_omd(iuse) = poud_om(ipou)%pors - wuse_om_stor(iuse)`: outflow minus stored inflow. Positive mass/volume means net addition and negative means net removal. This reports change/removal, not the complete routed effluent. Repeated calls for one use object do not guarantee a sum across all calls because the producer assigns its record.

The writer adds daily records to monthly arrays, monthly to yearly at month end, yearly to average annual at year end, and clears the daily/monthly/yearly records independently of their respective print flags. Average annual divides by `time%yrs_prt`. These operations sum volumes/masses; they do not make flow rates. The printed `flo` unit `m^3/s` conflicts with the m3 component and the absence of a rate conversion.

A final partial month stays in the monthly accumulator. The writer emits no monthly row for it and omits those days from the yearly and average-annual sums, even if daily files contain their values. [Period accumulation and writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L13-L68)

The literal `null` labels numeric `hyd_output%temp`, not a blank placeholder. Subtraction retains its left-hand temperature rather than taking a difference; division leaves temperature unchanged. Thus temperature is not a summed mass, a temperature difference, or a validated temperature of removed material. See [the hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337).

## CSV file routing limitations

The [use CSV openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_water_allocation.f90#L213) open monthly, yearly, and average-annual filenames on unit **3122**, which is also the daily CSV unit. Their headers/data instead target **3123, 3124, and 3125**. These source unit mismatches prevent assuming that the intended CSV filename receives the documented records. Actual runtime file routing and successful emission have not been validated.

[Back to the Water Allocation index](README.md).
