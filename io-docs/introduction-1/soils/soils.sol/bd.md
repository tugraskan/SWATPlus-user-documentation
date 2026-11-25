---
description: Moist bulk density of the soil layer
---

# bd

**Code reference:** `soildb(isol)%ly(j)%bd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L48)).

Moist bulk density of the soil layer ($\text{Mg/m}^3$, equivalent to $\text{g/cm}^3$; Fortran struct default: `1.3`), expressing the ratio of the mass of oven-dry solid particles to the total soil volume at or near field capacity:

$$\rho_b = \frac{M_s}{V_t}$$

where $\rho_b$ is `bd` ($\text{Mg/m}^3$), $M_s$ is the mass of oven-dry solid particles (Mg), and $V_t$ is total soil volume at or near field capacity ($\text{m}^3$). During initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L76-L77), values $\le 10^{-6}$ are reset to `1.3` and values $> 2.0$ are clamped to `2.0`.

SWAT+ uses layer bulk density $\rho_{b,l}$ to compute total porosity $\phi_l$ ([`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L94)), wilting-point water content $\theta_{\text{wp},l}$ ([`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L91)), and the concentration-to-mass conversion factor `conv_wt` ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L54)):

$$\phi_l = 1 - \frac{\rho_{b,l}}{2.65}, \qquad \theta_{\text{wp},l} = \frac{0.4 \cdot \text{clay}_l \cdot \rho_{b,l}}{100}, \qquad w_{\text{conv},l} = \frac{\rho_{b,l} \cdot \Delta z_l}{100}$$

where:

- $\phi_l$ is layer total porosity (`mm/mm`)
- $\rho_{b,l}$ is layer `bd` ($\text{Mg/m}^3$)
- $\theta_{\text{wp},l}$ is layer wilting-point volumetric water content (`mm/mm`)
- $\text{clay}_{l}$ is layer [clay](clay.md) percentage (%)
- $w_{\text{conv},l}$ is the concentration-to-mass conversion factor `conv_wt`
- $\Delta z_l$ is layer thickness (mm)
