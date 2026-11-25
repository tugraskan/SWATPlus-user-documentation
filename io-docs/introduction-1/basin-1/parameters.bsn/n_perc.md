---
description: Nitrate percolation coefficient
---

# n\_perc

**Code reference:** `bsn_prm%nperco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L90), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Controls the concentration of nitrate removed from the top soil layer in surface runoff relative to the percolating/lateral-flow concentration ($\beta_N$, default `0.1`, range `0–1`; values `< 1.e-6` are reset to `0.1` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L17) and copied per HRU in [`hrudb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hrudb_init.f90#L33)).

In [`nut_nlch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nlch.f90#L93), surface-runoff nitrate loss (`kg/ha`) is:

$$\text{NO}_{3,\text{surq}} = Q_{\text{surf}}\,\beta_N\,C_{\text{NO3}}$$

where $Q_{\text{surf}}$ is surface runoff (`mm`) and $C_{\text{NO3}}$ is the mobile-water nitrate concentration (`kg/ha/mm`). The same coefficient also scales surface-runoff concentrations for salts ([`salt_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L125)) and constituents ([`cs_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_lch.f90#L103)).
