---
description: "Name of the organic/mineral treatment record"
---

# org_min_name

**Code reference:** `wtp(iwtp)%conc(itrt)%org_min_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L136), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L51)).

25-character name resolved according to [org_min_typ](org_min_typ.md) to set `wtp(iwtp)%conc(itrt)%om_num` ([`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L61-L88)): matched against `om_treat_name` in [om_treat.wal](../om_treat.wal/README.md) (`"const"`), `dtbl_flo(:)%name` in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`"dtbl"`), or `recall_db(:)%org_min` (`"recall"`). Note that [`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L91-L99) also runs a secondary `dtbl_flo` lookup whenever `org_min_name /= "null"`.
