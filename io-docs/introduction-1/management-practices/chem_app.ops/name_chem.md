---
description: Chemical application name
---

# name (chem\_app.ops)

**Code reference:** `chemapp_db(ichemapp)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L98), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_chemapp.f90#L45)).

The name of the chemical application is a primary key matched when fertilizer, manure, or pesticide applications are scheduled in [**management.sch**](../../landuse-and-management/management.sch/README.md) ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L120-L153)), [**lum.dtl**](../../decision-tables/lum.dtl/README.md) ([`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L184-L251), [`hru_dtbl_actions_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_dtbl_actions_init.f90#L84-L85)), or manure allocation ([`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L105-L106)). All names in **chem\_app.ops** must be unique.

| Name           | Description |
| -------------- | ----------- |
| broadcast      |             |
| band           |             |
| foliar         |             |
| inject         |             |
| aerial\_liquid |             |
| aerial\_solid  |             |
| drill          |             |
| side\_dress    |             |
| fertigate      |             |
| basal          |             |
| rope\_wick     |             |
| tree\_inject   |             |
