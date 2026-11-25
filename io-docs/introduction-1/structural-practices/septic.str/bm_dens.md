---
description: Density of biomass
---

# bm\_dens

**Code reference:** `sep(isep)%bd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L32)).

Density of live biomass and plaque in the biozone ($\text{kg/m}^3$). In [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L198), it converts biomass and plaque mass per hectare into equivalent depth (mm) when updating biozone saturated storage capacity ($UL$, mm) and field capacity ($FC$, mm):

$$UL = \phi \cdot h_{\text{bz}} - \frac{M_{\text{plq}}}{10 \, \rho_b}$$

where $\rho_b$ is `bm_dens` ($\text{kg/m}^3$), $\phi$ is soil porosity, $h_{\text{bz}}$ is [`thk_bioz`](thk_bioz.md) (mm), and $M_{\text{plq}}$ is plaque mass (kg/ha). It also scales the daily biomass change in the [field-capacity update](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L192) using [`fc_lin`](fc_lin.md) and [`fc_exp`](fc_exp.md).
