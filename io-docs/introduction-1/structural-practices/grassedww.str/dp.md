---
description: Depth of grassed waterway
---

# dp

**Code reference:** `grwaterway_db(igrwwop)%grwat_d` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L52)).

Channel depth of the grassed waterway in metres (m; range `0.0–10.0`). In [`smp_grass_wway.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_grass_wway.f90#L109), assuming 8:1 channel side slopes, `dp` sets the channel capacity and the side-slope sheet-flow area $A_{\text{sf}}$ ($\text{m}^2$):

$$A_{\text{sf}} = (d - d_{\text{flow}}) \cdot 8.06 \cdot L \cdot 1000$$

where $A_{\text{sf}}$ is the side-slope sheet-flow area ($\text{m}^2$), $d$ is `dp` (m), $d_{\text{flow}}$ is daily flow depth (m), and $L$ is waterway length ([`len`](len.md), km). At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L85-L101)), SWAT+ checks bottom width:

$$b = w - 16 \, d$$

where $b$ is bottom width (m), $w$ is [`wd`](wd.md) (m), and $d$ is `dp` (m). If `dp <= 0` or $b \le 0$, SWAT+ resets `dp` to:

$$d = \frac{3}{64} \, w$$

where $d$ is the reset `dp` (m) and $w$ is [`wd`](wd.md) (m).
