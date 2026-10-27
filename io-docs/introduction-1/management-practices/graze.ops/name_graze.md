---
description: Grazing operation name
---

# name (graze.ops)

**Code reference:** `grazeop_db(igrazop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L123)).

The name of the grazing operation is a primary key referenced when grazing operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **graze.ops** file must be unique.

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
