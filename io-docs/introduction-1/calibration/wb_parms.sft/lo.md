---
description: Absolute lower limit enforced on landscape soft-calibration parameters.
---

# lo

**Code reference:** `ls_prms(i)%lo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L76), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ls_read_parms_cal.f90#L37)).

Absolute minimum parameter value (struct default `0.`) enforced after each update in [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L85-L815) and [`caltsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/caltsoft_hyd.f90#L86-L726):

$$p = \max(p, l)$$

where $p$ is the calibrated parameter value and $l$ is `lo`.

For row 4 (`pet_co`), [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L35) temporarily narrows the lower limit toward $1$ during pass 1 and restores it at [`calsoft_hyd_bfr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd_bfr.f90#L44):

$$l_1 = l + \frac{1 - l}{2}, \qquad l = l_1 - (1 - l_1)$$

where $l_1$ is the temporary pass-1 lower limit and $l$ is `lo`.
