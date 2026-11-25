---
description: "Name of the reservoir and wetland salt record"
---

# name (salt\_res)

**Code reference:** `res_salt_data(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_salt_module.f90#L36)).

Primary key identifying each initial salt-concentration record for reservoirs and wetlands. It is referenced by [salt](../reservoir.res_cs/salt.md) in [**reservoir.res\_cs**](../reservoir.res_cs/) (matched in [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L48)) and by wetland salt links in [`wet_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_salt_cs.f90#L48).
