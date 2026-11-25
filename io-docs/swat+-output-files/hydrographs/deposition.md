# Hydrograph Deposition

`deposition_day`, `deposition_mon`, `deposition_yr`, and `deposition_aa` each have TXT and optional CSV variants. The files use the same daily, monthly, yearly, and average-annual switches as `hyd` in [print.prt](../../introduction-1/simulation-settings/print.prt/README.md); `csvout = y` opens the CSV companions. All eight variants have the same 24 headings and 24 data values. [Openers and headers](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_hyd.f90#L141) [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyddep_output.f90#L18)

| Position | Heading | Value | Printed unit |
| ---: | --- | --- | --- |
| 1 | `jday` | Julian day | blank |
| 2 | `mon` | Month | blank |
| 3 | `day` | Day of month | blank |
| 4 | `yr` | Year | blank |
| 5 | `name` | Current object name | blank |
| 6 | `type` | Current object type (`hru` or `ru` at the active call sites) | blank |
| 7 | `flo` | `ht1%flo` | `m^3/s` |
| 8 | `sed` | `ht1%sed` | tons |
| 9 | `orgn` | `ht1%orgn` | kg N |
| 10 | `sedp` | `ht1%sedp` | kg P |
| 11 | `no3` | `ht1%no3` | kg N |
| 12 | `solp` | `ht1%solp` | kg P |
| 13 | `chla` | `ht1%chla` | kg |
| 14 | `nh3` | `ht1%nh3` | kg N |
| 15 | `no2` | `ht1%no2` | kg N |
| 16 | `cbod` | `ht1%cbod` | kg |
| 17 | `dox` | `ht1%dox` | kg |
| 18 | `san` | `ht1%san` | tons |
| 19 | `sil` | `ht1%sil` | tons |
| 20 | `cla` | `ht1%cla` | tons |
| 21 | `sag` | `ht1%sag` | tons |
| 22 | `lag` | `ht1%lag` | tons |
| 23 | `grv` | `ht1%grv` | tons |
| 24 | `null` | Numeric `ht1%temp` water-temperature component | deg C |

The header uses the complete 24-entry `hyd_hdr_units`, so both TXT and CSV unit rows include six blank identifier positions and align with their 24 headings. As elsewhere in this hydrograph family, `hyd_output%flo` is declared as water volume and the deposition writer performs no division by 86,400; the printed `m^3/s` label is therefore not by itself evidence that the value is a rate.

## Which objects write rows

There are two active call sites. `command` calls `hyddep_output` after `hru_control` for full HRUs and after `ru_control` for routing units, and only when the current object has `rcv_tot > 0`. The analogous HRU-LTE call is commented out. One daily row can therefore be written for each qualifying processed HRU or routing unit, not one row for each incoming or outgoing connection. [Call sites](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L275)

Daily writing also obeys the shared day-print interval. Regardless of whether a daily row is printed, the current `ht1` payload is added to `hdep_m`; monthly values feed `hdep_y`, yearly values feed `hdep_a`, and the average-annual record divides `hdep_a` by `time%yrs_prt`. The `hyd_output` operators preserve their existing temperature weighting/division behavior.

A final partial month stays in the monthly accumulator and is excluded from the yearly and average-annual values. [Period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyddep_output.f90#L28-L64).

{% hint style="warning" %}
The source filename says “deposition,” but the written `ht1` is a shared work variable left by the object controller; the writer does not independently calculate or validate deposition. For a full HRU, `hru_control` first zeros `ht1`. Its surface-runon path either lets `rls_routesurf` set only the deposited sediment component (the flow assignment there is commented out) or, for the wetland path, replaces `ht1` with the incoming surface-plus-tile hydrograph. For a routing unit, `ru_control` repeatedly overwrites `ht1` while looping over elements and hydrograph types, accumulates the routing-unit total separately in `ru_d`, and leaves `ht1` as the final scaled loop payload. `hyddep_output` writes that residual `ht1`, not `ru_d`. Interpret these files as the source's controller-residual diagnostic, not as a guaranteed complete deposition budget.
{% endhint %}

The separate [Hydrographs overview](README.md) documents the per-connection `hydin_*` and `hydout_*` schemas and retains the `hydin_yr.csv` extra-value warning.

[Back to the Hydrographs index](README.md).
