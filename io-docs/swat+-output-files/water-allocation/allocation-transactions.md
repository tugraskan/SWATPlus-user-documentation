# Allocation Transactions

On SWAT+ dev the allocation report is split into three file groups, each with daily, monthly, yearly and average-annual TXT files and optional CSV files. See the [Water Allocation index](README.md#how-to-produce-these-files) for the shared `water_allo` print setting.

| Group | Files | One row per |
| --- | --- | --- |
| [POU totals (MET)](#pou-totals) | `wallo_met_day`, `_mon`, `_yr`, `_aa` | place of use (POU) |
| [POU–POD](#pou-pod-rows) | `wallo_pou_pods_day`, `_mon`, `_yr`, `_aa` | point of diversion (POD) of each POU |
| [POU–POR](#pou-por-rows) | `wallo_pou_pors_day`, `_mon`, `_yr`, `_aa` | receiving point (POR) of each POU |

The [header routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_water_allocation.f90#L10-L194) opens these files and writes a title line, a heading line and a units line to each. The [writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L27-L221) handles one POU at a time: its MET row, then one row per POD, then one row per POR.

{% hint style="warning" %}
POD and POR rows carry only a POD or POR index local to the POU (`1`, `2`, …), not the POU number. Match them to their POU by order: for each POU in turn, the POD file receives `pods` rows and the POR file `pors` rows, where `pods` and `pors` are the counts in [place_of_use.wro](../../introduction-1/water-allocation/place_of_use.wro/README.md).
{% endhint %}

{% hint style="warning" %}
**CSV exceptions.** Every MET CSV row has an extra `ipou` before the year (9 values under 8 headings). Daily POD and POR CSV rows omit the four date values. The average-annual POR CSV file is opened as `wallo_pou_pod_aa.csv` (singular `pod`), although `files_out.out` lists it as `wallo_pou_pors_aa.csv` ([opener](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_water_allocation.f90#L186-L191)).
{% endhint %}

## POU totals

Files `wallo_met_day`, `_mon`, `_yr` and `_aa` (`.txt`, `.csv`).

| Field | Description | Printed unit | Value unit |
| --- | --- | --- | --- |
| [jday](jday-allocation-transactions.md) | Day of year at the reporting boundary | — | — |
| [mon](mon-allocation-transactions.md) | Month | — | — |
| [day](day-allocation-transactions.md) | Day of month | — | — |
| [yr](yr-allocation-transactions.md) | Calendar year | — | — |
| [ipou](ipou.md) | POU number | — | — |
| [name](name-allocation-transactions.md) | POU name | — | — |
| [duty](duty.md) | Water the POU asked for in the period | ha-m | m³ |
| [deliv](deliv.md) | Water recorded as delivered to the POU in the period | ha-m | m³ |

| Variant | Values in write order | Count |
| --- | --- | ---: |
| TXT, all periods | jday, mon, day, yr, ipou, name, duty, deliv | 8 |
| CSV, all periods | jday, mon, day, **ipou**, yr, ipou, name, duty, deliv | 9 |

[Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L42), [header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L338-L361)

## POU-POD rows

Files `wallo_pou_pods_day`, `_mon`, `_yr` and `_aa` (`.txt`, `.csv`).

| Field | Description | Printed unit | Value unit |
| --- | --- | --- | --- |
| jday, mon, day, yr | Reporting date, as in the MET file | — | — |
| [ipod](ipod.md) | POD position within the POU's POD list | — | — |
| [duty](duty.md) | Share of the POU duty assigned to this POD | ha-m | m³ |
| [deliv](deliv.md) | Withdrawal recorded for this POD | ha-m | m³ |
| flo … temp | 18-value [hydrograph](#hydrograph-values) of the water and constituents withdrawn | see below | see below |

| Variant | Values in write order | Count |
| --- | --- | ---: |
| TXT, all periods; CSV monthly, yearly, average annual | jday, mon, day, yr, ipod, duty, deliv, 18 hydrograph values | 25 |
| CSV daily | ipod, duty, deliv, 18 hydrograph values | 21 |

[Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L31-L46), [header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L364-L421)

## POU-POR rows

Files `wallo_pou_pors_day`, `_mon`, `_yr` and `_aa` (`.txt`, `.csv`; see the CSV exception above for the average-annual CSV name).

| Field | Description | Printed unit | Value unit |
| --- | --- | --- | --- |
| jday, mon, day, yr | Reporting date, as in the MET file | — | — |
| [ipor](ipor.md) | POR position within the POU's POR list | — | — |
| flo … temp | 18-value [hydrograph](#hydrograph-values) sent to this POR | see below | see below |

| Variant | Values in write order | Count |
| --- | --- | ---: |
| TXT, all periods; CSV monthly, yearly, average annual | jday, mon, day, yr, ipor, 18 hydrograph values | 23 |
| CSV daily | ipor, 18 hydrograph values | 19 |

[Daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L35-L49), [header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L424-L477)

## Hydrograph values

The POD and POR rows end with the 18 components of a SWAT+ hydrograph, in this order ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L31-L49)):

| Heading | Component | Value unit |
| --- | --- | --- |
| flo | water volume | m³ |
| sed | sediment | tons |
| orgn | organic nitrogen | kg N |
| sedp | organic phosphorus | kg P |
| no3 | nitrate nitrogen | kg N |
| solp | soluble phosphorus | kg P |
| chla | chlorophyll-a | kg |
| nh3 | ammonium nitrogen | kg N |
| no2 | nitrite nitrogen | kg N |
| cbod | carbonaceous biological oxygen demand | kg |
| dox | dissolved oxygen | kg |
| san, sil, cla, sag, lag, grv | sand, silt, clay, small aggregates, large aggregates, gravel | tons |
| null | temperature | °C |

{% hint style="info" %}
**Printed units.** The units line labels `duty` and `deliv` as ha-m and `flo` as m³/s. The writer prints the stored values without conversion, and these are volumes in m³: duty is set from `rate_max × 86400` or a decision table in m³, withdrawals and irrigation demands are summed in m³, and the hydrograph `flo` component holds m³. The last heading is printed as `null` but holds temperature.
{% endhint %}

## Daily duty and reported delivery

At the start of each day the allocator clears the daily POU, POD and POR records ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L33-L48)). It then runs outside sources, water towers and unlimited sources, and only after that sets each POU's duty ([source calls](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L50-L123), [duty setup](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L128-L186)):

- The duty starts as `rate_max × 86400`. If a maximum-demand decision table is named, the duty becomes the table's `dmd_m3` result. Either way it is capped at `rate_max × 86400`.
- The `wallo_dmd` actions can set the result to a constant (`set_dmd`), add the POU demand currently in memory (`irr_dmd`), or fill a reservoir, water tower or canal to a target (`fill_res`, `fill_wtow`, `fill_can`) ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L189-L240)). When `irr_dmd` targets the POU being set up, it reads the `rate_max × 86400` value assigned just before.
- Each POD duty is the POU duty times the POD fraction from `place_of_use.wro`, or from the six-entry decision-table array `trn_fr` when a POD-fraction table is named. The routine does not clear `trn_fr` between tables, so a table that leaves an entry unset reuses an earlier value ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L839-L857)).

The duty setup also sets the POU and POD delivery values back to 0. It does not clear the POD hydrographs, so a POD row can contain water withdrawn by a source call that ran earlier on the same day, while its `deliv` value no longer includes it.

**Irrigation POUs.** For a POU of type `irr`, the duty and delivery printed in the MET file are replaced during delivery ([`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L36-L101)). For each HRU of the irrigation user, the routine evaluates the HRU's land-use decision table. Its `irr_wallo` action sets the HRU demand as depth × area (m³) ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L242-L260)). The routine then:

- adds every HRU demand to the POU `duty`, including HRUs that receive nothing;
- supplies an HRU only while the summed demand is still below `rate_max × 86400` and the HRU demand is below the water still available from this POU's POD withdrawals;
- adds each supplied HRU demand to `deliv` and reduces the available water and constituents proportionally;
- sets the HRU's applied irrigation, runoff and demand to 0 when the HRU is not supplied.

The POD rows of an irrigation POU keep their own duty (the POU's `rate_max`-based duty times the POD fraction) and their withdrawals. For irrigation POUs the POD values therefore need not add up to the MET values.

## Withdrawal limits and compensation

Before calling the withdrawal routine for a POU, the controller checks the POD's accumulated withdrawal against `wdraw_max × 86400` ([`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L19-L28)). The withdrawal routine starts from the POD duty and does not reduce the request to the remaining allowance ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L26-L37)). For PODs without a withdrawal decision table, the accumulated withdrawal resets at year end ([`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L378-L379)). A `duty_reset` action can replace the maximum and reset the counter ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L182-L187)).

On dev the controller looks up, for each POU served by the POD, the POU's global number and the POD's position in that POU's list ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L258-L268)). Ordinary withdrawals are therefore recorded on the matching POU and POD.

Compensation is tried for every POU in the model that is finished and whose delivery is below its duty ([`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L42-L57)). The compensation call always withdraws from the POD whose controller is running. It also reuses the POU position left over from the ordinary-withdrawal loop. As a result:

- a POU not served by this POD can receive water from it;
- the withdrawal is recorded on the POD position of the last POU in this POD's list, which may belong to a different POD of the compensated POU;
- a POU with several compensating PODs triggers one withdrawal per such POD, all from this same source.

The printed difference between duty and delivery is a difference between these two diagnostics. The files have no separate unmet-demand value.

## What each POD source contributes

The POD hydrograph adds the withdrawals from all calls for that POD on the day. The adjacent `deliv` value is set from the latest withdrawal and can differ from the hydrograph's accumulated `flo` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L131-L145)). The source branches fill the hydrograph as follows ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L43-L129)):

| Source | Water and constituents in the POD hydrograph |
| --- | --- |
| Unlimited (`unl`) | Water only. The POD fraction is applied once to set the POD duty and again to compute the withdrawal from it. |
| Outside source (`osrc`) | Copies the outside-source record `osrc_om(j)` indexed by the source object number, sets the volume to the POD fraction × its flow × 86,400 (the flow is treated as m³/s), and converts its concentrations to masses. The record used here is indexed differently from the concentration record prepared at the start of the day ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L55-L85)). |
| Water tower (`wtow`), canal (`can`), reservoir (`res`) | Withdraws a proportional share of the stored water and constituent masses and reduces storage. The minimum is checked before the withdrawal, and the withdrawal fraction is capped at one, so a withdrawal can take storage below the minimum. |
| Channel (`cha`) | Copies a proportional share of water and masses from the channel outflow; the channel loses only water. The minimum is compared directly to the daily volume. Channels are skipped for compensation. |
| Aquifer (`aqu`) | Only water, nitrate and soluble phosphorus are assigned. Storage is reduced first and the withdrawal is calculated from the reduced state, so the POD receives less than was removed. |
| GWFlow (`gwf`) | No withdrawal is assigned; the POD hydrograph stays at zero. |

## Configuration values used by the allocator

| Input | How the source uses it |
| --- | --- |
| POU `rate_max` | Rate in m³/s multiplied by 86,400 to set the daily maximum volume. It also caps the demand-table result and, for irrigation POUs, the summed HRU demand that can be supplied. |
| POD and POR `frac` | Dimensionless multiplier on a volume or hydrograph. |
| POD `const_min` | Channel: compared directly to daily outflow volume (m³). Aquifer: compared to water-table depth (m). Reservoir, canal, tower: fraction of principal volume or current storage. |
| POD `ann_max` | Initializes `wdraw_max`; the controller multiplies it by 86,400. |

The POR maximum table, constant and annual limit are read but not used by the return routine, and its conveyance call is commented out ([`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L16-L28)). In each POR record of `place_of_use.wro`, positions 2 and 5 are both read into `num`, so position 5 is the receiving object number actually used ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L102-L108)). POD records no longer have this problem on dev.

## What the POR rows report

For POUs other than treatment plants, each POR receives its fraction of the POU's accumulated withdrawal hydrograph. Water-use POUs first replace that hydrograph with calculated effluent, and treatment POUs write treated hydrographs to their PORs directly ([`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L16-L69)). The return routine adds the water to a receiving channel, reservoir, aquifer, plant or storage; its `hru` branch adds nothing. Irrigation reaches HRUs through the irrigation POU path described above, not through PORs.

Every controller call delivers to and returns from all POUs already marked finished ([`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L59-L68)). Several controller calls on one day can therefore apply a POR hydrograph to its receiver more than once, and can repeat an irrigation POU's HRU loop. The POR row records the hydrograph once.

## Temperature

Scaling a hydrograph keeps its temperature; adding hydrographs weights temperature by volume and gives zero when the total volume is at most 1e-6 m³. Treatment and use POUs take temperature from the selected treatment or effluent record. The average-annual writer divides volume and masses by the number of printed years and leaves temperature unchanged.

## Reporting periods

The writer runs after the skipped years for every POU ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L441-L455)). Monthly values add the daily values. The yearly values add the **running** monthly totals on every call, before the month-end check, so daily values are counted repeatedly: if a POU's daily duty is 10 m³ on the first three days of a month, the yearly duty grows by 10 + 20 + 30 = 60 m³ for 30 m³ of daily duty ([`wallo_pou_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L68-L81)).

At year end the yearly values are added to the average-annual totals before the yearly print flag is checked, but they are cleared only when yearly output is on. The per-POD reset there also clears the monthly delivery instead of the yearly one ([`wallo_pou_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L125-L180)). Turning yearly output off can therefore change multi-year average-annual values. The average-annual values are the accumulated totals divided by `time%yrs_prt` ([`wallo_pou_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L182-L195)).

{% hint style="info" %}
These reporting-period findings come from reading the dev source. The runtime test cited on the main-branch version of this page (Baltschieder) was run on SWAT+ main and has not been repeated on dev.
{% endhint %}

[Back to the Water Allocation index](README.md).
