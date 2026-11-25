---
description: >-
  Initial soil water storage expressed as a fraction of field capacity water
  content
---

# sw\_init

**Code reference:** `bsn_prm%ffcb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L81), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

All soils in the watershed are initialized to the same fraction of field capacity water content (default `0`, range `0–1`; values `< 1.e-6` are reset to `0.` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L10)). When `sw_init <= 0.`, [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L88-L92) estimates the initial fraction ($f_{\text{fc}}$) from average annual precipitation ($P_{\text{ann}}$, `mm`):

$$f_{\text{fc}} = \frac{P_{\text{ann}}}{P_{\text{ann}} + \exp(9.043 - 0.002135\,P_{\text{ann}})}$$

where $f_{\text{fc}}$ is the estimated initial fraction of field capacity water content (dimensionless) and $P_{\text{ann}}$ is average annual precipitation (`mm`).

{% hint style="info" %}
We recommend using a warm-up period of at least 1 year, i.e. start the simulation at least 1 year prior to the period of interest. This allows the model to get the water cycling properly before any comparisons between measured and simulated data are made. If a warm-up period is incorporated, the value for *sw\_init* will not impact model results.
{% endhint %}
