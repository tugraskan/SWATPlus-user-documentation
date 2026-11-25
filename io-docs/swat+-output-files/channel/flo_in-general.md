---
description: "Mean daily channel inflow rate"
---

# flo_in

**Code reference:** `ch_in_d(ichan)%flo` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

The normal channel controller divides the inlet volume by 86,400 before adding channel rainfall or handling overbank flow. Tiny channels can use only the last incoming contribution. [Inlet assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L153-L170) · [Daily flow sources and bypass](sd-channel-general.md#where-the-daily-water-values-come-from)

**Unit:** m3/s. Daily rows contain the day's mean discharge. Monthly and yearly rows average daily rates over the reporting days. Average-annual rows average the yearly mean rates over reporting years ([period treatment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L43)). Other hydrograph report families can retain water volumes under similar headings; this mapping is specific to `channel_sd_*`.

[Back to the SD channel general schema](sd-channel-general.md).
