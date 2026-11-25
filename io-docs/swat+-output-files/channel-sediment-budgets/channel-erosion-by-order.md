# Channel Erosion by Order

`chanbud_order_*` writes a 12-value row for each order from 1 through 12, including orders with no contributions. The `_d`, `_m`, `_y`, and `_a` suffixes select daily, monthly, yearly, and average-annual files in TXT and optional CSV. [File creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_sd_channel.f90#L280), [Writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/chord_sedbud_output.f90#L12-L90)

| Position | Field | Description | Unit |
| ---: | --- | --- | --- |
| 1 | `jday` | Day of year | n/a |
| 2 | `mon` | Month | n/a |
| 3 | `day` | Day of month | n/a |
| 4 | `yr` | Calendar year | n/a |
| 5 | `iord` | SWAT-DEG channel order | n/a |
| 6 | `num` | Heading only: the value is the summed overbank days (`ob_days`) of the order's channels | days |
| 7 | `ebank_t` | Bank erosion mass, summed over the order's channels | tons |
| 8 | `ebtm_t` | Bed erosion mass, summed | tons |
| 9 | `ebank_m` | Bank cutting distance, divided by the number of channels in the order | m |
| 10 | `ebtm_m` | Bed cutting depth, divided by the number of channels in the order | m |
| 11 | `fp_t` | Floodplain sediment deposited, summed | tons |
| 12 | `fp_mm` | Floodplain deposition thickness, divided by the number of channels in the order | mm |

On SWAT+ dev the width, depth, floodplain-area and count columns of SWAT+ main are gone ([headings](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L497-L528)). Each channel with inflow adds its daily record to its order ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L314-L315)). When the row is written, `ebank_m`, `ebtm_m` and `fp_mm` are divided by the number of channels whose order equals `iord` **on that day**; the other values stay sums ([`chord_sedbud_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/chord_sedbud_output.f90#L14-L17), [`sd_channel_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L723-L744)). Channels without inflow count in that divisor, and if a decision table changes a channel's order during a period, the period total is divided by the count on the print day. Average-annual rows first divide the sums by the number of printed years.

The producer uses the channel's current order directly as the index into the 12 bins, so an order outside 1–12 is outside the array bounds ([order initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L75), [12-bin declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L109)). The erosion values use the same calculations as the [per-channel report](channel-erosion-by-channel.md#erosion-and-deposition-calculations).

[Back to the Channel Sediment Budgets index](README.md).
