---
description: "Bankfull channel depth"
---

# dep_bf

**Code reference:** `chsd_d(ich)%dep_bf = sd_ch_vel(ich)%dep_bf` ([assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L431)).

Bankfull channel depth. The initialization copies channel depth `sd_ch(i)%chd` into `sd_ch_vel(i)%dep_bf` ([initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L142); [channel-depth unit](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L633)).

**Unit:** m. The source's printed morphology units row incorrectly labels this depth `m/s`. This interpretation follows the assigned depth, rather than the field name alone.

[Back to the SD channel morphology schema](sd-channel-morphology.md).
