---
description: "Source object number of the POD (read but not used)"
---

# typ\_num (POD)

**Code reference:** `pou(ipou)%pod(ipod)%typ_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L95-L98)).

Position 5 of the POD record. The reader stores it, but no routine on dev uses this copy: withdrawals take the source object number from [typ_num](../point_of_diver.wro/typ_num.md) in `point_of_diver.wro` ([`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L27)). Enter the same source object number for consistency.
