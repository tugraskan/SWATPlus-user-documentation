---
description: "Precipitation volume on the channel surface"
---

# precip

**Code reference:** `ch_wat_d(ichan)%precip` ([water-body declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L9); [channel writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

The model multiplies precipitation depth by the channel footprint when inlet volume exceeds `1.e-6` m³. It adds that water to routing after recording `flo_in`. At or below the threshold it leaves this value at zero. [Precipitation calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L99-L106)

**Unit:** m3. These water-body terms are volumes, not ha-m. Monthly and yearly values accumulate daily amounts; average-annual values divide the accumulated amounts by reporting years.

[Back to the SD channel general schema](sd-channel-general.md).
