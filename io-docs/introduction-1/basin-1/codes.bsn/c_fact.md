---
description: C-factor method selector (overwritten with 1 in main 6f515368)
---

# c\_fact

**Code reference:** `bsn_cc%cfac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L43), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Legacy integer selector between the original SWAT minimum C-factor equation (`0`) and the APEX residue/biomass cover C-factor equation (`1`; struct default `0`).

In SWAT+ main (`6f515368`), [`ero_cfactor.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ero_cfactor.f90#L51-L53) unconditionally overwrites `bsn_cc%cfac = 1` before evaluating `if (bsn_cc%cfac == 0)`. Consequently, the value entered in **codes.bsn** is ignored and SWAT+ always computes the APEX residue and biomass cover C-factor ([`ero_cfactor.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ero_cfactor.f90#L68-L77)).
