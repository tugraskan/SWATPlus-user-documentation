---
description: Stream-order or basin record name in ch_sed_budget.sft.
---

# name

**Code reference:** `chcal(i)%ord(iord)%meas%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L290), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L122)).

Name of the stream-order target record (up to 16 characters, struct default `""`). When set to `"basin"`, [`calsoft_sum_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sum_output.f90#L160-L167) accumulates length-weighted simulated channel widening, downcutting, and headcut advance across the region's channels.
