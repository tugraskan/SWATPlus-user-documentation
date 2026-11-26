---
description: "Average air temperature lag, in days, applied to snowmelt temperature inputs"
---

# sno_lag

**Code reference:** `w_temp(ich_temp)%sno_lag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L174)).

Average air temperature lag in days (`1–3`, struct default `2`) intended for snowmelt temperature calculation in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L309-L324). Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads rows into `w_temp(1:)` while [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L189) reads `w_temp(0)%sno_lag`, source reading indicates entered values do not affect simulation results at `6f515368`.
