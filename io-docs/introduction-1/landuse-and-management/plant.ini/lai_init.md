---
description: Initial Leaf Area Index
---

# lai\_init

**Code reference:** `pcomdb(icom)%pl(iplt)%lai` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L129), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L69)).

Initial Leaf Area Index (`m^2/m^2`, default `0.0`, range `0.0–8.0`) at the start of the simulation. In [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_init.f90#L304-L308), SWAT+ assigns `pcom(j)%plg(ipl)%lai` to `lai_init` when [lc\_status](lc_status.md) is `"y"`, and overrides it to `0.0` when `lc_status` is `"n"`.
