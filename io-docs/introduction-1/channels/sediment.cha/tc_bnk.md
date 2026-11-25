---
description: "Critical shear stress required to initiate motion of the channel bank"
---

# tc_bnk

**Code reference:** `ch_sed(ich)%tc_bnk` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L102)).

Critical shear stress required to initiate motion of the channel bank (`N/m2`). Negative values are clamped to `0.` in [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L60). When `tc_bnk <= 1.0e-6`, [`ch_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_initial.f90#L89-L93) estimates it from bank silt + clay percentage and multiplies by `cov1`.
