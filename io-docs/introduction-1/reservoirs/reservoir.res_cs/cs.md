---
description: "Name of the constituent input record (cs_res) linked to this reservoir"
---

# cs

**Code reference:** `res_dat_c_cs(ires)%cs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L21)).

Foreign key referencing [name](../cs_res/name.md) in [**cs\_res**](../cs_res/). In [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L56-L57), SWAT+ matches this name to set `res_dat(ires)%cs`, which is used by [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L148-L158) to initialize constituent concentrations and by [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L230) during daily constituent routing.
