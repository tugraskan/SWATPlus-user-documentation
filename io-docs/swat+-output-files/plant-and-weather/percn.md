---
description: "Nitrate nitrogen leached from bottom of soil profile"
---

# percn

**Code reference:** `bpw_d%percn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L208)).

Nitrate nitrogen leached below the deepest soil layer. The percolate concentration is applied to water leaving that layer, and the exported mass is capped at the nitrate available in the layer. [Daily calculations](plant-weather-output.md#daily-plant-values)

**Unit:** kg N/ha.

Monthly and yearly reports sum the daily leaching amounts. Average-annual reports divide the accumulated amount by `time%yrs_prt`. HRU-LTE reports zero. [Daily full-HRU value](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L857), [HRU-LTE value](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L416), [period operators](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1323-L1383).

[Back to the plant and weather schema](plant-weather-output.md).
