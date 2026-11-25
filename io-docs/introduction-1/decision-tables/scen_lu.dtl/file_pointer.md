---
description: "Selector or referenced record name"
---

# file_pointer

**Code reference:** `dtbl_scen(i)%act(iac)%file_pointer` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L25)).

For `lu_change`, enter a record name from [landuse.lum](../../landuse-and-management/landuse.lum/). For `snow_change`, enter a record name from [snow.sno](../../hydrology/snow.sno/). For `hru_fr_update`, enter the filename of the updated routing-unit element table. [`dtbl_scen_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_scen_read.f90#L78-L97) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L1000-L1006)
