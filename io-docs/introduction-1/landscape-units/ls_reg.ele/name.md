---
description: "Record name"
---

# name

**Code reference:** `reg_elem(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L211), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L157)).

Name of the landscape region element (`character(len=16)`, default `""`). Note that [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205) is never called in SWAT+ main (`6f515368`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
