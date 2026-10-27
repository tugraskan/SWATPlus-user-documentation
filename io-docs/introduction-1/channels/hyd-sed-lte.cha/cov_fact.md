---
description: Channel cover factor
---

# cov\_fact

**Code reference:** `sd_chd(idb)%cov`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L28)).

The channel cover factor is defined as the ratio of degradation from a channel with a specified vegetative cover to the corresponding degradation from a channel with no vegetative cover. The vegetation affects degradation by reducing the stream velocity, and consequently its erosive power, near the bed surface.

{% hint style="info" %}
A value of **cov\_fact** = 1 indicates that there is no vegetative cover on the channel. A value of **cov\_fact** = 0 indicates that the channel is completely protected from erosion.
{% endhint %}
