---
description: Volume of water needed to fill the reservoir to principal spillway
---

# vol\_ps

**Code reference:** `res_hyddb(ires)%pvol` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L69)).

Volume of water needed to fill the reservoir to the principal spillway (`ha-m`; Fortran struct default: `0.`, historical table default: `1500.0`, range `15.0–3000.0`). QSWAT+ assumes an average depth of 10 m, so its interface default is $10 \cdot A_{\text{psa}}$.

If `vol_ps` $\le 0$ when SWAT+ reads `hydrology.res` ([`res_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_hyd.f90#L52-L55)) and $V_{\text{pvol}} + V_{\text{evol}} > 0$, the model sets `vol_ps` from emergency spillway volume (or `60000.0` ha-m otherwise):

$$V_{\text{pvol}} = 0.9 \, V_{\text{evol}}$$

where $V_{\text{pvol}}$ is `vol_ps` (ha-m) and $V_{\text{evol}}$ is [vol\_es](vol_es-1.md) (ha-m). During initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L31)), SWAT+ converts from ha-m to $\text{m}^3$:

$$V_{\text{pvol,m3}} = 10000 \cdot V_{\text{pvol}}$$

where $V_{\text{pvol}}$ is the input in ha-m and $V_{\text{pvol,m3}}$ is the internal storage target ($\text{m}^3$).
