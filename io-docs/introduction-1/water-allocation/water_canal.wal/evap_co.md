---
description: "Water fraction retained after evaporation adjustment"
---

# evap_co

**Code reference:** `canal(ic)%evap_co` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_module.f90#L203)).

The model multiplies canal water storage by this value during the evaporation adjustment. A value of 1 retains all the water at this step; 0.9 retains 90%.
