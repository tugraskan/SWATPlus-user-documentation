---
description: Fraction of solar radiation that is photosynthetically active
---

# slr\_act

**Code reference:** `ch_nut(ich)%tfact` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L147)).

Fraction of incoming daily solar radiation that is photosynthetically active (dimensionless, default `0.30`, range `0.0–1.0`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L73), values `<= 0.` are replaced with `0.3`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L178-L182), `tfact` scales weather-station solar radiation $H_{\text{solrad}}$ divided by daylength $T_{\text{day}}$ to compute daylight-average photosynthetically active light intensity $I_a$ used in the algal light-attenuation factor:

$$I_a = \frac{H_{\text{solrad}} \cdot \text{tfact}}{T_{\text{day}}}$$

where $I_a$ is daylight-average photosynthetically active light intensity, $H_{\text{solrad}}$ is weather-station solar radiation, $\text{tfact}$ is `slr_act` (dimensionless), and $T_{\text{day}}$ is daylength.
