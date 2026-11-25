---
description: Average depth of water at principal spillway
---

# dp\_ps

**Code reference:** `wet_hyddb(ires)%pdep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L85)).

The average depth of water at principal spillway (mm) is used during initialization ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L134), [weir height](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L147)) to calculate the principal storage volume (`wet_ob%pvol`, $\text{m}^3$) and default weir height ($h_{\text{weir}}$, m):

$$V_{\text{pvol}} = A_{\text{hru}} \cdot d_{\text{ps}} \cdot 10, \qquad h_{\text{weir}} = \frac{d_{\text{ps}}}{1000}$$

where $A_{\text{hru}}$ is HRU area (ha) and $d_{\text{ps}}$ is `dp_ps` (mm). If a weir height is specified in column [height](../../reservoirs/weir.res/vel_co.md) of [**weir.res**](../../reservoirs/weir.res/), that value overrides $h_{\text{weir}}$.

The principal volume of the wetland is used during daily wetland simulation in the equation that updates surface area as storage changes and for wetland release conditions and actions.
