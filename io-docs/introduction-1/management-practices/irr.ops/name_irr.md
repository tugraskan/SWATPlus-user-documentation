---
description: Irrigation operation name
---

# name (irr.ops)

**Code reference:** `irrop_db(irr_op)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L6), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L48)).

The name of the irrigation operation is a primary key matched when irrigation operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L96-L97)) or [**lum.dtl**](../../decision-tables/lum.dtl/README.md) ([`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/dtbl_lum_read.f90#L139-L156)). All names in **irr.ops** must be unique.

| Name            | Description       |
| --------------- | ----------------- |
| sprinkler\_med  | Medium sprinkler  |
| sprinkler\_high | High sprinkler    |
| drip            | Drip irrigation   |
| furrow          | Furrow irrigation |
