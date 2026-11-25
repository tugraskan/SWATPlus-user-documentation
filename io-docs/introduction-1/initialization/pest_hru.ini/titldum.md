---
description: Leading pesticide label token
---

# titldum

**Code reference:** `titldum` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L9)).

Leading character token on each pesticide row in `pest_hru.ini` ([`pest_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L59)). SWAT+ parses this token and discards it without name matching; rows must appear in the same order as pesticides in [**constituents.cs**](../../constituents/constituents.cs.md).
