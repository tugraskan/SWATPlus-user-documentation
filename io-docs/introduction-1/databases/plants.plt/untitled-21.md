---
description: Plant/landcover type
---

# plnt\_typ

**Code reference:** `pldb(ic)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L27)).

SWAT+ main (`6f515368`) compares this text literally, so use one of the values below. `warm_annual_tuber` and `cold_annual_tuber` follow the annual rules, and their end-of-season root fraction is forced to 0.7 ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L34-L36)).

| Option       | Description         |
| ------------ | ------------------- |
| perennial    | Perennial plants    |
| warm\_annual | Warm-season annuals |
| cold\_annual | Cold-season annuals |
| warm\_annual\_tuber | Warm-season annuals harvested below ground |
| cold\_annual\_tuber | Cold-season annuals harvested below ground |

Fall-planted land covers will go dormant when daylength is less than the threshold daylength.
