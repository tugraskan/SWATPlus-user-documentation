---
description: "Water percolating below the soil profile"
---

# perc

**Code reference:** `bwb_d%perc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L12)).

In full HRUs, the field reads water leaving the bottom soil layer, including crack flow when enabled. HRU-LTE reports water drained from its single soil-water store above the percolation threshold and adds it to shallow groundwater. [Calculation and reporting details](README.md#evapotranspiration-and-soil-water)

**Unit:** mm.

[Back to the output table](README.md).
