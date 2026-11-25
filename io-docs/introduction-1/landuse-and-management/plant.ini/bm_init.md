---
description: Initial plant biomass
---

# bm\_init

**Code reference:** `pcomdb(icom)%pl(iplt)%bioms` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L130), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L69)).

Initial dry plant biomass (`kg/ha`, default `0.0`, historical range `0.0–1000.0`). In [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L308), SWAT+ assigns this value directly to `pl_mass(j)%tot(ipl)%m` and computes initial total plant N and P mass from the maturity-dependent plant N and P fractions ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L317-L324)). When [lc\_status](lc_status.md) is `"y"`, total biomass is partitioned into root, seed, leaf, and stem pools ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L336-L353)).
