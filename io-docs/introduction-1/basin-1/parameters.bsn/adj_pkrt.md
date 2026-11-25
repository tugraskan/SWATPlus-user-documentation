---
description: Adjustment factor for the weather-generator half-hour rainfall fraction
---

# adj\_pkrt

**Code reference:** `bsn_prm%adj_pkr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L83), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless adjustment factor (default `1`, range `0.5–2`; values `< 1.e-6` are reset to `1.0` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L12)) for the weather-generator monthly maximum half-hour rainfall fraction ($\alpha_{0.5,\text{mo}}$) in [`cli_initwgn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_initwgn.f90#L294-L300):

$$\alpha_{0.5,\text{mo}} = \min\!\Big(0.95,\;\max\!\big(0.1,\; a_{\text{pkr}}\,(1 - \exp(x_3 / \bar{P}_{\text{mo}}))\big)\Big)$$

where $a_{\text{pkr}}$ is `adj_pkrt`, $x_3$ is derived from smoothed monthly maximum 0.5-hour rainfall, and $\bar{P}_{\text{mo}}$ is mean monthly wet-day rainfall (`mm`). This field does not directly control sediment routing in SWAT+ main (`6f515368`).
