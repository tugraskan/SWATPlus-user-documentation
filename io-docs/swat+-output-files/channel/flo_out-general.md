---
description: "Mean daily channel outflow rate"
---

# flo_out

**Code reference:** `ch_out_d(ichan)%flo` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

The normal channel controller divides the daily routed volume after water-allocation withdrawals by 86,400. Tiny channels can report only the last incoming contribution even when a larger flow is passed downstream. [Outflow assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L330-L372) · [Daily flow sources and bypass](sd-channel-general.md#where-the-daily-water-values-come-from)

**Unit:** m3/s. Daily rows contain the day's mean discharge. Monthly and yearly rows average daily rates over the reporting days. Average-annual rows average the yearly mean rates over reporting years ([period treatment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L43)). Other hydrograph report families can retain water volumes under similar headings; this mapping is specific to `channel_sd_*`.

[Back to the SD channel general schema](sd-channel-general.md).
