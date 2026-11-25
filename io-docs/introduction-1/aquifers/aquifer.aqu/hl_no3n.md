---
description: Half-life of NO3-N in the aquifer
---

# hl\_no3n

**Code reference:** `aqudb(i)%hlife_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L20)).

Nitrate nitrogen in the aquifer can be removed by bacterial uptake or by chemical conversion in oxygen-depleted zones. The half-life (days) is the time needed for the nitrate concentration to fall to half its original value, as a net result of all these processes. [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L170) converts it to a daily retention factor, which is applied to stored nitrate in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L162):

$$
\text{NO3}_{t} = \text{NO3}_{t-1} \times \exp\left(\frac{-0.693}{t_{1/2} + 0.1}\right)
$$

where $\text{NO3}_{t}$ and $\text{NO3}_{t-1}$ are stored aquifer nitrate nitrogen on days $t$ and $t-1$, and $t_{1/2}$ is `hl_no3n` (days). The 0.1-day offset prevents division by zero. With _hl\_no3n_ = 0, about 99.9% of stored nitrate is removed each day.
