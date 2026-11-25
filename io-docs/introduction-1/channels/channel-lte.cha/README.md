---
description: >-
  This file summarizes the main channel information and references several other
  files that specify the details.
---

# channel-lte.cha

{% hint style="info" %}
[`sd_channel_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_read.f90#L218-L296) stores each row at `sd_dat(i)` using the integer `id` column (`i`), then resolves `init`, `hyd`, `sednut`, and `nut` indices using the loop counter `sd_dat(ichi)`. Keep row `id` values sequential (`1, 2, ...`) matching file row order.
{% endhint %}

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [id](id-channel-lte.cha.md) | ID of the channel | integer |  |  |  |
| [name](name.md) | Name of the channel | string |  |  |  |
| [cha\_ini](cha_ini.md) | Pointer to the channel initialization file | string |  |  |  |
| [cha\_hyd](cha_hyd.md) | Pointer to the channel hydrology and sediment file | string |  |  |  |
| [cha\_sed](cha_sed.md) | Placeholder sediment pointer (currently not used) | string |  |  |  |
| [cha\_nut](cha_nut.md) | Pointer to the channel nutrient file | string |  |  |  |
