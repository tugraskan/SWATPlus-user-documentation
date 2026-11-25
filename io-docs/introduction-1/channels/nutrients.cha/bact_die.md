---
description: Coliform die-off rate in the reach at 20ºC
---

# bact\_die

**Code reference:** `ch_nut(ich)%rk5` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L126)).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory and values `<= 0.` are replaced with `2.0` in [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L102), but `rk5` is not used in simulation calculations).* Additionally, selecting `"rk5"` in calibration ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L609-L611)) modifies `ch_nut%rs2` instead of `rk5`.
