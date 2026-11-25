---
description: "Name of the salt input record (salt_res) linked to this reservoir"
---

# salt

**Code reference:** `res_dat_c_cs(ires)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L20)).

Foreign key referencing [name](../salt_res/name.md) in [**salt\_res**](../salt_res/). In [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L48-L49), SWAT+ matches this name to set `res_dat(ires)%salt`, which is used by [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L130-L134) to initialize salt-ion concentrations and masses in reservoir water.
