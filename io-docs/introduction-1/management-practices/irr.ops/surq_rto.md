---
description: Surface runoff ratio
---

# sumq\_frac

**Code reference:** `irrop_db(irr_op)%surq` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L9), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L48)).

Dimensionless surface runoff ratio (`fraction`; default `0.0`, valid range `0.0–1.0`) dividing irrigation water between land application and immediate surface runoff.

In [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L361-L362), [`#L532`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L533), [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L149-L150), [`#L253-L259`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L275-L281), and [`wet_irrp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_irrp.f90#L109-L110), SWAT+ assigns the fraction $(1 - f_{\text{surq}})$ (multiplied by `eff_frac`) to applied irrigation and the fraction $f_{\text{surq}}$ to irrigation surface runoff `irrig(j)%runoff`.
