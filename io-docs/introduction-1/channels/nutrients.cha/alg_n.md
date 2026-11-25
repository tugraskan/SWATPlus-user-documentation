---
description: Fraction of algal biomass that is nitrogen
---

# alg\_n

**Code reference:** `ch_nut(ich)%ai1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L139)).

Fraction of algal biomass that is nitrogen (`mg N/mg alg`, default `0.08`, range `0.07–0.09`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L65), values `<= 0.` are replaced with `0.08`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L220-L221), `ai1` is used to compute intermediate algal nitrogen uptake terms (`alg_no3_m` and `alg_nh4_m`). However, from source reading at `6f515368`, the reach ammonia and nitrate updates in [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L284-L301) do not add `alg_nh4_m` or `alg_no3_m`, so `alg_n` does not alter simulated nitrogen concentrations.
