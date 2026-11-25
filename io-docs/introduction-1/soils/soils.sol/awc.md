---
description: Available water capacity of the soil layer
---

# awc

**Code reference:** `soildb(isol)%ly(j)%awc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L49)).

Plant available water capacity of the soil layer (`mm H2O/mm soil`; Fortran struct default: `0.2`), defined as the difference between volumetric water content at field capacity ($-0.033\text{ MPa}$) and permanent wilting point ($-1.5\text{ MPa}$):

$$\text{AWC} = \theta_{\text{fc}} - \theta_{\text{wp}}$$

where $\text{AWC}$ is `awc` (`mm H2O/mm soil`), $\theta_{\text{fc}}$ is volumetric water content at field capacity (`mm/mm`), and $\theta_{\text{wp}}$ is volumetric water content at permanent wilting point (`mm/mm`). During initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L78-L79) (and [`soil_awc_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_awc_init.f90#L45-L46)), values $\le 10^{-6}$ are replaced with `0.005` and values $\ge 0.8$ are clamped to `0.8`.

SWAT+ computes field-capacity water content $\theta_{\text{fc},l}$ and plant-available water storage $\text{FC}_{l}$ (mm) in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L93-L100) and [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L149):

$$\theta_{\text{fc},l} = \theta_{\text{wp},l} + \text{AWC}_l, \qquad \text{FC}_l = \Delta z_l \left(\theta_{\text{fc},l} - \theta_{\text{wp},l}\right)$$

where:

- $\theta_{\text{fc},l}$ is layer field-capacity volumetric water content (`mm/mm`)
- $\theta_{\text{wp},l}$ is layer wilting-point volumetric water content (`mm/mm`)
- $\text{AWC}_{l}$ is layer `awc` (`mm H2O/mm soil`)
- $\text{FC}_{l}$ is plant-available water storage capacity (mm)
- $\Delta z_l$ is layer thickness (mm)

If $\theta_{\text{fc},l} \ge \phi_l$ (porosity), SWAT+ adjusts field-capacity and wilting-point water contents:

$$\theta_{\text{fc},l} = \phi_l - 0.05, \qquad \theta_{\text{wp},l} = \theta_{\text{fc},l} - \text{AWC}_l$$

where $\theta_{\text{fc},l}$ is adjusted field-capacity water content (`mm/mm`), $\phi_l$ is layer porosity (`mm/mm`), $\theta_{\text{wp},l}$ is adjusted wilting-point water content (`mm/mm`), and $\text{AWC}_{l}$ is layer `awc` (`mm H2O/mm soil`). If the resulting $\theta_{\text{wp},l} \le 0$, SWAT+ falls back to:

$$\theta_{\text{fc},l} = 0.75\,\phi_l, \qquad \theta_{\text{wp},l} = 0.25\,\phi_l$$

where $\theta_{\text{fc},l}$ is fallback field-capacity water content (`mm/mm`), $\theta_{\text{wp},l}$ is fallback wilting-point water content (`mm/mm`), and $\phi_l$ is layer porosity (`mm/mm`).
