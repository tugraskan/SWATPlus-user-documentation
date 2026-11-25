---
description: "Coefficient influencing the magnitude of groundwater temperature contributions to the channel"
---

# gw

**Code reference:** `w_temp(ich_temp)%gw` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L172)).

Dimensionless coefficient (struct default `1.0`) intended to scale the groundwater temperature contribution in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L330). Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads rows into `w_temp(1:)` while [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L199) reads `w_temp(0)%gw`, source reading indicates entered values do not affect simulation results at `6f515368`.
