---
description: "Plant carbon growth (period daily mean)"
---

# c_gro

**Code reference:** `hpw_d(j)%c_gro` accumulates `pl_mass_up%c` ([growth assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_biomass_gro.f90#L147)), after a daily reset ([reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_grow.f90#L24)).

Daily plant carbon growth. For longer periods the plant/weather averaging operator divides the accumulated growth by the number of reporting days; these values are period daily means rather than total growth over the whole month or year ([averaging](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L1354)).

**Unit:** kg C/ha.

[Back to the plant and weather schema](plant-weather-output.md).
