---
description: Soil water adjustment factor for CN3
---

# cn3\_swf

**Code reference:** `hyd_db(ithyd)%cn3_swf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L17)).

Fraction $f$ of the interval from field capacity to saturation used to set the soil water content corresponding to wet-condition curve number CN3. The curve number calculation uses:

$$W_3 = W_{\mathrm{fc}} + f\left(W_{\mathrm{sat}} - W_{\mathrm{fc}}\right)$$

where $W_3$ is the soil water content corresponding to CN3 (mm), $W_{\mathrm{fc}}$ is the profile field capacity water content (mm), $f$ is `cn3_swf` (fraction), and $W_{\mathrm{sat}}$ is the profile saturated water content (mm). SWAT+ then bounds the result before fitting the retention curve. [`curno.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/curno.f90#L67-L81)

For an HRU with a tile drain, SWAT+ sets this fraction to 0.95 at initialization. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L54-L58)
