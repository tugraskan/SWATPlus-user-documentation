---
description: "Name of the organic/mineral source record"
---

# org_min_name

**Code reference:** `osrc(isrc)%conc(lev)%org_min_name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L136), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L48)).

25-character name resolved according to [org_min_typ](org_min_typ.md) to set `osrc(isrc)%conc(lev)%om_num` ([`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L57-L84)): matched against `om_osrc_name` in [om_osrc.wal](../om_osrc.wal/README.md) (`"const"`), `dtbl_flo(:)%name` in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`"dtbl"`), or `recall_db(:)%org_min` (`"recall"`).
