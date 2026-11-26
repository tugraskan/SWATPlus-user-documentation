---
description: Clay content of channel bank and bed
---

# clay

**Code reference:** `sd_chd(idb)%ch_clay` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L32)).

Clay content of the channel bank and bed material, entered in percent (`%`, default `50.00`, range `0–100`).

{% hint style="info" %}
On SWAT+ dev the bank critical velocity was replaced ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L209-L238)). `clay` now enters only through a cohesion factor:
{% endhint %}

$$
v_{cr} = 0.8 \cdot c_{veg} \cdot 0.87\, e^{0.0202\, C_{clay}}
$$

where $v_{cr}$ is the bank critical velocity (m/s), $c_{veg}$ is the cover factor (set to 1.0 by the routine, see [cov\_fact](cov_fact.md)) and $C_{clay}$ is `clay` (%). The SWAT+ main cohesion equation, its 1000 floor and the unused exponent `b_exp` are gone.
