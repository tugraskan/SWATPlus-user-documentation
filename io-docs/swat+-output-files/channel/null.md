---
description: "Numeric hydrograph temperature slots"
---

# null

The general SD channel header prints `null` three times. Each position corresponds to a real numeric hydrograph component, not a separator:

| Position | Written component |
| --- | --- |
| After `grv_stor` | `ch_stor(ichan)%temp` |
| After `grv_in` | `ch_in_d(ichan)%temp` |
| After `grv_out` | `ch_out_d(ichan)%temp` |

**Code reference:** [write order](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_output.f90#L33) and [hydrograph declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49).

**Unit:** deg C in the declaration; the printed units row leaves these slots blank. The actual printed label remains `null`. This establishes numeric positions and their source components, not that all three carry physically meaningful simulated temperatures. They are distinct from the appended `water_temp` field.

[Back to the SD channel general schema](sd-channel-general.md).
