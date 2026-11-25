---
description: "Change in soil-water storage"
---

# sw_change

**Code reference:** `bwb_d%delsw` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L41)).

Full HRUs subtract the soil-water sum measured at the start of the current simulation day from the ending sum. The printed starting endpoint can refer to an earlier day under an intermittent daily print schedule. HRU-LTE reports zero. [Calculation and reporting details](README.md#evapotranspiration-and-soil-water)

**Unit:** mm.

[Back to the output table](README.md).
