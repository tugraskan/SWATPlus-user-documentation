---
description: "Net lateral flow between groundwater cells"
---

# lateral

**Code reference:** `latl_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L589)); `gw_hyd_grid_mo%latl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L125)).

The signed sum of lateral groundwater exchanges between cells. This basin sum is a net exchange, not the sum of all positive intercell transfers.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

Positive cell values are inflow from non-boundary neighbors and negative values are outflow. The basin output sums these signed values; it does not sum absolute transfers or promise exact cancellation. ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L85)).

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
