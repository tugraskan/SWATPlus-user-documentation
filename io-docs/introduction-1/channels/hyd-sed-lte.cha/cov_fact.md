---
description: Channel cover factor
---

# cov\_fact

**Code reference:** `sd_chd(idb)%cov` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L28)).

The channel cover factor is defined as the ratio of degradation from a channel with a specified vegetative cover to the corresponding degradation from a channel with no vegetative cover. The vegetation affects degradation by reducing the stream velocity, and consequently its erosive power, near the bed surface.

{% hint style="info" %}
A value of **cov\_fact** = 1 indicates that there is no vegetative cover on the channel. A value of **cov\_fact** = 0 indicates that the channel is completely protected from erosion.
{% endhint %}
