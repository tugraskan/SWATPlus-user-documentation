---
description: Minimum snow water content that corresponds to 100% snow cover
---

# snow\_h2o

**Code reference:** `snodb(isno)%covmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L79)).

Snow water equivalent $W_{\max}$ in mm at which an HRU becomes fully snow covered. The built-in snow record uses 25 mm. If snow water equivalent $W$ is below this threshold, [`sq_snom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_snom.f90#L69-L76) multiplies melt by the fractional coverage:

$$f_{\mathrm{cov}} = \frac{r}{r + \exp(a - br)}, \qquad r = \frac{W}{W_{\max}}$$

where:

- $f_{\mathrm{cov}}$ is the fractional snow cover (dimensionless),
- $r$ is the relative snow water equivalent (dimensionless),
- $W$ is the snow water equivalent (mm),
- $W_{\max}$ is `snow_h2o` (mm), and
- $a$ and $b$ are the shape coefficients calibrated by [cov50](cov50.md) (dimensionless).

At or above the threshold, the coverage is 1.
