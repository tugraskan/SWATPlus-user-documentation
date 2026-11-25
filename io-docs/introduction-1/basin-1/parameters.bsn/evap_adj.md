---
description: Reach evaporation adjustment factor
---

# evap\_adj

**Code reference:** `bsn_prm%evrch` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L109), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Calibration multiplier (default `0.6`, range `0.5–1`; values `< 1.e-6` are reset to `0.60` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L32)) used to adjust open-water evaporation from main channels, especially to dampen reach evaporation in arid regions.

In [`ch_rtmusk.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtmusk.f90#L216-L221), daily channel evaporation (`m^3/day`) is computed as:

$$E_{\text{ch}} = \text{evrch} \cdot \text{PET} \cdot \frac{1000\,L_{\text{ch}}\,W_{\text{ch}}}{1000}$$

where:
- $E_{\text{ch}}$ is daily channel evaporation (`m^3/day`, capped by available channel water storage),
- $\text{evrch}$ is `evap_adj` (dimensionless),
- $\text{PET}$ is daily potential evapotranspiration (`mm`),
- $L_{\text{ch}}$ is channel length (`km`), and
- $W_{\text{ch}}$ is channel width (`m`).
