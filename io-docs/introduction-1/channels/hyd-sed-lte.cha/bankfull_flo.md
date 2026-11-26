---
description: Bankfull flow factor
---

# bankfull\_flo

**Code reference:** `sd_chd(idb)%bankfull_flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L36)).

Factor applied to the channel's flow at bankfull depth (from the channel rating curve) to get the flow above which water spills onto the floodplain ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L109)).

{% hint style="warning" %}
During initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L97-L98)), values at or below `1.0e-6` are clamped to `0.0`. On SWAT+ dev the entered factor is used: [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L108-L132) multiplies it by the second rating-curve flow to get the bankfull flow that sets the overbank fraction. (SWAT+ main overwrote it with `1.5` on every call.)
{% endhint %}
