---
description: "Harvest result in full HRUs. Zero in HRU-LTE."
---

# yield

**Code reference:** `hpw_d(j)%yield`, `hltpw_d(isd)%yield` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L198)).

The daily full-HRU value records the shared harvest result and then clears it. A later grain, biomass, or tuber harvest can overwrite an earlier result on the same day. HRU-LTE reports zero because its output uses a local default, while the season-end action stores the calculated yield in separate state. Monthly and yearly rows sum daily results. Average-annual rows divide that sum by the number of printed years. [Daily calculations](plant-weather-output.md#daily-plant-values)

**Unit:** kg/ha.

[Back to the plant and weather schema](plant-weather-output.md).
