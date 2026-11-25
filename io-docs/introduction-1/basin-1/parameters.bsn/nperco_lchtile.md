---
description: Nitrogen concentration coefficient for tile flow
---

# nperco\_lchtile

**Code reference:** `bsn_prm%nperco_lchtile` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L108), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Dimensionless nitrate concentration multiplier ($\beta_{\text{tile}}$, default `0.5`, range `0–1`; values `< 1.e-6` are reset to `0.50` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L30) and copied per HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L35)).

In [`nut_nlch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L114), `nperco_lchtile` scales nitrate removed by subsurface tile drainage (`kg/ha`):

$$\text{NO}_{3,\text{tile}} = C_{\text{NO3}}\,\beta_{\text{tile}}\,Q_{\text{tile}}$$

where $C_{\text{NO3}}$ is the mobile-water nitrate concentration (`kg/ha/mm`) summed from the tile layer downward and $Q_{\text{tile}}$ is tile flow (`mm`). Despite the `lchtile` name, SWAT+ main (`6f515368`) does not apply this factor to bottom-layer percolation leaching ([`nut_nlch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L140-L148)).
