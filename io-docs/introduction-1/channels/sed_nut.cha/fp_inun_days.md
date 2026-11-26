---
description: "Number of days the flood plain remains inundated after a flood event"
---

# fp_inun_days

**Code reference:** `sd_chd1(idb)%fp_inun_days` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L49)).

Number of days the flood plain remains inundated after a flood event (`days`, struct default `5.0`). On SWAT+ dev it enters a trap efficiency that is then replaced in the same block, so it has no effect on floodplain deposition ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L137-L153)).

{% hint style="warning" %}
(In SWAT+ main, [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L79) reset it to `1.0` on every call.)
{% endhint %}
