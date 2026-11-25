---
description: "Average air temperature lag, in days, applied to groundwater temperature inputs"
---

# gw_lag

**Code reference:** `w_temp(ich_temp)%gw_lag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L175)).

Average air temperature lag in days (`200–365`, struct default `250`) intended for groundwater temperature calculation in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_temp.f90#L272-L287). Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads rows into `w_temp(1:)` while [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L190) reads `w_temp(0)%gw_lag`, source reading indicates entered values do not affect simulation results at `6f515368`.
