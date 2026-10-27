---
description: Volume surface area coefficient for HRU impoundment
---

# vol\_area\_co

**Code reference:** `wet_hyddb(ires)%acoef`

**Declared type:** `wetland_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L90)).

The parameters vol\_area\_co, vol\_dp\_a and vol\_dp\_b are coefficients that control how strongly the wetland area changes as storage volume changes relative to principal storage. They are used for wetland initialization and to update wetland area for each simulation time step.&#x20;

vol\_dp\_a and vol\_dp\_b are used to infer wetland depth from current storage volume. Subsequently, vol\_area\_co is used to convert the wetland depth to wetland area. The larger vol\_area\_co, the more the wetland area changes in response to changes in depth.

The final area is clipped between 0.01 and 1.0, so the effect of extreme values of vol\_area\_co, vol\_dp\_a, and vol\_dp\_b may get hidden by those limits.

The wetland area affects seepage, groundwater exchange, depth/release calculations, and constituent settling.
