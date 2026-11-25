---
description: "POR receiving object number"
---

# num (POR)

**Code reference:** `pou(ipou)%por(ipor)%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L39), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104-L105)).

1-based index of the receiving object in the array selected by [typ (POR)](por_typ.md) (default: `0`). In [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104-L105), both position 2 and position 5 are read into `pou(ipou)%por(ipor)%num`, so position 5 overwrites position 2. Used as the target object index `j` in [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L18).
