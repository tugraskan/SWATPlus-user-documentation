---
description: Land-use calibration group name for a water_balance.sft target row.
---

# name

**Code reference:** `lscal(ireg)%lum(ilum)%meas%name` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L89), [match](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sum_output.f90#L32)).

Calibration group identifier (up to 16 characters, struct default `"default"`). Matched against each HRU's `lum_group_c` (`cal_group` in `landuse.lum`) in [`calsoft_sum_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sum_output.f90#L32) and [`calsoft_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_hyd.f90#L81); `"basin"` applies to all HRUs in the region.
