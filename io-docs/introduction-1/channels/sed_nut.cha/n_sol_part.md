---
description: "Instream transformation coefficient converting soluble nitrogen to particulate nitrogen"
---

# n_sol_part

**Code reference:** `sd_chd1(idb)%n_sol_part` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L52)).

Instream transformation coefficient converting nitrate (`no3`) to organic nitrogen (`orgn`) when `bsn_cc%qual2e == 1` (struct default `0.01`). In [`sd_channel_control3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L205-L212), the transformed fraction over reach travel time $t_{\text{travel}}$ (`h`) is:

$$f_{\text{N}} = 1 - \exp\!\left(-k_{\text{N}}\,t_{\text{travel}}\right)$$

where $f_{\text{N}}$ is the transformed fraction (dimensionless), $k_{\text{N}}$ is `n_sol_part` (`1/h`), and $t_{\text{travel}}$ is reach travel time (`h`).

The converted mass (`min(ht1%no3, f_N * ht1%orgn)`) is added to `ht2%orgn` and subtracted from `ht2%no3`.
