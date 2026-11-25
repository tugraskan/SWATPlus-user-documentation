---
description: >-
  Coefficient to control the impact of the storage time constant for normal flow
  on the overall storage time constant for the channel
---

# msk\_co1

**Code reference:** `bsn_prm%msk_co1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L100), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Weighting coefficient ($c_1$, default `0.75`, range `0–10`; values `< 1.e-6` are reset to `0.75` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L25)) controlling the influence of bankfull-depth storage time constant ($K_{\text{bf}}$) on the Muskingum reach storage time constant ($K_m$, `hours`) in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L169-L171):

$$K_m = \frac{c_1}{c_1 + c_2}\,K_{\text{bf}} + \frac{c_2}{c_1 + c_2}\,K_{0.1\text{bf}}$$

where $c_2$ is [msk\_co2](msk_co2.md) and $K_{0.1\text{bf}}$ is the low-flow storage time constant at `0.1` times bankfull depth. This parameter is only used when channel routing uses the Muskingum method ([rte\_cha](../codes.bsn/rte_cha.md) = `1`).
