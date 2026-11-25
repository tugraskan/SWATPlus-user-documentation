---
description: Snowpack temperature lag factor
---

# tmp\_lag

**Code reference:** `snodb(isno)%timp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L78)).

Dimensionless coefficient $\lambda$ for estimating snowpack temperature. The built-in snow record uses 0.8. [`sq_snom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_snom.f90#L45-L52) resets its snowpack temperature variable to zero on each call, so the implemented estimate is:

$$T_{\mathrm{pack}} = \lambda T_{\mathrm{air}}$$

where $T_{\mathrm{pack}}$ is the estimated snowpack temperature (°C), $\lambda$ is `tmp_lag` (dimensionless), and $T_{\mathrm{air}}$ is the daily mean air temperature (°C). The previous day's snowpack temperature does not carry over in this routine. This is flagged as a suspected model issue.
