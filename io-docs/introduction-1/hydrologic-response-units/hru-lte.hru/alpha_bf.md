---
description: Baseflow alpha factor
---

# alpha\_bf

**Code reference:** `hlt_db(i)%abf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L22)).

Daily baseflow recession constant (1/days). SWAT+ converts it to a retention factor when reading the file ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L138)) and uses it for shallow aquifer flow in mm ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L336-L337)):

$$Q_{gw,t} = Q_{gw,t-1} \, e^{-\alpha} + w_{perc} \left( 1 - e^{-\alpha} \right)$$

where $Q_{gw,t}$ and $Q_{gw,t-1}$ are shallow aquifer flow on day $t$ and day $t-1$ (`mm`), $\alpha$ is `alpha_bf` (`1/days`), and $w_{perc}$ is daily soil percolation (`mm`). Flow is limited to the water stored in the shallow aquifer.
