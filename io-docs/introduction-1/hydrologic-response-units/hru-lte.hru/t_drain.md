---
description: Design subsurface tile drain time
---

# t\_drain

**Code reference:** `hlt_db(i)%tdrain` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L46)).

Tile drainage time in hours. A value of 0 means no tile flow. Otherwise daily tile flow in mm is taken from water above available water capacity and capped at 10 mm ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L308-L316)):

$$q_{tile} = \min \left( (SW - AWC) \left( 1 - e^{-24/t} \right), \; 10 \right)$$

where $q_{tile}$ is daily tile flow (`mm`), $SW$ is soil water content (`mm`), $AWC$ is profile available water capacity (`mm`), and $t$ is `t_drain` (`hours`).
