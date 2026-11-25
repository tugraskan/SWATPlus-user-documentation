---
description: "Mass fraction of the fertilizer that is mineral nitrogen (sum of NO3 and NH3)"
---

# fminn

**Code reference:** `manure_om(it)%fminn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/fertilizer_data_module.f90#L40)).

Mineral N fraction, in kg N per kg. [fnh3n](fnh3n.md) splits it between ammonium and nitrate ([`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L84-L85), [`pl_manure.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_manure.f90#L167-L168)).
