---
description: "Name identifying this component-value record"
---

# om_osrc_name

**Code reference:** `om_osrc_name(iom_osrc)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L219), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L43)).

16-character name identifying an outside-source organic/mineral record. Matched against `org_min_name` in [outside_src.wal](../outside_src.wal/README.md) when `org_min_typ == "const"` ([`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L61)).
