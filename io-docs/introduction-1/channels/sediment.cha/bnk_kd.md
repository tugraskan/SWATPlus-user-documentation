---
description: "Jet-test-derived erodibility of the channel bank sediment"
---

# bnk_kd

**Code reference:** `ch_sed(ich)%bnk_kd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L98)).

Jet-test-derived erodibility of the channel bank sediment (`cm3/(N*s)`). When `bnk_kd <= 1.0e-6`, [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L94-L100) sets it to `0.2` if `tc_bnk <= 1.0e-6` or to $0.2 / \sqrt{\tau_{\text{c,bnk}}}$ otherwise, where $\tau_{\text{c,bnk}}$ is `tc_bnk` (Hanson and Simon, 2001).
