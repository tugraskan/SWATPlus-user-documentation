---
description: "Record number"
---

# k

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L19)).

The leading integer identifier on this data row. In [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L40-L43), SWAT+ reads this integer into `ires` to index `res_dat_c_cs(ires)` (matching reservoir records in [**reservoir.res**](../reservoir.res/)), then backspaces and re-reads it into `k`.
