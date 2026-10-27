---
description: Weir discharge linear coefficient
---

# linear\_c

**Code reference:** `res_weir(ires)%c`

**Declared type:** `reservoir_weir_outflow` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_weir.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L139)).

`linear_c` is the linear coefficient in the weir-release equation. SWAT+ calculates discharge as `(reservoir area in ha * 0.45) * linear_c * width * head^exp_k`, where `head` is the water depth above the weir crest; the source labels the result as m3/s.
