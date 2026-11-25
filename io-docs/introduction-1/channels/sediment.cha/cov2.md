---
description: "Channel bed cover factor scaling the computed bed critical shear stress"
---

# cov2

**Code reference:** `ch_sed(ich)%cov2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L95)).

Channel bed cover factor (struct default `0.1`) scaling the computed bed critical shear stress in [`ch_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_initial.f90#L95-L99). [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L66-L74) clamps `cov2` to `[0.0, 1.0]` when `eqn <= 0`, and to `[1.0, 25.0]` (resetting `<= 0.0` to `1.0`) when `eqn > 0`.
