---
description: Volume of water needed to fill the reservoir to emergency spillway
---

# vol\_es

**Code reference:** `res_hyddb(ires)%evol` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L72)).

Volume of water needed to fill the reservoir to the emergency spillway (`ha-m`; Fortran struct default: `0.`, historical table default: `55.0`, range `10.0–100.0`). QSWAT+ assumes an average depth of 10 m, so its interface default is $10 \cdot A_{\text{esa}}$.

If `vol_es` $\le 0$ when SWAT+ reads `hydrology.res` ([`res_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_hyd.f90#L57)), SWAT+ estimates it from principal spillway volume:

$$V_{\text{evol}} = 1.11 \, V_{\text{pvol}}$$

where $V_{\text{evol}}$ is `vol_es` (ha-m) and $V_{\text{pvol}}$ is [vol\_ps](vol_ps.md) (ha-m). During initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L30)), SWAT+ converts from ha-m to $\text{m}^3$:

$$V_{\text{evol,m3}} = 10000 \cdot V_{\text{evol}}$$

where $V_{\text{evol,m3}}$ is the internal emergency-spillway storage volume ($\text{m}^3$) and $V_{\text{evol}}$ is `vol_es` (ha-m).

Although the historical `hydrology.res` summary table lists smaller values for emergency spillway defaults/ranges than for principal spillway, physically `vol_es` must exceed [vol\_ps](vol_ps.md) (along with [area\_es](area_es.md) exceeding [area\_ps](area_ps.md)) for SWAT+ to fit the two-point area–volume curve in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_initial.f90#L62-L84) instead of falling back to fixed exponent `0.9` ($b_2$).
