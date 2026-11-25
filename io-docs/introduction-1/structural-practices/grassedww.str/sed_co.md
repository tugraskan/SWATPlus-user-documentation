---
description: Sediment transport coefficient
---

# sed\_co

**Code reference:** `grwaterway_db(igrwwop)%grwat_spcon` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L51)).

User-defined linear coefficient for sediment transport capacity in the grassed waterway (dimensionless; range `0.0–1.0`). In [`smp_grass_wway.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/smp_grass_wway.f90#L158), maximum sediment concentration $C_{\text{ch}}$ ($\text{Mg/m}^3$) is computed as:

$$C_{\text{ch}} = c_{\text{sp}} \cdot v_c^{1.5}$$

where $c_{\text{sp}}$ is `sed_co` and $v_c$ is flow velocity in the waterway (m/s). At runtime ([`structure_set_parms.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L91)), if `sed_co <= 0`, SWAT+ resets it to `0.005`.
