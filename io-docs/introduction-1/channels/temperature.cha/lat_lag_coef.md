---
description: "Coefficient applied to the lateral flow air temperature lag"
---

# lat_lag_coef

**Code reference:** `w_temp(ich_temp)%lat_lag_coef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L178)).

Dimensionless coefficient (struct default `0.75`) intended to scale lagged lateral-flow air temperature in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L331). Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads rows into `w_temp(1:)` while [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L197) reads `w_temp(0)%lat_lag_coef`, source reading indicates entered values do not affect simulation results at `6f515368`.
