---
description: Object type
---

# obj

**Code reference:** `dtbl_lum(i)%act(iac)%ob` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L18)).

Object-type label for the action. Most actions act on an HRU whatever is entered, and `chan_change` acts on the current channel. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L454-L456) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1256-L1260)

`irrigate` uses it to choose the water source whose storage is reduced: `aqu`, `cha` or `sdc`, or `res`, with the source number in [obj_num](obj_num-1.md). Any other label removes water from no source. If the demand exceeds the source storage, nothing is applied. [`actions.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/actions.f90#L263-L320)
