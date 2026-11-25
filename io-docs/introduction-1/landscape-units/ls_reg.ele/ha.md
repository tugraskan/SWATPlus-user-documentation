---
description: "Area of the region element in hectares"
---

# ha

**Code reference:** `reg_elem(i)%ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L212), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L157)).

Area of the landscape region element in hectares (`real`, `ha`, default `0.0`). Even inside the uncalled [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L190-L196), region HRU areas are taken from `hru(ihru)%area_ha` or `lsu_elem(iihru)%ru_frac * lsu_out(ilsu)%area_ha`, not `reg_elem%ha`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
