---
description: "Jet-test-derived erodibility of the channel bed sediment"
---

# bed_kd

**Code reference:** `ch_sed(ich)%bed_kd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L99)).

Jet-test-derived erodibility of the channel bed sediment (`cm3/(N*s)`). When `bed_kd <= 1.0e-6`, [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L105-L111) sets it to `0.2` if `tc_bed <= 1.0e-6` or to $0.2 / \sqrt{\tau_{\text{c,bed}}}$ otherwise, where $\tau_{\text{c,bed}}$ is `tc_bed` (Hanson and Simon, 2001).
