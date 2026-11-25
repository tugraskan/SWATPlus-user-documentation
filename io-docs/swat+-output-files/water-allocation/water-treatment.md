# Water-Treatment Diagnostics

The `wallo_treat_day`, `wallo_treat_mon`, `wallo_treat_yr`, and `wallo_treat_aa` TXT and CSV files report water-treatment diagnostics. See the [Water Allocation index](README.md#how-to-produce-these-files) for the shared `water_allo` print setting.

{% hint style="warning" %}
All variants print 24 headings. Daily TXT writes 24 values, but all CSV and monthly/yearly/AA TXT write only 23 because jday is omitted. Treatment writes identifier before name, opposite to the common header. Read the actual prefix and 18-value tail, not the printed headings alone.
{% endhint %}

| Report variant | Actual prefix before the 18-component hydrograph | Total values |
| --- | --- | ---: |
| Daily treatment TXT | jday, mon, day, yr, itrt, name | 24 |
| Monthly/yearly/AA treatment TXT | mon, day, yr, itrt, name | 23 |
| All treatment CSV | mon, day, yr, itrt, name | 23 |

The table preserves the common printed heading order. In treatment rows, identifier and name are reversed relative to that header. In 23-value rows, omitted `jday` shifts the remaining values another position: the numeric tail begins at position 6, the printed `flo` position contains sediment, and the final numeric temperature is at position 23 under `grv`, with no value corresponding to the terminal heading `null`.

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday-water-use-and-treatment.md) | Day of year; omitted in 23-value rows | n/a |
| [mon](mon-water-use-and-treatment.md) | Reporting month | n/a |
| [day](day-water-use-and-treatment.md) | Reporting day of month | n/a |
| [yr](yr-water-use-and-treatment.md) | Reporting calendar year | n/a |
| [name](name.md) | Treatment name; written after the index | n/a |
| [use](use.md) | Treatment-object index; written before the name | n/a |
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

The treatment loop reuses the same working hydrograph across PORs. Each pass scales its flow, converts its concentrations to masses, and caps flow and masses against the allocated stored water. A later POR starts from the preceding pass's result, so the order of PORs can change the reported removal values. [Treatment loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L60-L85), [Allocation return rows](allocation-transactions.md#what-the-por-rows-report)

The [treatment producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L79) resets `wal_tr_omd(iwtp)` on entry, then adds allocated stored inflow minus treated outflow across PORs. This reports change/removal, not the complete routed effluent. Repeated calls for one treatment object do not guarantee a sum across all calls because the producer resets the record per call.

The writer adds daily records to monthly arrays, monthly to yearly at month end, yearly to average annual at year end, and clears the daily/monthly/yearly records independently of their respective print flags. Average annual divides by `time%yrs_prt`. These operations sum volumes/masses; they do not make flow rates. The printed `flo` unit `m^3/s` conflicts with the m3 component and the absence of a rate conversion.

A final partial month stays in the monthly accumulator. The writer emits no monthly row for it and omits those days from the yearly and average-annual sums, even if daily files contain their values. [Period accumulation and writes](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L13-L67)

The literal `null` labels numeric `hyd_output%temp`, not a blank placeholder. Addition uses volume weighting when combined flow exceeds 1e-6 and zero otherwise; division leaves temperature unchanged. Thus temperature is not a summed mass or a validated temperature of removed material. See [the hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337).

## CSV file routing limitations

The [yearly treatment CSV opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_water_allocation.f90#L289) opens unit **3126**, while its headers/data target **3136**. This source unit mismatch prevents assuming that the intended `wallo_treat_yr.csv` filename receives the documented records. Actual runtime file routing and successful emission have not been validated.

[Back to the Water Allocation index](README.md).
