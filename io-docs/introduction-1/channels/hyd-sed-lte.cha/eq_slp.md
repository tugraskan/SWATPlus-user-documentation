---
description: Critical velocity multiplier
---

# eq\_slp

**Code reference:** `sd_chd(idb)%vcr_coef` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L30)).

{% hint style="info" %}
On SWAT+ dev this coefficient is read but not used: the line that applied it is gone and the new critical velocity has no coefficient ([`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L209-L238)). The text below describes SWAT+ main.
{% endhint %}

On SWAT+ main this dimensionless coefficient (`sd_ch%vcr_coef`, default `0`) multiplied the critical velocity calculated in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L175-L177):

$$v_{\text{cr,adj}} = c_{\text{vcr}}\,v_{\text{cr}}$$

where $v_{\text{cr,adj}}$ is the adjusted critical velocity (`m/s`), $c_{\text{vcr}}$ is `eq_slp` (dimensionless), and $v_{\text{cr}}$ is the unadjusted critical velocity (`m/s`).

A value of `0` sets critical velocity to `0` (allowing bank erosion whenever reach velocity is positive at [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_sediment3.f90#L186)), while `1` uses the calculated critical velocity unchanged.
