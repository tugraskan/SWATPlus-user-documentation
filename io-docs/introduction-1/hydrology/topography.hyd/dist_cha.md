---
description: Average distance to stream
---

# dist\_cha

**Code reference:** `topo_db(ith)%dis_stream` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L10)).

Average distance from the HRU to the stream in meters. The built-in topography record uses 100 m. The supplied value is copied to the HRU and can be changed with the calibration parameter `dis_stream`. The nitrogen-loss equation that used it is commented out. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L68) · [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L153-L155) · [`nut_nlch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L149-L152)

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations.)*
