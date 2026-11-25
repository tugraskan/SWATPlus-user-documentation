---
description: >-
  Coefficient to control the impact of the storage time constant for low flow on
  the overall storage time constant for the channel
---

# msk\_co2

**Code reference:** `bsn_prm%msk_co2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L102), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Weighting coefficient ($c_2$, default `0.25`, range `0–10`; values `< 1.e-6` are reset to `0.25` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L27)) controlling the influence of the low-flow storage time constant ($K_{0.1\text{bf}}$, evaluated at `0.1` times bankfull depth) on the overall Muskingum storage time constant $K_m$ in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L169-L171) (see [msk\_co1](msk_co1.md)).

This parameter is only used when channel routing uses the Muskingum method ([rte\_cha](../codes.bsn/rte_cha.md) = `1`).
