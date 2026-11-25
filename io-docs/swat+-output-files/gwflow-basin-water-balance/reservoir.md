---
description: "Groundwater exchange with reservoirs"
---

# reservoir

**Code reference:** `resv_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L595)); `gw_hyd_grid_mo%resv` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L132)).

Signed groundwater exchange with reservoirs.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

Positive values indicate reservoir water entering groundwater; negative values indicate groundwater entering the reservoir. ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L69)).

The routine visits the active neighbors of the reservoir cells and uses the difference between the configured reservoir elevation and the neighbor's groundwater head. It computes a horizontal exchange using a connection length based on the smaller cell area. A reservoir-to-cell exchange is set to zero if adding it to the running signed seepage total would exceed reservoir storage. Groundwater discharge is capped at the cell's available storage. The same signed net exchange is written to the reservoir's seepage term. [Neighbor loop and exchange](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L39-L89) · [Reservoir seepage assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_reservoir.f90#L213-L215)

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
