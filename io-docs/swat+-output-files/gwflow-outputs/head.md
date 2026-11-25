---
description: "Groundwater head with explicit period averaging"
---

# head

**Code reference:** daily `gw_state(i)%head`, monthly `gw_state(i)%hdmo`, yearly `gw_state(i)%hdyr`, and average annual `gw_head_sum_aa(i) / nbyr_r` ([daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1228); [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1364); [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1621); [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2025)).

Groundwater head for the reported active cell. Monthly head sums are divided by `time%day_mo`; yearly sums by `time%day_end_yr`. Average annual is the sum of yearly mean heads divided by the configured `time%nbyr`, rather than a single mean weighted by every simulated day.

A mid-month or mid-year start can lower the corresponding reported mean for a positive head. See [partial reporting periods](cell-water-balance.md#partial-reporting-periods).

**Unit:** m.

This is hydraulic head, not depth below ground surface. The latter is [wt_depth](wt_depth.md).

[Back to the cell water-balance schema](cell-water-balance.md).
