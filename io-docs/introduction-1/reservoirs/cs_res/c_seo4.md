---
description: "Initial concentration of selenate"
---

# c\_seo4

**Code reference:** `res_cs_data(ires)%c_seo4` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L50)).

Initial selenate concentration in reservoir or wetland water (`g/m3`; Fortran struct default: `0.`). During initialization in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L151-L152) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L181-L185), SWAT+ converts concentration to initial mass:

$$M_{\text{cs}} = \frac{c}{1000} \cdot V$$

where $M_{\text{cs}}$ is initial selenate mass (kg), $c$ is `c_seo4` (`g/m3`), and $V$ is initial water volume ($\text{m}^3$).
