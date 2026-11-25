---
description: Height of weir above reservoir bottom
---

# height

**Code reference:** `res_weir(ires)%h` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L142)).

Weir-crest height above the impoundment bottom (`m`; Fortran struct default: `0.0`). In SWAT+ main (`6f515368`), `res_weir%h` is read during wetland initialization in [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L139-L142), setting `wet_ob%weir_hgt` and overriding wetland principal-spillway volume:

$$V_{\text{pvol}} = 10000 \cdot A_{\text{hru}} \cdot h$$

where $A_{\text{hru}}$ is HRU area (ha) and $h$ is `height` (m). For reservoirs, `res_weir%h` is not read directly; instead `res_ob%weir_hgt` is initialized in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L35) and can be updated by decision-table actions ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L952)) or, for wetlands, scheduled operations ([`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L511)):

$$h_{\text{weir}} = \frac{V_{\text{pvol}}}{10000 \, A_{\text{psa}}}$$

where $h_{\text{weir}}$ is weir-crest height (m), $V_{\text{pvol}}$ is principal spillway volume ($\text{m}^3$), and $A_{\text{psa}}$ is principal spillway surface area (ha). Release head is computed in [`res_weir_release.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_weir_release.f90#L51) and [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L194):

$$h_{\text{above}} = \max(0,\, d - h_{\text{weir}})$$

where $h_{\text{above}}$ is water depth above the weir crest (m), $d$ is water depth (m), and $h_{\text{weir}}$ is weir-crest height (m).
