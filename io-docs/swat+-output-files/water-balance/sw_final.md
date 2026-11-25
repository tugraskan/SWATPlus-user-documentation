---
description: "Soil water at the end of the reporting period"
---

# sw_final

**Code reference:** `bwb_d%sw_final` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L20)).

Current soil water for the full-HRU and HRU-LTE daily rows. Full-HRU, landscape-unit, and basin period rows copy their latest daily endpoint. Longer-period HRU-LTE rows leave this field at zero. [Calculation and reporting details](README.md#period-calculations)

**Unit:** mm.

Storage timing is writer-dependent. The [HRU routine](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L40) adds the daily water-balance record to the monthly accumulator before updating daily soil-water and snowpack means. It advances initial daily stores inside the day-print gate. The [family warning](README.md) explains why the nominal heading alone does not guarantee boundary timing or equality with a mean of printed daily rows. These source-order concerns have not been runtime-tested.

[Back to the output table](README.md).
