---
description: "Daily plant biomass"
---

# bioms

**Code reference:** `bpw_d%bioms` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L197)).

The daily full-HRU value copies the plant-community biomass record before the controller clamps any negative biomass to zero. HRU-LTE reports its current dry matter, which the season-end action can reset to zero before output. Longer-period rows average the daily values. [Daily calculations](plant-weather-output.md#daily-plant-values)

**Unit:** kg/ha.

[Back to the plant and weather schema](plant-weather-output.md).
