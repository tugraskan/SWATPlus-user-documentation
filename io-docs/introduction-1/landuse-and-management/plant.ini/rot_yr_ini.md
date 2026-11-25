---
description: Initial rotation year
---

# rot\_yr\_ini

**Code reference:** `pcomdb(icom)%rot_yr_ini` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L140), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L62)).

Integer initial rotation year (struct default `1`) for the plant community. During initialization in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L286), SWAT+ assigns `pcom(j)%rot_yr = pcomdb(icom)%rot_yr_ini` for decision-table scheduling—including selecting the starting crop on `pl_hv_summer2` generic rotation tables ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L466-L468)).

For date-scheduled `management.sch` sequences, `rot_yr_ini` also determines the starting operation index `sched(isched)%first_op` by counting `skip` commands and backward Julian-day wraps until reaching `rot_yr_ini` ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L262-L282)).
