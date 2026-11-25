---
description: Name of the Landscape Unit
---

# name (ls\_unit.def)

**Code reference:** `lsu_out(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L70)).

Name of the Landscape Unit (`character(len=16)`, struct default `"basin"`). SWAT+ writes `lsu_out(ilsu)%name` to daily, monthly, yearly, and average-annual LSU output files (`lsunit_wb_*`, `lsunit_nb_*`, `lsunit_ls_*`, `lsunit_pw_*`) in [`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L72-L252), and does not use it in physical calculations.
