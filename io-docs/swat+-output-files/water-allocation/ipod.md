---
description: "Point-of-diversion position within its place of use"
---

# ipod

**Code reference:** POD loop index in [daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L49), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L85-L105), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L143-L163), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L198-L218).

The position of the POD in the POU's POD list in [place_of_use.wro](../../introduction-1/water-allocation/place_of_use.wro/README.md): `1` for the first POD listed under the POU, `2` for the second, and so on. It is not the POD number from `point_of_diver.wro`. The row does not say which POU it belongs to; rows follow the POU order of the MET file.

[Back to the allocation-transactions schema](allocation-transactions.md).
