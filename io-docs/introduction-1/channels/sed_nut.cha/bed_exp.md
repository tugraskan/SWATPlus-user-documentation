---
description: "Exponential coefficient controlling bed erosion rate for the channel reach"
---

# bed_exp

**Code reference:** `sd_chd1(idb)%bed_exp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L57)).

Exponential coefficient $\beta$ controlling bed erosion rate in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L284) (struct default `1.5`):

$$e_{\text{btm}} = 0.0001\left(\frac{v}{v_{\text{cr}}}\right)^{\beta}$$

where $e_{\text{btm}}$ is bed erosion depth (`m`), $v$ is flow velocity (`m/s`), $v_{\text{cr}}$ is critical velocity (`m/s`), and $\beta$ is `bed_exp` (dimensionless).

{% hint style="warning" %}
On SWAT+ dev the entered `bed_exp` is used: bed cutting is `0.0001 × (v / v_cr)^bed_exp` m when velocity exceeds the critical velocity ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L273-L288)). The bed load is still not added to the routed hydrograph ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L296-L298)). (SWAT+ main reset `bed_exp` to 1.0 on every call.)
{% endhint %}
