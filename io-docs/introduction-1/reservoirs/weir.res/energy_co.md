---
description: Weir discharge exponential coefficient
---

# exp\_k

**Code reference:** `res_weir(ires)%k` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L140)).

`exp_k` is the exponent applied to the water depth above the weir crest in the weir-release equation: `(reservoir area in ha * 0.45) * linear_c * width * head^exp_k`.
