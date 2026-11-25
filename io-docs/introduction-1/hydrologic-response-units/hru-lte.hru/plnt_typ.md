---
description: Plant type
---

# plnt\_typ

**Code reference:** `hlt_db(i)%plant` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L41)).

Plant name, a foreign key referencing the `name` column in [**plants.plt**](../../databases/plants.plt/). The plant record supplies base and optimum temperature, radiation-use efficiency and maximum leaf area index for growth. SWAT+ writes a warning if the name is not found ([`hru_lte_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_read.f90#L157-L165)).
