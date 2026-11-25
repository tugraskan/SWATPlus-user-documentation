---
description: "Groundwater/channel exchange diagnostic"
---

# gw_sw

**Code reference:** `gw_hyd_ss(i)%gwsw` for daily cell output ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1223)).

Daily negative values represent groundwater discharge to channels. In the monthly and yearly cell arrays, the channel-exchange routine adds signed Q to `gwsw` for both directions, so those fields and their average-annual derivatives are net channel exchange rather than discharge alone. Positive values can therefore represent channel seepage into groundwater.

Source: [daily split and combined period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L89).

**Unit:** m3/day for this cell report's flux fields.

**Period treatment:** daily rows print the daily cell diagnostic. Monthly rows divide the separate `gw_hyd_ss_mo` array by `time%day_mo`; yearly rows divide `gw_hyd_ss_yr` by `time%day_end_yr`. Average-annual rows sum yearly daily means and divide by `real(time%nbyr)`, giving equal weight to yearly means rather than pooling every simulated day. These rates are not the mm basin totals. See [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1336), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1593), and [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1638).

The period arrays have their own producers and known gaps; they cannot all be reconstructed by summing daily rows. See the [family table](README.md).

[Back to the cell water-balance schema](cell-water-balance.md).
