---
description: Concentration of total P in suspended solid load from impervious areas
---

# conc\_totp

**Code reference:** `urbdb(iu)%tpconc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L14)).

Concentration in suspended solids from impervious areas, in mg per kg of solids. Total P load is `conc_totp × solids / 1e6` (kg/ha); 75% goes to organic P and 25% to soluble P ([`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L148-L172)). It is used only by the build-up/wash-off method ([`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L122-L128)).
