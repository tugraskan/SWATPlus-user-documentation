---
description: "Fraction of incoming shortwave radiation blocked by shading"
---

# value

**Code reference:** `shf_db(idlsu)%value` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1201)).

The solar-radiation term in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L387) uses $1 - \text{ssff}$, so `0` means no shading and `1` means full shading. When active (`w_temp(0)%sf_on == 1`), the first row matching day of year and channel in [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L371-L381) is used; day `366` uses `0.5`. Because `w_temp(0)%sf_on` remains `0` at `6f515368`, source reading indicates `shf_db%value` is not reached on this path.
