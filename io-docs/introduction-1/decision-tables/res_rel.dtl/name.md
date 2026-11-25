---
description: "Decision table name"
---

# name

**Code reference:** `dtbl_res(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L29)).

Decision table name, up to 40 characters. Reservoir and wetland initialization match their release fields to this name; a name that matches nothing gives no warning. A [reservoir.res](../../reservoirs/reservoir.res/README.md) `rel` name starting with `ctbl_` selects a control table instead. The calibration condition `res_typ` also compares against table names, but it looks up the table by reservoir number rather than the reservoir's own table. [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L129-L137) · [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L87-L95)
