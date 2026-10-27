---
description: Plant/landcover type
---

# plnt\_typ

**Code reference:** `pldb(ic)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L32)).

| Option       | Description         |
| ------------ | ------------------- |
| perennial    | Perennial plants    |
| warm\_annual | Warm-season annuals |
| cold\_annual | Cold-season annuals |

Fall-planted land covers will go dormant when daylength is less than the threshold daylength.
