---
description: Width of grassed waterway
---

# wd

**Code reference:** `grwaterway_db(igrwwop)%grwat_w` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L53)).

Top width of the grassed waterway in metres (m; range `0.0–1000.0`). Used with depth ([`dp`](dp.md)) and the assumed 8:1 side slope to compute the trapezoidal channel bottom width ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L98-L101), [`ttcoef_wway.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ttcoef_wway.f90#L66)):

$$b = w - 2 \cdot d \cdot z$$

where $b$ is bottom width (m), $w$ is `wd` (m), $d$ is `dp` (m), and $z$ is the horizontal-to-vertical side slope (`8`). If $b \le 0$, SWAT+ resets `dp` to $\frac{3}{64} \, w$.
