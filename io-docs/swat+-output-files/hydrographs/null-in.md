---
description: "Numeric water-temperature component printed as null"
---

# null

**Code reference:** `ob(icmd)%hin_d(iin)%temp` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L20); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49)).

Numeric water-temperature component printed as null.

**Unit:** deg C.

Daily volume and constituent mass values are added into monthly and yearly totals; the average-annual record divides accumulated volume and masses by `time%yrs_prt`. The [hydrograph operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1337) combine temperature by water-volume weighting, and division by years leaves temperature unchanged. The writers perform no volume-to-rate conversion. This is a real value occupying the final hydrograph component, not a separator or an absent field. Meaningful temperatures depend on the upstream simulation. Important: the [yearly CSV write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydin_output.f90#L55) inserts an extra receiving-object number after `type`, giving 29 values under 28 headings. Use the matching TXT or repair the CSV layout before interpreting later columns.

[Back to the output table](README.md).
