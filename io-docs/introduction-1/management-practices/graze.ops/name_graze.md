---
description: Grazing operation name
---

# name (graze.ops)

**Code reference:** `grazeop_db(igrazop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L123), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_grazeops.f90#L49)).

The name of the grazing operation is a primary key matched when grazing operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L160-L161)) or [**lum.dtl**](../../decision-tables/lum.dtl/README.md) ([`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L259-L260)). All names in **graze.ops** must be unique.

| Name         | Description              |
| ------------ | ------------------------ |
| dairy\_high  | High-productivity dairy  |
| dairy\_low   | Low-productivity dairy   |
| beef\_high   | High-productivity beef   |
| beef\_low    | Low-productivity beef    |
| swine\_high  | High-productivity swine  |
| swine\_low   | Low-productivity swine   |
| sheep\_high  | High-productivity sheep  |
| sheep\_low   | Low-productivity sheep   |
| goats\_high  | High-productivity goats  |
| goats\_low   | Low-productivity goats   |
| horses\_high | High-productivity horses |
| horses\_low  | Low-productivity horses  |
