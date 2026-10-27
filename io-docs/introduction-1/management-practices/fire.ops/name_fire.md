---
description: Fire operation name
---

# name (fire.ops)

**Code reference:** `fire_db(ifireop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L41)).

The name of the fire operation is a primary key referenced when burning/fire operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **fire.ops** file must be unique.

| Name          | Description         |
| ------------- | ------------------- |
| grass         | Grass fire          |
| tree\_intense | Intense forest fire |
| tree\_low     | Low forest fire     |
