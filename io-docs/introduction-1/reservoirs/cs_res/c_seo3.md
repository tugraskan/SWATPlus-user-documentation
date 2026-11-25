---
description: "Initial concentration of selenite"
---

# c\_seo3

**Code reference:** `res_cs_data(ires)%c_seo3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L51)).

Initial selenite concentration in reservoir or wetland water (`g/m3`; Fortran struct default: `0.`). During initialization in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L154-L155) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L182-L186), SWAT+ converts concentration to initial mass:

$$M_{\text{cs}} = \frac{c}{1000} \cdot V$$

where $M_{\text{cs}}$ is initial selenite mass (kg), $c$ is `c_seo3` (`g/m3`), and $V$ is initial water volume ($\text{m}^3$).
