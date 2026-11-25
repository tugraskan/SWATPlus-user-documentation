---
description: Organic carbon content of the soil layer
---

# carbon

**Code reference:** `soildb(isol)%ly(j)%cbn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L51)).

Organic carbon content of the soil layer (`%` by weight of fine earth `< 2` mm; Fortran struct default: `2.0`). During initialization in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L47), SWAT+ enforces a floor of `0.001`%:

$$\text{cbn}_l = \max(0.001,\, \text{carbon}_l)$$

where $\text{cbn}_{l}$ is the initialized layer organic carbon content (%) and $\text{carbon}_{l}$ is input `carbon` (%). SWAT+ then computes the initial total organic carbon mass $C_{\text{tot},l}$ (kg/ha) ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L118-L121)):

$$C_{\text{tot},l} = 10000 \cdot \Delta z_l \cdot \rho_{b,l} \cdot \frac{\text{cbn}_l}{100}$$

where $C_{\text{tot},l}$ is initial total organic carbon mass (kg/ha), $\Delta z_l$ is layer thickness (mm), $\rho_{b,l}$ is layer bulk density ($\text{Mg/m}^3$), and $\text{cbn}_{l}$ is layer organic carbon content (%). Layer `cbn` also drives denitrification ([`nut_nminrl.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nminrl.f90#L199)), dynamic phosphorus sorption ([`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L83)), and pesticide sorption ([`pest_lch.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_lch.f90#L44)):

$$K_d = K_{\text{oc}} \cdot \frac{\text{cbn}_l}{100}$$

where $K_d$ is the pesticide soil–water partition coefficient, $K_{\text{oc}}$ is the organic-carbon sorption coefficient, and $\text{cbn}_{l}$ is layer organic carbon content (%).
