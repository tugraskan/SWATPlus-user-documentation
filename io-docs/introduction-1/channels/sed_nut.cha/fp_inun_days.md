---
description: "Number of days the flood plain remains inundated after a flood event"
---

# fp_inun_days

**Code reference:** `sd_chd1(idb)%fp_inun_days` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L49)).

Number of days the flood plain remains inundated after a flood event (`days`, struct default `5.0`). It multiplies the floodplain trap-efficiency calculation in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L122-L128).

{% hint style="warning" %}
In SWAT+ main (`6f515368`), [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L79) resets `sd_ch(ich)%fp_inun_days = 1.0` on every call before trap efficiency is computed. Based on source reading, values entered in `sed_nut.cha` do not affect floodplain deposition unless modified through calibration after that reset (which does not occur inside the daily sediment routine).
{% endhint %}
