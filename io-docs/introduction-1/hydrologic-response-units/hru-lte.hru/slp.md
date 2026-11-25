---
description: Land surface slope
---

# slp

**Code reference:** `hlt_db(i)%slope` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L18)).

Average land surface slope in m/m. It drives lateral soil flow ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L297-L302)) and the calculated USLE [LS factor](usle_ls.md) ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L237-L242)).
