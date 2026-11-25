---
description: On/off flag for vegetative filter strip
---

# flag

**Code reference:** `filtstrip_db(ifiltop)%vfsi` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L32)).

Enter 0 to deactivate the filter strip or any positive value to activate it. The value is copied directly to the HRU and checked at runtime ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L608)): when `vfsi > 0`, the filter-strip removal calculations are applied to the HRU's surface loads.
