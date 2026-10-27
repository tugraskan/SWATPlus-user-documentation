---
description: Nitrogen settling rate during the mid-year nutrient settling period
---

# mid\_n\_stl

**Code reference:** `res_nut(ires)%nsetlr1` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L113)).

Enter this annual nutrient loss-rate coefficient in 1/year. SWAT+ divides it by 365 after reading it and uses the resulting daily coefficient in the temperature-adjusted reservoir and wetland nutrient-loss calculation.
