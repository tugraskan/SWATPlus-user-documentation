---
description: Land cover status at start of simulation
---

# lc\_status

**Code reference:** `pcomdb(icom)%pl(iplt)%igro` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L126), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L68)).

Single-character flag (`len=1`, struct default `"y"`) indicating whether the plant is actively growing at simulation start. SWAT+ copies it to `pcom(j)%plcur(ipl)%gro` ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L128)). When set to `"y"`, SWAT+ initializes LAI ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L302-L306)), perennial lifetime heat-unit fraction `phuacc_p`, and root/seed/leaf/stem biomass partitioning ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L336-L353)); when `"n"`, initial LAI is set to `0.0`.

| Option | Description       |
| ------ | ----------------- |
| `n`    | Plant not growing |
| `y`    | Plant growing     |
