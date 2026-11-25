---
description: "Recharge-pond seepage to groundwater"
---

# pond

**Code reference:** `pond_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L599)); `gw_hyd_grid_mo%pond` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L136)).

Water entering groundwater through recharge-pond seepage.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

Positive values indicate seepage from recharge ponds entering groundwater. ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L250)).

After the configured operating start, the model adds source water and rainfall and deducts evaporation. It assigns each active connected cell seepage equal to pond-bed conductivity times connection area, bounded by the pond water remaining when the cell is processed. The cell loop deducts that water as it goes. If the code finds no configured channel, diversion canal, or unlimited source, it skips rainfall, evaporation, and seepage for that pond. [Operating date and sources](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L76-L97) · [Source gate and sequential seepage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L151-L263)

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
