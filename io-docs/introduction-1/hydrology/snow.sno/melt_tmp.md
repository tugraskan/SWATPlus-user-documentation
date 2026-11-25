---
description: Snow melt base temperature
---

# melt\_tmp

**Code reference:** `snodb(isno)%melttmp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L75)).

Base snowmelt temperature $T_b$ in °C. The built-in snow record uses 0.5 °C. Snowmelt is considered when daily maximum air temperature $T_{\max}$ exceeds $T_b$ and the HRU has snow. [`sq_snom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_snom.f90#L63-L80) multiplies $[(T_{\mathrm{pack}}+T_{\max})/2-T_b]$ by the seasonal melt factor and snow-covered fraction, then bounds melt between zero and the remaining snow water equivalent.
