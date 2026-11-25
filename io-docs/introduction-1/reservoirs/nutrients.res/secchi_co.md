---
description: Annual loss-rate coefficient for soluble phosphorus
---

# secchi\_co

**Code reference:** `res_nut(ires)%psolr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L118)).

Despite the legacy input label, this field is the annual loss-rate coefficient for soluble phosphorus (`1/year`; historical table default: `1.0`, range `0.50–2.0`; Fortran struct default: `1.`), not a water-clarity coefficient. SWAT+ divides the input by `365` in [`res_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_nut.f90#L70) and applies it in [`res_nutrient.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L87-L93):

$$f_{\text{solP}} = \min\!\left(1,\; \max\!\left(0,\; (C_{\text{solP}} - C_{P,\min}) \, \frac{k_{\text{solP}}}{365} \, \theta_P^{(T - 20)}\right)\right), \qquad M_{\text{solP,new}} = M_{\text{solP}} \,(1 - f_{\text{solP}} \, f_{\text{sol}})$$

where:

- $f_{\text{solP}}$ is the daily soluble phosphorus loss fraction (dimensionless)
- $C_{\text{solP}}$ is soluble phosphorus concentration (ppm)
- $C_{P,\min}$ is [p\_min\_stl](p_min_stl.md) (ppm)
- $k_{\text{solP}}$ is `secchi_co` (`1/year`)
- $\theta_P$ is [theta\_p](theta_p.md) (dimensionless)
- $T$ is daily average air temperature (`deg C`)
- $M_{\text{solP}}$ and $M_{\text{solP,new}}$ are the pre- and post-settling soluble phosphorus masses (kg)
- $f_{\text{sol}}$ is the soluble settling fraction (`0.2`, initialized in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L146) and [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L103))
