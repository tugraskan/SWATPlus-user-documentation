---
description: Fraction of snow_h2o at which snow cover is 50%
---

# cov50

**Code reference:** `snodb(isno)%cov50` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L80)).

Fraction of [snow_h2o](snow_h2o.md) at which the HRU is 50% snow covered. The built-in snow record uses 0.5. The model fits the coverage curve through $(\text{cov50},0.5)$ and $(0.95,0.95)$, using snow water equivalent fractions as the first coordinate. [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L48-L52)

The fit in [`ascrv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ascrv.f90#L31-L33) takes the logarithm of the input and divides by $0.95-\text{cov50}$. Values of 0 and 0.95 therefore make the fit singular, even though they fall within the historical table range.
