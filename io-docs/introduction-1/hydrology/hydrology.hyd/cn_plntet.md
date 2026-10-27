---
description: Lateral flow coefficient
---

# latq\_co

**Code reference:** `hyd_db(ithyd)%latq_co` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L25)).

Soil lateral flow is computed for each soil layer using a hillslope storage method. The equation is a function of excess water above field capacity, total soil water capacity, hydraulic conductivity, slope, and flow length. The lateral flow coefficient is a direct linear coefficient applied to the hillslope storage equation.
