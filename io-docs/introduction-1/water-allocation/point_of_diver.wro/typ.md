---
description: "Type of POD source object"
---

# typ

**Code reference:** `pod(ipod)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L104), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L212,L220)).

10-character source object type code (default: `""`). At read time ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L227-L248)), `osrc`, `res`, `cha`, `hru`, `aqu`, `can`, and `wtow` attach `wallo_pod` to the corresponding source object. During simulation ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L120), [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L43-L129)), withdrawals dispatch on `unl` (unlimited), `osrc`, `wtow`, `cha`, `can`, `res`, `aqu`, and `gwf` (empty branch in main `6f515368` and dev `aa4179fe`).
