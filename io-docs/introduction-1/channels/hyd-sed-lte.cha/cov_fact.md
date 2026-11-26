---
description: Channel cover factor
---

# cov\_fact

**Code reference:** `sd_chd(idb)%cov` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L28)).

The channel cover factor is defined as the ratio of degradation from a channel with a specified vegetative cover to the corresponding degradation from a channel with no vegetative cover. The vegetation affects degradation by reducing the stream velocity, and consequently its erosive power, near the bed surface.

{% hint style="info" %}
A value of **cov\_fact** = 1 indicates that there is no vegetative cover on the channel. A value of **cov\_fact** = 0 indicates that the channel is completely protected from erosion.
{% endhint %}

{% hint style="info" %}
On SWAT+ dev the bank-erosion routine sets the cover factor to `1.0` on every call before computing the critical velocity, so the entered value has no effect there ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L209-L238)). It still enters the gully headcut coefficient at initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L121))).
{% endhint %}
