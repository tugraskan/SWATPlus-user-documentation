---
description: "Initial concentration of boron"
---

# c\_born

**Code reference:** `res_cs_data(ires)%c_born` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L52)).

Initial boron concentration in reservoir or wetland water (`g/m3`; Fortran struct default: `0.`). During initialization in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L157-L158) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L183-L187), SWAT+ converts concentration to initial mass:

$$M_{\text{cs}} = \frac{c}{1000} \cdot V$$

where $M_{\text{cs}}$ is initial boron mass (kg), $c$ is `c_born` (`g/m3`), and $V$ is initial water volume ($\text{m}^3$).
