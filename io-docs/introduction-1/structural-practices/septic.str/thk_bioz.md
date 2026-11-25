---
description: Thickness of biozone layer
---

# thk\_bioz

**Code reference:** `sep(isep)%thk` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L29)).

The biozone layer is a thin soil layer underneath the septic tank effluent (STE) distribution chamber where pollutants are degraded by naturally existing live biomass bacteria. In [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L108), `thk_bioz` (mm) determines the biozone volume ($V_{\text{bz}}$, $\text{m}^3$) and the [plaque-adjusted saturated storage capacity](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L198) ($UL$, mm):

$$V_{\text{bz}} = h_{\text{bz}} \cdot A_{\text{hru}} \cdot 10, \qquad UL = \phi \cdot h_{\text{bz}} - \frac{M_{\text{plq}}}{10 \, \rho_b}$$

where $h_{\text{bz}}$ is `thk_bioz` (mm), $A_{\text{hru}}$ is HRU area (ha), $\phi$ is soil porosity, $M_{\text{plq}}$ is plaque mass (kg/ha), and $\rho_b$ is [`bm_dens`](bm_dens.md) ($\text{kg/m}^3$).
