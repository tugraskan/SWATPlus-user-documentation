---
description: Absolute upper limit enforced on landscape soft-calibration parameters.
---

# up

**Code reference:** `ls_prms(i)%up` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L77), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ls_read_parms_cal.f90#L37)).

Absolute maximum parameter value (struct default `0.`) enforced after each update in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L84-L814) and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L85-L725):

$$p = \min(p, u)$$

where $p$ is the calibrated parameter value and $u$ is `up`.

For row 4 (`pet_co`), [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L36) temporarily narrows the upper limit toward $1$ during pass 1 and restores it at [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L45):

$$u_1 = u - \frac{u - 1}{2}, \qquad u = u_1 + (u_1 - 1)$$

where $u_1$ is the temporary pass-1 upper limit and $u$ is `up`.
