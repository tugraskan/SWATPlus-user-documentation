---
description: Nitrification rate coefficient
---

# nit

**Code reference:** `sep(isep)%nitr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L44)).

The biozone nitrification rate coefficient, normalized by live biomass concentration in the biozone pore volume ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L254-L255)):

$$k_{\text{nit}} = \max\!\left(0,\; K_{\text{nit}} \cdot \frac{B \, A_{\text{hru}}}{V_{\text{bz}} \, \phi}\right), \qquad R_{\text{nit}} = \text{NH}_4 \left(1 - e^{-k_{\text{nit}}}\right)$$

where $k_{\text{nit}}$ is the effective daily nitrification rate ($\text{day}^{-1}$), $K_{\text{nit}}$ is `nit`, $B$ is live biomass (kg/ha), $A_{\text{hru}}$ is HRU area (ha), $V_{\text{bz}}$ is biozone volume ($\text{m}^3$), $\phi$ is porosity, $\text{NH}_{4}$ is biozone ammonium N (kg/ha), and $R_{\text{nit}}$ is daily nitrified N (kg/ha).
