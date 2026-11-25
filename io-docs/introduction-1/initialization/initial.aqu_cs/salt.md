---
description: "Name of the referenced salt initialization record"
---

# salt

**Code reference:** `aqu_init_dat_c_cs(iaqu)%salt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L91)).

Foreign key referencing [name](../salt_aqu.ini/name.md) in [**salt\_aqu.ini**](../salt_aqu.ini/). When `cs_db%num_salts > 0`, [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L113-L127) matches `aqu_init_dat_c_cs(iaq)%salt` positionally for aquifer `iaq` and initializes `cs_aqu(iaq)%saltc`, `cs_aqu(iaq)%salt`, and `cs_aqu(iaq)%salt_min`.
