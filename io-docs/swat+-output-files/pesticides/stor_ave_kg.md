---
description: "Average, initial, and final pesticide storage"
---

# stor_ave_kg

**Code reference:** `aqupst_d(j)%pest(ipest)%stor_ave` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L12)).

The daily value equals `stor_final_kg`. The snapshot is taken at the end of that pesticide's turn, so it can miss daughter mass added by a parent processed later in the day. [Daily snapshots and loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L366-L378).

**Unit:** kg.

The daily producer copies the end-of-day stored mass into this field. Monthly and yearly output averages those daily values using calendar month length or `time%day_end_yr`. Average annual divides the accumulated daily storage by `time%days_prt`. The basin writer sums aquifer masses before applying the same time divisions. [Daily assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L375), [Storage averaging operator](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_pesticide_module.f90#L117)

[Back to schema](aquifer-pesticide-balance.md).
