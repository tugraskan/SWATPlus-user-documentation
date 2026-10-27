---
description: Hydraulic conductivity of the reservoir bottom
---

# k

**Code reference:** `res_hyddb(ires)%k`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L74)).

If seepage occurs in the reservoir, the hydraulic conductivity must be set to a value other than 0.

This input controls reservoir-bottom seepage when the basin groundwater-flow option is off. When groundwater-flow mode is active, SWAT+ calculates reservoir seepage through the groundwater-flow routine instead.
