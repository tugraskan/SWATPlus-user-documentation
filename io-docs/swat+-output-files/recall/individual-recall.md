# Individual Recall Objects

`recall_day`, `recall_mon`, `recall_yr`, and `recall_aa` each have TXT and optional CSV variants. Their intended schema has 24 columns: six identifiers followed by the 18-value `hyd_output` payload. [Openers and headers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L182) [Writers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L17)

| Field | Description | Unit |
| --- | --- | --- |
| [jday](jday.md) | Julian day | n/a |
| [mon](mon.md) | Month | n/a |
| [day](day.md) | Day of month | n/a |
| [yr](yr.md) | Year | n/a |
| [name](name.md) | Recall-object name | n/a |
| [type](type.md) | Recall-object type | n/a |
| [flo](flo.md) | Recall water volume | m3 |
| [sed](sed.md) | Sediment | tons |
| [orgn](orgn.md) | Organic nitrogen | kg N |
| [sedp](sedp.md) | Sediment phosphorus | kg P |
| [no3](no3.md) | Nitrate nitrogen | kg N |
| [solp](solp.md) | Soluble phosphorus | kg P |
| [chla](chla.md) | Chlorophyll-a | kg |
| [nh3](nh3.md) | Ammonia nitrogen | kg N |
| [no2](no2.md) | Nitrite nitrogen | kg N |
| [cbod](cbod.md) | Carbonaceous biochemical oxygen demand | kg |
| [dox](dox.md) | Dissolved oxygen | kg |
| [san](san.md) | Sand | tons |
| [sil](sil.md) | Silt | tons |
| [cla](cla.md) | Clay | tons |
| [sag](sag.md) | Small aggregates | tons |
| [lag](lag.md) | Large aggregates | tons |
| [grv](grv.md) | Gravel | tons |
| [null](null.md) | Numeric water-temperature component printed as `null` | deg C |

Daily values are added to monthly and yearly `hyd_output` accumulators. Average annual divides accumulated volume and mass components by `time%yrs_prt`; the hydrograph division operator leaves the temperature component unchanged. The TXT unit row uses the 24-entry `hyd_hdr_units`, whose flow label is `m^3/s`, although `hyd_output%flo` is declared and written as volume with no division by 86,400. The table therefore uses m3.

{% hint style="warning" %}
All four individual Recall CSV openers write only the 18-entry `hyd_hdr_units3` units record after their 24-column heading record. There are no six blank identifier placeholders, so the CSV units row is not position-aligned: its first value (`m^3`) appears under `jday`, not `flo`. In addition, `recall_aa.csv` omits `time%yrc` from its data write and therefore has 23 values under 24 headings. The corresponding average-annual TXT record includes the year. These are source-level layout defects, not alternate schemas.
{% endhint %}

The yearly and average-annual sums omit a final partial month because the yearly accumulator receives the monthly sum only at calendar month end. [Period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L30-L58).

## How Recall inputs become daily output

For types 1–3, the reader copies the hydrograph values into the input array without converting flow rates or constituent concentrations. The routing command uses them as water volume and constituent masses. Check the time basis as well as the physical units when preparing a [Recall input](../../introduction-1/point-sources-and-inlets/recall.rec/README.md). [Input reader](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L163-L172), [hydrograph declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L31-L50).

| Recall input type | Record used by the daily writer |
| --- | --- |
| 1, daily | The current day-of-year entry. A negative daily volume can trigger the channel diversion calculation. |
| 2, monthly | The current month entry, copied in full each day of the month. |
| 3, yearly | The current year entry, copied in full each day of the year. The year check uses `>= start_yr OR <= end_yr`, which does not exclude dates outside an ordered input range. |

The period writer accumulates the daily copies. For example, a type-2 entry of 100 m³ becomes 3,100 m³ in a 31-day month with all days included. Input years after the first stored year advance the array by one slot at each year change. A gap in the input years can therefore misalign later data with the simulation-year index. [Input year indexing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L113-L145), [daily record selection](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L317-L352), [period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L17-L55).

Two other branches have source limitations. The subdaily reader (type 0) backs up after reading the date but has no payload read or index advance in that branch. Its indices start at zero, outside the allocated arrays, and the record does not advance. The type-4 reader can load an EXCO payload, but the main Recall routing command has no active type-4 assignment to the daily hydrograph. [Subdaily indices and allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L45-L47), [reader branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L98-L191), [routing cases](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L317-L352).

For a negative type-1 volume, the diversion routine can reduce channel storage of nitrate, soluble phosphorus, ammonia, nitrite, dissolved oxygen, and organic nitrogen. If channel water storage exceeds 10 m³, the calculated mass changes stay in the channel storage; they are not copied to the Recall report. At or below 10 m³, the routine zeros those six values in the Recall hydrograph before reporting. [Diversion routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_nut.f90#L19-L83), [report copy](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L326-L352).

[Back to the Recall index](README.md).
