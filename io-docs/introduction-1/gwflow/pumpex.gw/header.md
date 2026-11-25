---
description: "Label of the pumping period"
---

# header

**Code reference:** `header` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L45), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L983)).

Text label at the start of each line (for example a well name). It is read and discarded; despite its Fortran name `header`, it is a value on every data line ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L983-L984)). It cannot contain spaces. *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
