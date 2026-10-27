---
description: "Fraction of incoming shortwave radiation blocked by shading"
---

# value

**Code reference:** `shf_db(idlsu)%value` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L1198)).

The solar-radiation term uses 1 - value, so zero means no shading and one means full shading. The first row matching day of year and channel is used; day 366 uses 0.5 in that branch. No interpolation or automatic replacement for an unmatched ordinary day is established by this lookup.
