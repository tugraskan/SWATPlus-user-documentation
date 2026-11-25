---
description: "Groundwater evapotranspiration"
---

# gw_et

**Code reference:** `gwet_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L584)); `gw_hyd_grid_mo%gwet` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L120)).

Groundwater consumed by evaporation and plant water uptake.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

The groundwater-ET producer records removal with a negative sign. ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_gwet.f90#L72)).

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
