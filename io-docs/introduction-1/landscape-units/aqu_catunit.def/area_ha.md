---
description: "Region area"
---

# area\_ha

**Code reference:** `acu_out(i)%area_ha` / `acu_reg(i)%area_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L195), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L60)).

Region area in hectares (`real`, `ha`, struct default `0.0`), read into `acu_out(i)%area_ha` (`#L55`, `#L60`) and `acu_reg(i)%area_ha` (`#L98`, `#L103`) in [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L55-L103).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
