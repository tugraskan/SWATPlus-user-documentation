# Hydrographs

Set the desired period columns on the `hyd` row of [`print.prt`](../../introduction-1/simulation-settings/print.prt/README.md) to `y`. Set `csvout = y` for matching CSV files. Daily rows follow the daily print window and interval, and both writers run after the `nyskip` warm-up years. [File openers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_hyd.f90#L17-L139), [routing and reporting calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L421-L442).

* hydin\_day.txt
* hydout\_day.txt
* hydin\_mon.txt
* hydout\_mon.txt
* hydin\_yr.txt
* hydout\_yr.txt
* hydin\_aa.txt
* hydout\_aa.txt

The same `hyd` period switches also open `deposition_{day,mon,yr,aa}` TXT files and optional CSV companions. Those 24-column object-level records are documented separately on [Hydrograph Deposition](deposition.md). They are not the per-connection `hydin_*` and `hydout_*` schemas below.

Each row represents a connection and its selected hydrograph type. A pair of objects can have more than one connection. In the incoming files, the row starts with the receiving object. In the outgoing files, it starts with the source object. [Incoming loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L14-L27), [outgoing loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L421-L429).

## What the connection rows measure

- **Outgoing.** The routing command takes the selected hydrograph from the processed source object and applies the outgoing connection fraction before writing or accumulating the row. The reported volume and masses already include that fraction. [Outgoing snapshot](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L421-L429).
- **Incoming.** For receivers other than full HRUs, HRU-LTEs, and routing units, the command applies the incoming connection fraction to the selected source hydrograph and saves it in the per-connection output record. Full HRUs, HRU-LTEs, and routing units use the separate runon and subsurface routing branch. That branch leaves the incoming report payload at zero even when water is routed to those objects. The writer still loops over their incoming connections. [Receiver branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L111-L216), [daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L14-L33).
- **Routing-unit expansion.** When setup expands a connection to a routing unit into connections to its members, each added incoming connection uses the outgoing fraction times the member's fraction. The added entry stores the source property's index in `typ_no`, while a direct entry normally stores the source object's number. [Connection setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L372-L399).

{% tabs %}
{% tab title="In" %}
| Field    | Description                                     | Unit |
| -------- | ----------------------------------------------- | ---- |
| [jday](jday-in.md) | Julian Day | n/a |
| [mon](mon-in.md) | Month | n/a |
| [day](day-in.md) | Day of the month | n/a |
| [yr](yr-in.md) | Year | n/a |
| [name](name-in.md) | Name of the receiving object | n/a |
| [type](type-in.md) | Type of the receiving object | n/a |
| [objtyp](objtyp-in.md) | Type of the source object | n/a |
| [typ_no](typ_no-in.md) | ID of the source object | n/a |
| [hyd_typ](hyd_typ-in.md) | Type of the incoming hydrograph | n/a |
| [fraction](fraction-in.md) | Fraction of the incoming hydrograph | fraction |
| [flo](flo-in.md) | Incoming water volume | m3 |
| [sed](sed-in.md) | Incoming sediment | tons |
| [orgn](orgn-in.md) | Incoming organic nitrogen | kg N |
| [sedp](sedp-in.md) | Incoming sediment phosphorus | kg P |
| [no3](no3-in.md) | Incoming nitrate nitrogen | kg N |
| [solp](solp-in.md) | Incoming soluble phosphorus | kg P |
| [chla](chla-in.md) | Incoming Chlorophyll-a | kg |
| [nh3](nh3-in.md) | Incoming ammonia nitrogen | kg N |
| [no2](no2-in.md) | Incoming nitrite nitrogen | kg N |
| [cbod](cbod-in.md) | Incoming carbonaceous biochemical oxygen demand | kg |
| [dox](dox-in.md) | Incoming dissolved oxygen | kg |
| [san](san-in.md) | Incoming sand | tons |
| [sil](sil-in.md) | Incoming silt | tons |
| [cla](cla-in.md) | Incoming clay | tons |
| [sag](sag-in.md) | Incoming small aggregates | tons |
| [lag](lag-in.md) | Incoming large aggregates | tons |
| [grv](grv-in.md) | Incoming gravel | tons |
| [null](null-in.md) | Numeric water-temperature component printed as null | deg C |
{% endtab %}

{% tab title="Out" %}
| Field    | Description                                     | Unit |
| -------- | ----------------------------------------------- | ---- |
| [jday](jday-out.md) | Julian Day | n/a |
| [mon](mon-out.md) | Month | n/a |
| [day](day-out.md) | Day of the month | n/a |
| [yr](yr-out.md) | Year | n/a |
| [name](name-out.md) | Name of the source object | n/a |
| [type](type-out.md) | Type of the source object | n/a |
| [objtyp](objtyp-out.md) | Type of the receiving object | n/a |
| [typ_no](typ_no-out.md) | ID of the receiving object | n/a |
| [hyd_typ](hyd_typ-out.md) | Type of the outgoing hydrograph | n/a |
| [fraction](fraction-out.md) | Fraction of the outgoing hydrograph | fraction |
| [flo](flo-out.md) | Outgoing water volume | m3 |
| [sed](sed-out.md) | Outgoing sediment | tons |
| [orgn](orgn-out.md) | Outgoing organic nitrogen | kg N |
| [sedp](sedp-out.md) | Outgoing sediment phosphorus | kg P |
| [no3](no3-out.md) | Outgoing nitrate nitrogen | kg N |
| [solp](solp-out.md) | Outgoing soluble phosphorus | kg P |
| [chla](chla-out.md) | Outgoing Chlorophyll-a | kg |
| [nh3](nh3-out.md) | Outgoing ammonia nitrogen | kg N |
| [no2](no2-out.md) | Outgoing nitrite nitrogen | kg N |
| [cbod](cbod-out.md) | Outgoing carbonaceous biochemical oxygen demand | kg |
| [dox](dox-out.md) | Outgoing dissolved oxygen | kg |
| [san](san-out.md) | Outgoing sand | tons |
| [sil](sil-out.md) | Outgoing silt | tons |
| [cla](cla-out.md) | Outgoing clay | tons |
| [sag](sag-out.md) | Outgoing small aggregates | tons |
| [lag](lag-out.md) | Outgoing large aggregates | tons |
| [grv](grv-out.md) | Outgoing gravel | tons |
| [null](null-out.md) | Numeric water-temperature component printed as null | deg C |
{% endtab %}
{% endtabs %}


At source revision `6f515368`, the [incoming](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L20) and [outgoing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydout_output.f90#L22) writers print the 28 fields in each table in order. The final `null` is a numeric temperature component in degrees C. The printed flow units say `m^3/s`, but `hyd_output%flo` is [declared as water volume](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), and these writers do not convert it to a rate. The table uses m3 for the source volume convention. Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion.

Both writers transfer monthly values to the yearly accumulator only at calendar month end. If the simulation ends before the last day of a month, the final partial month can appear in daily records while its values remain outside the yearly and average-annual totals. [Month and year flags](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/time_control.f90#L175-L191), [incoming accumulator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L32-L62), [outgoing accumulator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydout_output.f90#L36-L71).

{% hint style="warning" %}
The yearly incoming CSV file `hydin_yr.csv` contains an extra receiving-object number after `type`: 29 data values under 28 printed headings. The yearly TXT write does not include that extra value. This is a [source write-list mismatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L55), derived by static inspection; no model run was performed.
{% endhint %}
