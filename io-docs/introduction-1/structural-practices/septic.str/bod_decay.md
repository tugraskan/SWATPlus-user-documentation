---
description: BOD decay rate coefficient
---

# bod\_decay

**Code reference:** `sep(isep)%bod_dc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L33)).

Biozone BOD decay rate coefficient ($\text{m}^3/\text{day}$), normalized by live biomass concentration in the biozone pore volume (daily rate capped at `4.0` $\text{day}^{-1}$ in [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L242-L244)):

$$k_{\text{bod}} = \min\!\left(\max\!\left(0,\; K_{\text{bod}} \cdot \frac{B \, A_{\text{hru}}}{V_{\text{bz}} \, \phi}\right),\; 4\right), \qquad \Delta \text{BOD} = \text{BOD}_i \left(1 - e^{-k_{\text{bod}}}\right)$$

where $k_{\text{bod}}$ is the effective daily decay rate ($\text{day}^{-1}$), $K_{\text{bod}}$ is `bod_decay`, $B$ is live biomass (kg/ha), $A_{\text{hru}}$ is HRU area (ha), $V_{\text{bz}}$ is biozone volume ($\text{m}^3$), $\phi$ is porosity, and $\text{BOD}_{i}$ is initial daily BOD concentration.
