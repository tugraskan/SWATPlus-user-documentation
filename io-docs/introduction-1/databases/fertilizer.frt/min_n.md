---
description: Fraction of fertilizer that is mineral N (NO3+NH3)
---

# min\_n

**Code reference:** `fertdb(it)%fminn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fertilizer_data_module.f90#L7)).

Mass fraction of the applied fertilizer that is mineral N, in kg N per kg fertilizer. It is split into nitrate, `min_n × (1 − nh3_n)`, and ammonium, `min_n × nh3_n`, and added to the soil ([`pl_fert.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert.f90#L81-L84)) or to ponded water ([`pl_fert_wet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_fert_wet.f90#L63-L64)).
