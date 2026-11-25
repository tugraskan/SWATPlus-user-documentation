---
description: Exponential coefficient for calculation of field capacity in the biozone
---

# fc\_exp

**Code reference:** `sep(isep)%fc2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L37)).

Exponential coefficient used with [`fc_lin`](fc_lin.md) to update biozone field capacity ($FC$, mm) in response to daily bacterial biomass growth $\Delta B$ ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L192)):

$$FC_{\text{new}} = FC + c_1 \, (UL - FC)^{c_2} \, \frac{\Delta B}{10 \, \rho_b}$$

where $c_1$ is `fc_lin`, $c_2$ is `fc_exp`, $UL$ is saturated water capacity of the biozone (mm), $\Delta B$ is daily biomass change (kg/ha), and $\rho_b$ is [`bm_dens`](bm_dens.md) ($\text{kg/m}^3$).
