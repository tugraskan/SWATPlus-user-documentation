---
description: Time to drain soil to field capacity
---

# t\_fc

**Code reference:** `sdr(isdr)%time` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L88)).

Time required to drain the soil profile from saturation to field capacity in hours (default `48.00`, range `0.0–100.0`). Used with the original drawdown tile drainage routine (`tiledrain = 0` in `codes.bsn`) in [`swr_origtile.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_origtile.f90#L23-L28):

$$q_{\text{tile}} = \min\!\left(SW_{\text{ex}}\left(1 - e^{-24 / t}\right),\; D_c\right)$$

where $q_{\text{tile}}$ is daily tile drainage (mm), $SW_{\text{ex}}$ is excess soil water above field capacity (mm), $t$ is `t_fc` (hours), and $D_c$ is the drainage coefficient (`drain`, mm/day). If `t_fc < 1.0`, all excess soil water drains on that day, subject to the `drain` cap.
