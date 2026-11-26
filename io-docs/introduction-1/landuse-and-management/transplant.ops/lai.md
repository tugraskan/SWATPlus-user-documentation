---
description: "Leaf area index (read but not used in main 6f515368)"
---

# lai

**Code reference:** `transpl(ic)%lai` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L147), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_transplant_read.f90#L43)).

Initial leaf area index (`m^2/m^2`, struct default `0.0`). The assignment to `pcom(j)%plg(ipl)%lai` in [`mgt_transplant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_transplant.f90#L31) is commented out.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
