---
description: Organic carbon in suspended and benthic sediment
---

# carbon

**Code reference:** `res_sed(ires)%carbon` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L102)).

Organic carbon content of suspended and benthic sediment (`%`; Fortran struct default: `0.`). SWAT+ uses `carbon` in [`res_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L57-L60) to compute the pesticide sorption partition coefficient and water-column dissolved fraction:

$$K_d = K_{\text{oc}} \cdot \frac{\text{OC}}{100}, \qquad f_d = \min\!\left(1,\; \frac{1}{1 + K_d \, r_{\text{sw}}}\right)$$

where $\text{OC}$ is `carbon` (%), $K_{\text{oc}}$ is the pesticide organic-carbon sorption coefficient, $K_d$ is the partition coefficient (`(mg/kg)/(mg/L)`), $r_{\text{sw}}$ is the suspended-sediment-to-water-volume ratio, and $f_d$ is the dissolved fraction in the water column (`fd1`) used for volatilization, settling, and diffusive exchange.
