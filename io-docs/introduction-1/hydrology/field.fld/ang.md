---
description: Field orientation angle
---

# ang

**Code reference:** `field_db(ith)%ang` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L19)).

Field orientation angle in degrees. The built-in field record uses 30°. SWAT+ copies the value to the HRU and routing unit and exposes `field_ang` for HRU calibration. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L83-L86) · [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L241-L248) · [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L191-L193)

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations.)*
