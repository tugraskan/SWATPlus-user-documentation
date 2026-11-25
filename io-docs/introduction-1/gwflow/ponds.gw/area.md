---
description: "Pond surface area, m²"
---

# area

**Code reference:** `gw_pond_info(i)%area` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L409), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1949)).

Surface area of the pond, in m². Rain and evaporation are applied over it ([`gwflow_pond.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pond.f90#L228-L234)):

$$V_{\text{rain}} = \frac{P}{1000} \, A, \qquad V_{\text{evap}} = c \, \frac{E_{p}}{1000} \, A$$

where $P$ and $E_{p}$ are the day's precipitation and PET (mm) and $c$ is [evap_co](evap_co.md). Seepage uses the connection areas in `pond_cell.gw`, not this area.
