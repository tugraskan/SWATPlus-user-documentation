---
description: "Place-of-use number in the MET files"
---

# ipou

**Code reference:** POU loop index `ipou` in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L453-L455), printed by [daily](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L49), [monthly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L85-L105), [yearly](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L143-L163), [average annual](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L198-L218).

The POU number: the record number given in the first column of [place_of_use.wro](../../introduction-1/water-allocation/place_of_use.wro/README.md). It appears at position 5 in MET TXT rows. MET CSV rows print it twice, at positions 4 and 6, with the year between them.

POD and POR rows do not carry this number; see the ordering note in the [schema](allocation-transactions.md).

[Back to the allocation-transactions schema](allocation-transactions.md).
