---
description: Perennial leaf turnover rate with minimum stress
---

# leaf\_tov\_min

**Code reference:** `pldb(ic)%leaf_tov_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L80)).

Turnover applies to perennials with the `moisture_gro` trigger ([`pl_leaf_senes.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_leaf_senes.f90#L87-L104)).

Minimum-stress perennial leaf-turnover time, in months. SWAT+ converts the stress-adjusted monthly turnover time to a daily turnover fraction as 1 / (30 × leaf_tov_mon).
