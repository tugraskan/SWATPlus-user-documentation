---
description: Irrigation source
---

# irr\_src

**Code reference:** `hlt_db(i)%irrsrc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L45)).

Source of irrigation water. It matters only when irrigation is active; see [irr\_flag](irr_flag.md).

* `outside_bsn`: outside the basin, not limited by aquifer storage
* `shal_aqu`: shallow aquifer, limited to its storage ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L248-L254))
* `deep_aqu`: deep aquifer, limited to its storage ([`hru_lte_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L257-L263))

Any other value behaves like `outside_bsn`.
