---
description: Potential ET method
---

# pet\_flag

**Code reference:** `hlt_db(i)%ipet` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L43)).

Potential ET method ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L162-L175)):

* `harg`: Hargreaves method
* `p_t`: Priestley-Taylor method

Only the exact value `harg` selects Hargreaves. Any other value uses Priestley-Taylor.
