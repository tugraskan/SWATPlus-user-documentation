---
description: "Channel bank erodibility factor scaling the computed bank critical shear stress"
---

# cov1

**Code reference:** `ch_sed(ich)%cov1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L94)).

Channel bank erodibility factor (struct default `0.1`) scaling the computed bank critical shear stress in [`ch_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_initial.f90#L89-L93) and providing the monthly `erod(1:12)` fallback when all monthly values sum below `1.0e-6` ([`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L118-L122)). [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L65-L73) clamps `cov1` to `[0.0, 1.0]` when `eqn <= 0`, and to `[1.0, 25.0]` (resetting `<= 0.0` to `1.0`) when `eqn > 0`.
