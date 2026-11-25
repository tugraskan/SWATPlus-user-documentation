---
description: Minimum temperature for plant growth
---

# tmp\_base

**Code reference:** `pldb(ic)%t_base` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L54)).

**Current use:** heat units to maturity ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L251-L255)) and temperature stress ([`pl_tstr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_tstr.f90#L68-L77); see [tmp\_opt](untitled-6.md)).

SWAT+ uses the base temperature to calculate the number of heat units accrued every day. The minimum or base temperature for plant growth varies with growth stage of the plant. However, this variation is ignored by the model - SWAT+ uses the same base temperature throughout the growing season.

Base temperature is measured by growing plants in growth chambers at several different temperatures. The rate of leaf tip appearance as a function of temperature is plotted. Extrapolating the line to the leaf tip appearance rate of 0.0 leaves/day gives the base or minimum temperature for plant growth. The figure below plots data for corn. Note that the line intersects the x-axis at 8°C.

![](<../../../.gitbook/assets/image (23).png>)
