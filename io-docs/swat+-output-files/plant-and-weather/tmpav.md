---
description: "Mean air temperature. Daily calculation differs between HRU types."
---

# tmpav

**Code reference:** `bpw_d%tmpav` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L212)).

Full HRUs use the station mean computed before monthly temperature adjustments, then apply the HRU elevation lapse adjustment when enabled. HRU-LTE computes the mean from the station's adjusted maximum and minimum. Longer-period rows average the daily values. [Daily calculations](plant-weather-output.md#daily-weather-and-heat-units)

**Unit:** deg C.

[Back to the plant and weather schema](plant-weather-output.md).
