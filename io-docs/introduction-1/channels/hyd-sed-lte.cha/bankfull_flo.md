---
description: Bankfull flow factor
---

# bankfull\_flo

**Code reference:** `sd_chd(idb)%bankfull_flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L36)).

Factor applied to the channel's flow at bankfull depth (from the channel rating curve) to get the flow above which water spills onto the floodplain ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L109)).

{% hint style="warning" %}
During initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L97-L98)), values at or below `1.0e-6` are clamped to `0.0`. In SWAT+ main (6f515368), [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L78) overwrites this factor with `1.5` every call before multiplying it by the rating-curve bankfull flow. From source reading, the entered factor does not control this sediment-routing path.
{% endhint %}
