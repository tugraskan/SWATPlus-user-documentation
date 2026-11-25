---
description: "Groundwater exchange with canals"
---

# canal

**Code reference:** `canl_grid` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L597)); `gw_hyd_grid_mo%canl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L135)).

Signed groundwater exchange with canals.

**Unit:** mm.

The daily diagnostic is summed over active cells and divided by the full basin area, then converted from m3 to mm. Monthly and yearly basin values sum these normalized daily diagnostics. Average-annual output divides the simulation accumulator by `real(time%nbyr)`, the configured simulation-year count, rather than `time%yrs_prt` or a separately counted set of reporting years.

Positive values indicate canal water entering groundwater. Negative values indicate groundwater leaving toward a canal. Three routines add signed flow to this same cell counter:

- Channel-linked canals cap positive seepage at the source channel's available storage and deduct it from that channel. [Channel-linked canal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal.f90#L119-L150)
- Recall-diversion canals calculate exchange only when the canal has stored water. Positive seepage is capped at and deducted from that diverted storage. [Recall-diversion canal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_div.f90#L67-L121)
- External canals use a configured operating day range. The model treats the supply for positive seepage as unlimited. [External canal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_ext.f90#L39-L87)

All three cap negative exchange using available groundwater. The channel-linked and Recall-diversion routines record the groundwater loss without adding that volume to the linked channel or diversion storage. [Channel-linked update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal.f90#L132-L150) · [Diversion update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal_div.f90#L103-L121)

The basin accumulators are updated independently of whether daily output is enabled ([normalization and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L869); [average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1985)).

[Back to the daily schema](daily-basin-water-balance.md) · [Back to the longer-period schema](longer-period-basin-water-balance.md).
