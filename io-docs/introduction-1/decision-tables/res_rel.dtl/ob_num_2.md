---
description: "Not used in release calculations"
---

# ob_num

**Code reference:** `dtbl_res(i)%act(iac)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L19)).

Object number on the action row. The release calculation does not read it; the action always applies to the object being simulated. Enter 0. [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L87-L106)

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in release calculations).*
