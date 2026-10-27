---
description: ​Irrigation operation name
---

# name (irr.ops)

**Code reference:** `irrop_db(irr_op)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L6)).

The name of the irrigation operation is a primary key referenced when irrigation operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **irr.ops** file must be unique.

| Name            | Description       |
| --------------- | ----------------- |
| sprinkler\_med  | Medium sprinkler  |
| sprinkler\_high | High sprinkler    |
| drip            | Drip irrigation   |
| furrow          | Furrow irrigation |
