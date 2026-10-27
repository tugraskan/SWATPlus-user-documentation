---
description: Not used; daily curve-number runoff uses a fixed impervious-area curve number of 98
---

# urb\_cn

**Code reference:** `urbdb(iu)%urbcn2`

**Declared type:** `urban_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_parm_read.f90#L42), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_data_module.f90#L16)).

SWAT+ reads this value from `urban.urb` but does not use it afterward, so changing it has no effect. For daily curve-number runoff, the model instead uses a fixed curve number of 98 for impervious urban area.
