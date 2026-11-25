---
description: "Record name"
---

# name

**Code reference:** `acu_out(i)%name` / `acu_reg(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L60)).

Name of the aquifer cataloging unit (`character(len=16)`, struct default `"basin"`), read into both `acu_out(i)%name` (`#L55`, `#L60`) and `acu_reg(i)%name` (`#L98`, `#L103`) in [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L55-L103).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
