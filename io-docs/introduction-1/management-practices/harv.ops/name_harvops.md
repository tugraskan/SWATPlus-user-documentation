---
description: Harvest operation name
---

# name (harv.ops)

**Code reference:** `harvop_db(iharvop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L111)).

The name of the harvest operation is a primary key referenced when harvest operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **harv.ops** file must be unique.

| Name           | Description                           |
| -------------- | ------------------------------------- |
| forest\_cut    | Cutting of forest                     |
| grain          | Grain harvest                         |
| grass\_bag     | Grass mowing (removing the clippings) |
| grass\_mulch   | Grass mowing (leaving the clippings)  |
| hay\_cut\_high | Hay cutting (high)                    |
| hay\_cut\_low  | Hay cutting (low)                     |
| orchard        | Orchard fruit harvest                 |
| peanuts        | Peanut harvest                        |
| tuber          | Tuber harvest                         |
| silage         | Silage harvest                        |
| stover\_high   | Stover harvest (high)                 |
| stover\_low    | Stover harvest (low)                  |
| stover\_med    | Stover harvest (medium)               |
| vegetables     | Vegetable harvest                     |
| cotton\_picker | Cotton harvest (picker)               |
| cotton\_strip  | Cotton harvest (stripper)             |
