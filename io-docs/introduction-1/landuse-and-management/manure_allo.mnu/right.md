---
description: "Manure right designation, either sr for senior or jr for junior right (read but not used in main 6f515368)"
---

# right

**Code reference:** `mallo(imro)%trn(i)%right` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L47), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L95)).

Character string (`len=2`, default `""`) intended to designate senior (`sr`) or junior (`jr`) manure priority rights.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
