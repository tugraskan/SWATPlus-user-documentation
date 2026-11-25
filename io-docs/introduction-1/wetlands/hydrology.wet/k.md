---
description: Hydraulic conductivity of the wetland bottom
---

# k

**Code reference:** `wet_hyddb(ires)%k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L88)).

Hydraulic conductivity of the wetland bottom (mm/hr), copied to `hru%wet_hc` ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L131)) to compute daily wetland seepage in [`wetland_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L105):

$$Q_{\text{seep}} = \min\!\left(V,\; 240 \cdot K_{\text{wet}} \cdot A_{\text{wet}}\right)$$

where $Q_{\text{seep}}$ is daily seepage volume ($\text{m}^3$, computed as $K_{\text{wet}} \times 24 \times A_{\text{wet}} \times 10$), $V$ is current wetland storage ($\text{m}^3$), $K_{\text{wet}}$ is `k` (mm/hr), and $A_{\text{wet}}$ is wetland surface area (ha). When `gwflow` is active, `k` is converted to m/day via $K_{\text{wet}} \cdot 24 / 1000$ ([`gwflow_wetland.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_wetland.f90#L65)).

In SWAT+ main (6f515368), a nonpositive input is replaced by `soil(ires)%phys(1)%k` during reading ([`wet_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_read_hyd.f90#L63)). Here `ires` is the wetland-hydrology reader index, not necessarily an individually matched HRU.
