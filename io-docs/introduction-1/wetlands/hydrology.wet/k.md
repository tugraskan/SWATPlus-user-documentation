---
description: Hydraulic conductivity of the wetland bottom
---

# k

**Code reference:** `wet_hyddb(ires)%k` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L88)).

This value supplies the hydraulic conductivity used for wetland seepage. If k is zero or negative, SWAT+ replaces it during input processing with a first-layer soil hydraulic-conductivity value.
