---
description: Reservoir surface area when reservoir is filled to emergency spillway
---

# area\_es

**Code reference:** `res_hyddb(ires)%esa` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L71)).

Reservoir surface area when filled to the emergency spillway (`ha`; Fortran struct default: `0.`, historical table default: `500.0`, range `1.0–1000.0`). By default, QSWAT+ sets `area_es` to `1.15 * area_ps`. If `area_es` $\le 0$ when SWAT+ reads `hydrology.res` ([`res_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_hyd.f90#L59)), the model estimates it from principal spillway area:

$$A_{\text{esa}} = 1.5 \, A_{\text{psa}}$$

where $A_{\text{esa}}$ is `area_es` (ha) and $A_{\text{psa}}$ is [area\_ps](area_ps.md) (ha).

Although the historical `hydrology.res` summary table lists smaller values for emergency spillway defaults/ranges than for principal spillway, physically `area_es` must exceed [area\_ps](area_ps.md) (and [vol\_es](vol_es-1.md) must exceed [vol\_ps](vol_ps.md)) for SWAT+ to fit the two-point log-linear area–volume curve in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_initial.f90#L62-L84); otherwise the model falls back to the fixed exponent `0.9` ($b_2$).
