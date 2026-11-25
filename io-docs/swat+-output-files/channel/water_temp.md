---
description: "Current channel water temperature"
---

# water_temp

**Code reference:** `wtemp` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33)).

The individual report appends the current `wtemp` value after the outgoing hydrograph's numeric `null` slot. The controller sets `wtemp` to 5 + 0.75 times the weather station's daily mean air temperature. It is a shared variable. The reporting loop runs after channel processing, so multiple rows can show the value left by the last channel that set it. Longer-period rows use the same reporting-day value. The [basin schema](basin-sd-channel-general.md) ends at column 65. [Shared variable declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L6), [Temperature calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L450), [Reporting loop](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L578)

**Unit:** deg C.

[Back to the SD channel general schema](sd-channel-general.md).
