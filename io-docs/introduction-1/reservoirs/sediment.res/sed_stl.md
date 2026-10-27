---
description: Sediment settling rate input (read but not used by the model)
---

# sed\_stl

**Code reference:** `res_sed(ires)%sed_stlr`

**Declared type:** `reservoir_sed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_sed.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L104)).

SWAT+ main (6f515368) reads and stores `sed_stl`, but the value is not used in the reservoir or wetland sediment calculation. The model instead computes a settling coefficient from `d50` as `exp(-0.184 * d50)`.
