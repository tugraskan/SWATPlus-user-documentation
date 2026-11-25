---
description: Qual2E light averaging option
---

# q2e\_lt

**Code reference:** `ch_nut(ich)%lao` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L132)).

Qual2E defines four light averaging options:

1. Depth-averaged algal growth attenuation factor for light (FL) is computed from one daylight average solar radiation value calculated in the steady state temperature heat balance.
2. FL is computed from one daylight average solar radiation value supplied by the user.
3. FL is obtained by averaging the hourly daylight values of FL computed from the hourly daylight values of solar radiation calculated in the steady state temperature heat balance.
4. FL is obtained by averaging the hourly daylight values of FL computed from the hourly daylight values of solar radiation calculated from a single value of total daily, photosynthetically active, solar radiation and an assumed cosine function.

The options above describe the intended light-averaging methods.

SWAT+ main (6f515368) stores this field as a real value and replaces a nonpositive value with `2` in [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L62), but does not branch on `lao` in [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L175-L188) (which always evaluates Light Averaging Option #2).
