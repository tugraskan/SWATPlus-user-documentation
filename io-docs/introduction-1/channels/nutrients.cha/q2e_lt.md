---
description: Qual2E light averaging option
---

# q2e\_lt

**Code reference:** `ch_nut(ich)%lao`

**Declared type:** `channel_nut_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_read_nut.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/channel_data_module.f90#L132)).

Qual2E defines four light averaging options:

1. Depth-averaged algal growth attenuation factor for light (FL) is computed from one daylight average solar radiation value calculated in the steady state temperature heat balance.
2. FL is computed from one daylight average solar radiation value supplied by the user.
3. FL is obtained by averaging the hourly daylight values of FL computed from the hourly daylight values of solar radiation calculated in the steady state temperature heat balance.
4. FL is obtained by averaging the hourly daylight values of FL computed from the hourly daylight values of solar radiation calculated from a single value of total daily, photosynthetically active, solar radiation and an assumed cosine function.

The options above describe the intended light-averaging methods.

SWAT+ main (6f515368) stores this field as a real value and replaces a nonpositive value with 2, but does not use the selected light-averaging option in a later calculation.
