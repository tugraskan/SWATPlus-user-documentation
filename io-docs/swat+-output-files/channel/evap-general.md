---
description: "Evaporation volume from the channel surface"
---

# evap

**Code reference:** `ch_wat_d(ichan)%evap` ([water-body declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L10); [channel writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

Potential evapotranspiration times the reach evaporation coefficient and channel footprint, capped at available channel storage. The footprint uses channel length times width. [Evaporation calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L210-L225)

**Unit:** m3. These water-body terms are volumes, not ha-m. Monthly and yearly values accumulate daily amounts; average-annual values divide the accumulated amounts by reporting years.

[Back to the SD channel general schema](sd-channel-general.md).
