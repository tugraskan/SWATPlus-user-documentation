---
description: "Organic nitrogen concentration (read but not used in main 6f515368)"
---

# orgn

**Code reference:** `pudl_db(ic)%orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_puddle.f90#L42)).

Organic nitrogen concentration (`ppm`, struct default `0.0`) intended for standing paddy water after puddling. Keep the column in each row so subsequent fields remain aligned.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
