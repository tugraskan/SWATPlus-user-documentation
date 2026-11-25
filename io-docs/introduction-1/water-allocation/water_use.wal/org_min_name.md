---
description: "Name of the organic/mineral water-use record"
---

# org_min_name

**Code reference:** `wuse(iwuse)%conc(lev)%org_min_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L136), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L49)).

25-character name resolved according to [org_min_typ](org_min_typ.md) to set `wuse(iwuse)%conc(lev)%om_num` ([`water_use_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L58-L85)): matched against `om_use_name` in [om_use.wal](../om_use.wal/README.md) (`"const"`), `dtbl_flo(:)%name` in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`"dtbl"`), or `recall_db(:)%org_min` (`"recall"`).
