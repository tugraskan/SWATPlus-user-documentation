---
description: Oxygen uptake rate per unit of algal respiration
---

# alg\_o2\_resp

**Code reference:** `ch_nut(ich)%ai4` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L142)).

Mass of oxygen consumed per unit mass of algal respiration (`mg O2/mg alg`, default `2.0`, range `1.60–2.30`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L68), values `<= 0.` are replaced with `2.0`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L213-L216), `alg_m1` and `alg_m` are evaluated identically so `alg_m2 = 0`, and `alg_m_o2` ([`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L272)) is omitted from `factm` at [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L278). From source reading at `6f515368`, `alg_o2_resp` does not affect simulated dissolved oxygen.
