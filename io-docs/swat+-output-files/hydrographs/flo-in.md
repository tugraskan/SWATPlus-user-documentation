---
description: "Incoming water volume"
---

# flo

**Code reference:** `ob(icmd)%hin_d(iin)%flo` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L20); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32)).

Incoming water volume after application of the connection fraction. Receivers of type HRU, HRU-LTE, or routing unit can receive flow while this report field stays at zero. [Connection behavior](README.md#what-the-connection-rows-measure).

**Unit:** m3.

Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion. The printed units row says `m^3/s`, whereas the source declares this component as volume and the writer makes no division by 86400; interpret the numeric value with the upstream hydrograph's volume convention. Important: the [yearly CSV write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L55) inserts an extra receiving-object number after `type`, giving 29 values under 28 headings. Use the matching TXT or repair the CSV layout before interpreting later columns.

[Back to the output table](README.md).
