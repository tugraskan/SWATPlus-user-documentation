---
description: Residue decomposition coefficient
---

# rsd\_decomp

**Code reference:** `bsn_prm%rsdco` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L98), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Default daily fraction of residue that decomposes under optimal moisture, temperature, C:N ratio, and C:P ratio (default `0.05`, range `0.02–0.1`; values `< 1.e-6` are reset to `0.05` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L23)).

During plant-parameter initialization ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L22)), any crop in [**plants.plt**](../../databases/plants.plt/) whose `rsdco_pl` is `< 1.e-6` inherits `rsd_decomp`. The resulting rate coefficient $c_{\text{rsd}}$ drives daily decay in [`nut_nminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L171), [`rsd_decomp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rsd_decomp.f90#L112), and [`cbn_surfrsd_decomp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cbn_surfrsd_decomp.f90#L115):

$$\delta_r = c_{\text{rsd}}\,c_a\,f_{\text{cs}}$$

where $\delta_r$ is the daily residue decomposition fraction (dimensionless), $c_{\text{rsd}}$ is the crop decomposition coefficient (`rsdco_pl`, defaulting to `rsd_decomp`, dimensionless), $c_a$ is the residue C:N/C:P ratio factor (dimensionless), and $f_{\text{cs}}$ is the combined soil temperature and soil-water factor (dimensionless).
