---
description: Harvest operation name
---

# name (harv.ops)

**Code reference:** `harvop_db(iharvop)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L111), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_harvops.f90#L44)).

The name of the harvest operation is a primary key matched when harvest or harvest-and-kill operations are scheduled in [**management.sch**](../../landuse-and-management/management.sch/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L71-L81)) or [**lum.dtl**](../../decision-tables/lum.dtl/README.md) ([`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L115-L125)). All names in **harv.ops** must be unique.

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
