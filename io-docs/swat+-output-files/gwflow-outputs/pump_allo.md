---
description: "Groundwater pumping for HRU irrigation"
---

# pump_allo

**Code reference:** `gw_hyd_ss(i)%ppag` for daily cell output ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1223)).

Cell pumping removals are negative. The daily per-cell diagnostic is assigned for each request, while period arrays add requests, so summing the printed daily cell values need not reproduce period results when a cell serves repeated requests.

The separate HRU pumping reports use positive `hru_pump` diagnostics, monthly/yearly totals in m3, and average annual in m3/yr. The same printed name does not imply the same value, sign, unit, or serialization path. Their daily long-format writer follows a reset; see the family warning.

**Unit:** m3/day for this cell report's flux fields.

**Period treatment:** daily rows print the daily cell diagnostic. Monthly rows divide the separate `gw_hyd_ss_mo` array by `time%day_mo`; yearly rows divide `gw_hyd_ss_yr` by `time%day_end_yr`. Average-annual rows sum yearly daily means and divide by `real(time%nbyr)`, giving equal weight to yearly means rather than pooling every simulated day. These rates are not the mm basin totals. See [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1336), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1593), and [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1638).

The period arrays have their own producers and known gaps; they cannot all be reconstructed by summing daily rows. See the [family table](README.md).

[Back to the cell water-balance schema](cell-water-balance.md).
