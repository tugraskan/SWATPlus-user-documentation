---
description: "Snowmelt depth"
---

# snomlt

**Code reference:** `bwb_d%snomlt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L8)).

Full HRUs use a seasonal melt factor, temperatures, and a snow-cover adjustment. HRU-LTE uses 4.57 times the nonnegative daily mean air temperature. Both cap the melt depth at available snow water. [Calculation and reporting details](README.md#snow-irrigation-and-drainage)

**Unit:** mm.

[Back to the output table](README.md).
