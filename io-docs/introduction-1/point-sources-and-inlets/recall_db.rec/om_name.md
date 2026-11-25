---
description: Organic/mineral constituent name matched in water-allocation concentration definitions
---

# om\_name

**Code reference:** `recall_db(i)%org_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_module.f90#L7), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L49)).

Organic/mineral constituent record name (`character(len=25)`, not a data filename) matched against `org_min_name` in water-allocation concentration definitions for outside sources ([`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L79)), water treatment ([`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L83)), and water use ([`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L80)).
