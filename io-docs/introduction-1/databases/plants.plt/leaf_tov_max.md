---
description: Perennial leaf turnover rate with maximum stress
---

# leaf\_tov\_max

**Code reference:** `pldb(ic)%leaf_tov_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L81)).

Turnover applies to perennials with the `moisture_gro` trigger ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L87-L104)).

Maximum-stress perennial leaf-turnover time, in months. SWAT+ combines it with leaf_tov_min and converts the result to a daily turnover fraction as 1 / (30 × leaf_tov_mon).
