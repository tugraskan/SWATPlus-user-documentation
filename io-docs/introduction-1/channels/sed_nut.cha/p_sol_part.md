---
description: "Instream transformation coefficient converting soluble phosphorus to particulate phosphorus"
---

# p_sol_part

**Code reference:** `sd_chd1(idb)%p_sol_part` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L53)).

Instream transformation coefficient converting soluble phosphorus (`solp`) to particulate phosphorus (`sedp`) when `bsn_cc%qual2e == 1` (struct default `0.01`). In [`sd_channel_control3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L214-L220), the transformed fraction over reach travel time $t_{\text{travel}}$ (`h`) is:

$$f_{\text{P}} = 1 - \exp\!\left(-k_{\text{P}}\,t_{\text{travel}}\right)$$

where $f_{\text{P}}$ is the transformed fraction (dimensionless), $k_{\text{P}}$ is `p_sol_part` (`1/h`), and $t_{\text{travel}}$ is reach travel time (`h`).

The converted mass (`min(ht1%solp, f_P * ht1%sedp)`) is added to `ht2%sedp` and subtracted from `ht2%solp`.
