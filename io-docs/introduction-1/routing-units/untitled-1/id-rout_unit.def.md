---
description: Unique ID of the Routing Unit
---

# id (rout\_unit.def)

**Code reference:** `numb` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L29), [first read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L118), [second read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L126)).

SWAT+ main (6f515368) reads `numb` sequentially for each Routing Unit (`do iru = 1, sp_ob%ru`) but does not use it to select or store the definition. Definitions are associated with Routing Units by row position, so keep the rows in the same order as the Routing Units.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
