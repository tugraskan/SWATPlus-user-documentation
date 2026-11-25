---
description: "Evaporation coefficient"
---

# evap_co

**Code reference:** `gw_pond_info(i)%evap_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L411), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1955)).

Factor applied to PET to get pond evaporation ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L233-L238)):

$$V_{\text{evap}} = c \, \frac{E_{p}}{1000} \, A$$

where $V_{\text{evap}}$ is daily pond evaporation volume ($\text{m}^3$), $c$ is `evap_co` (dimensionless), $E_{p}$ is daily PET (mm), and $A$ is pond [area](area.md) ($\text{m}^2$).

Evaporation is limited to the water in the pond.
