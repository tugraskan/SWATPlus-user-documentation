---
description: "Groundwater discharge through tile drains"
---

# tile

**Code reference:** `tile_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L594)); `gw_hyd_grid_mo%tile` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L131)).

Groundwater discharged through tile drains.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

Negative values represent discharge from groundwater through tile drains. The daily per-cell diagnostic is assigned rather than accumulated; repeated qualifying calls replace its previous value. ([producer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_tile.f90#L50)).

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

The producer also adds each tile-drain event to separate monthly and yearly cell accumulators. The cell files divide those accumulators by their period day counts. The basin files sum the normalized daily values, which use the last stored daily value per cell. If the same cell qualifies repeatedly, converting the cell rates back to volumes can still give a different total. [Event bookkeeping](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_tile.f90#L59), [Basin daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L900), [Monthly cell division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1340), [Yearly cell division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1597)

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
