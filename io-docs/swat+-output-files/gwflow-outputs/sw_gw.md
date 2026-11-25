---
description: "Surface-water seepage diagnostic with a period-accumulation gap"
---

# sw_gw

**Code reference:** `gw_hyd_ss(i)%swgw` for daily cell output ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1223)).

Daily positive values represent channel seepage into groundwater. No accumulating producer was identified for the monthly or yearly cell `swgw` arrays: the channel routine instead adds both directions to `gwsw`. Their zero/default-derived values must not be interpreted as verified absence of seepage.

Source: [daily split and combined period accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_channel_exch.f90#L89).

**Unit:** m3/day for this cell report's flux fields.

**Period treatment:** daily rows print the daily cell diagnostic. Monthly rows divide the separate `gw_hyd_ss_mo` array by `time%day_mo`; yearly rows divide `gw_hyd_ss_yr` by `time%day_end_yr`. Average-annual rows sum yearly daily means and divide by `real(time%nbyr)`, giving equal weight to yearly means rather than pooling every simulated day. These rates are not the mm basin totals. See [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1336), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1593), and [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1638).

The period arrays have their own producers and known gaps; they cannot all be reconstructed by summing daily rows. See the [family table](README.md).

[Back to the cell water-balance schema](cell-water-balance.md).
