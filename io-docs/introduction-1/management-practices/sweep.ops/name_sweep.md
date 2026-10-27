---
description: Street sweeping operation name
---

# name (sweep.ops)

**Code reference:** `sweepop_db(isweepop)%name`

**Declared type:** `streetsweep_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_sweepops.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L135)).

The name of the street sweeping operation is a primary key referenced when street sweeping operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **sweep.ops** file must be unique.

| Name      | Description              |
| --------- | ------------------------ |
| high\_eff | High-efficiency sweeping |
