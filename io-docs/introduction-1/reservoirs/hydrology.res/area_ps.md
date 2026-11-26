---
description: Reservoir surface area when reservoir is filled to principal spillway
---

# area\_ps

**Code reference:** `res_hyddb(ires)%psa` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L68)).

Reservoir surface area when filled to the principal spillway (`ha`; Fortran struct default: `0.`, historical table default: `1500.0`, range `1–3000.0`). If a shapefile is used to implement reservoirs in QSWAT+, the interface sets `area_ps` to the polygon area. If `area_ps` $\le 0$ when SWAT+ reads `hydrology.res` ([`res_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_hyd.f90#L58)), the model estimates it from principal spillway volume:

$$A_{\text{psa}} = 0.08 \, V_{\text{pvol}}$$

where $A_{\text{psa}}$ is `area_ps` (ha) and $V_{\text{pvol}}$ is [vol\_ps](vol_ps.md) (ha-m).

SWAT+ pairs (`area_ps`, [vol\_ps](vol_ps.md)) with ([area\_es](area_es.md), [vol\_es](vol_es-1.md)) in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L62-L84) to fit the power-law area–volume curve applied daily in [`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L203):

$$A = b_1 V^{b_2}$$

where $A$ is daily surface area (ha), $V$ is reservoir storage ($\text{m}^3$), and $b_1, b_2$ are the fitted shape parameters. SWAT+ also uses `area_ps` in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L35) to initialize the default weir height:

$$h_{\text{weir}} = \frac{V_{\text{pvol,m3}}}{10000 \, A_{\text{psa}}}$$

where $h_{\text{weir}}$ is the default weir height (m), $V_{\text{pvol,m3}}$ is principal spillway storage ($\text{m}^3$), and $A_{\text{psa}}$ is `area_ps` (ha).
