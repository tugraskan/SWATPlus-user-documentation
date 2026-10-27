---
description: Minimum temperature for plant growth
---

# tmp\_base

**Code reference:** `pldb(ic)%t_base`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L59)).

SWAT+ uses the base temperature to calculate the number of heat units accrued every day. The minimum or base temperature for plant growth varies with growth stage of the plant. However, this variation is ignored by the model - SWAT+ uses the same base temperature throughout the growing season.

Base temperature is measured by growing plants in growth chambers at several different temperatures. The rate of leaf tip appearance as a function of temperature is plotted. Extrapolating the line to the leaf tip appearance rate of 0.0 leaves/day gives the base or minimum temperature for plant growth. The figure below plots data for corn. Note that the line intersects the x-axis at 8°C.

![](<../../../.gitbook/assets/image (23).png>)
