---
description: "Area of the channel"
---

# area

**Code reference:** `ch_wat_d(ichan)%area_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L8)).

On days when inlet volume exceeds `1.e-6` m³, the model multiplies channel length (km) by width (m) and divides by 10. At or below that threshold it retains the previous value or initial default. [Area assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L82-L102)

**Unit:** ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the SD channel general schema](sd-channel-general.md).
