---
description: Width of weir
---

# width

**Code reference:** `res_weir(ires)%w` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L141)).

Weir-crest width (`m`; Fortran struct default: `2.5`). For wetlands linked to a weir record, `width` is copied to `wet_ob%weir_wid` in [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L140). SWAT+ multiplies `width` directly in the weir-release equation in [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L199-L208) and [`res_weir_release.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_weir_release.f90#L84-L104):

$$Q = 0.45 \, A \cdot c \cdot w \cdot h_{\text{above}}^{k}$$

where $A$ is surface area (ha), $c$ is [linear\_c](disch_co.md), $w$ is `width` (m), $k$ is [exp\_k](energy_co.md), and $h_{\text{above}}$ is water depth above the weir crest (m).
