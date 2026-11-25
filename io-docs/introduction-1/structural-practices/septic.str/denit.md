---
description: Denitrification rate coefficient
---

# denit

**Code reference:** `sep(isep)%denitr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L45)).

The biozone denitrification rate coefficient, normalized by live biomass concentration in the biozone pore volume ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L266-L267)):

$$k_{\text{den}} = \max\!\left(0,\; K_{\text{den}} \cdot \frac{B \, A_{\text{hru}}}{V_{\text{bz}} \, \phi}\right), \qquad R_{\text{den}} = \text{NO}_3 \left(1 - e^{-k_{\text{den}}}\right)$$

where $k_{\text{den}}$ is the effective daily denitrification rate ($\text{day}^{-1}$), $K_{\text{den}}$ is `denit`, $B$ is live biomass (kg/ha), $A_{\text{hru}}$ is HRU area (ha), $V_{\text{bz}}$ is biozone volume ($\text{m}^3$), $\phi$ is porosity, $\text{NO}_{3}$ is biozone nitrate N (kg/ha), and $R_{\text{den}}$ is daily denitrified N (kg/ha).
