---
description: Hydraulic conductivity of the wetland bottom
---

# k

**Code reference:** `wet_hyddb(ires)%k`

**Declared type:** `wetland_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L88)).

This value supplies the hydraulic conductivity used for wetland seepage. If k is zero or negative, SWAT+ replaces it during input processing with a first-layer soil hydraulic-conductivity value.
