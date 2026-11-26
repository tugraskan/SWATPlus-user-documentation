---
description: Plant population (read but not used in main 6f515368)
---

# plnt\_pop

**Code reference:** `pcomdb(icom)%pl(iplt)%pop` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L132), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L70)).

Real value (default `0.0`) intended to specify initial plant population. Although [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L326-L331) checks `pcom(j)%plcur(ipl)%pop_com`, that field is never populated from `pcomdb(icom)%pl(iplt)%pop`.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
