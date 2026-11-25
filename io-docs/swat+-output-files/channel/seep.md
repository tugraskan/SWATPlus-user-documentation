---
description: "Seepage volume out of the channel bottom"
---

# seep

**Code reference:** `ch_wat_d(ichan)%seep` ([water-body declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L11); [channel writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

The router computes transmission loss from channel-bed conductivity, reach length, and width, caps it at available channel storage, and subtracts it from storage. With GWFlow enabled, the report records zero for this column even if that subtraction occurs. [Transmission loss and reported value](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L192-L208)

**Unit:** m3. These water-body terms are volumes, not ha-m. Monthly and yearly values accumulate daily amounts; average-annual values divide the accumulated amounts by reporting years.

[Back to the SD channel general schema](sd-channel-general.md).
