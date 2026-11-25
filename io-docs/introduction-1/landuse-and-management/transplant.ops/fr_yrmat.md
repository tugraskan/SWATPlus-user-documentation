---
description: "Fraction of years to maturity completed"
---

# fr\_yrmat

**Code reference:** `transpl(ic)%fr_yrmat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L150), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L43)).

Dimensionless fraction of years to maturity already completed at transplanting (struct default `0.05`; note the inline Fortran comment says `years`, but the code uses it as a fraction). In [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L25-L34), SWAT+ adds it to the perennial lifetime heat-unit fraction (`phuacc_p`) and computes the integer plant growth year:

$$\text{curyr}_{\text{mat}} = \max\!\big(1,\; \lfloor f_{\text{mat}} \cdot \text{mat}_{\text{yrs}} \rfloor\big)$$

where $f_{\text{mat}}$ is `fr_yrmat` and $\text{mat}_{\text{yrs}}$ is the species' years to maturity (`pldb%mat_yrs`).
