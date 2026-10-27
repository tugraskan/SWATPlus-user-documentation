---
description: Master list of recall inputs
---

# recall.rec

This file lists the recall inputs used in a simulation. The referenced data records are supplied separately.

| Field | Description | Type |
| --- | --- | --- |
| [num](num.md)\* | Recall input record number | integer |
| [name](name.md) | User label for the recall input; read but not used in SWAT+ main (6f515368) | string |
| [type](type.md)\* | Recall type: 0=subdaily, 1=daily, 2=monthly, 3=yearly, 4=EXCO/average-annual constant | integer |
| [fname](fname.md)\* | Time-series filename for types 0-3; EXCO database name for type 4 | string |

\* Input-file labels marked with an asterisk have different Fortran names: `num` → `k`; `type` → `recall(i)%typ`; `fname` → `recall(i)%filename`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/recall_read.f90#L80).
