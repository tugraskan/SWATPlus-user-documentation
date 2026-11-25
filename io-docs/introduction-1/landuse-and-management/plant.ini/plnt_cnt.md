---
description: Number of plants in the community
---

# plnt\_cnt

**Code reference:** `pcomdb(icom)%plants_com` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L139), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L62)).

Integer count (struct default `1`) of plant entries belonging to this plant community. It controls allocation and reading of the subsequent plant rows in [`readpcom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L65-L67) and sets `pcom(j)%npl` during HRU initialization in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L87). This number must match the number of plant lines listed beneath the community header.
