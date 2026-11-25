---
description: "Action type, normally release"
---

# typ

**Code reference:** `dtbl_res(i)%act(iac)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L17)).

Use `release` for reservoir release actions. The reader uses the type to resolve named `weir` and `meas` records. The release calculation uses the option to select the equation after the row is eligible. [`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L76-L97) · [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L87-L106)
