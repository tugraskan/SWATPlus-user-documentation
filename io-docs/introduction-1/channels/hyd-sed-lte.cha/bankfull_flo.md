---
description: Bankfull flow factor
---

# bankfull\_flo

**Code reference:** `sd_chd(idb)%bankfull_flo`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L36)).

Factor applied to the channel's flow at bankfull depth (from the channel rating curve) to get the flow above which water spills onto the floodplain.

{% hint style="warning" %}
In SWAT+ 62.0.1 the channel sediment routine resets this value to 1.5 every time it runs, so the value in hyd-sed-lte.cha currently has no effect.
{% endhint %}
