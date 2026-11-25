---
description: "First day of year of the pumping period"
---

# pe_dy_s

**Code reference:** `pe_dy_s` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L139), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L984)).

Day of year (1–365) on which the period starts; that day is included ([`gwflow_pump_ext.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_ext.f90#L39-L41)). It is ignored when [pe_yr_s](pe_yr_s.md) is before the first simulation year.
