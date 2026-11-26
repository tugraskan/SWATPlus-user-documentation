---
description: "Decision table name"
---

# name

**Code reference:** `dtbl_flo(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L29)).

Name of the decision table, up to 40 characters. Water allocation, saturated buffer, and connectivity inputs select a table by this name; unmatched names give no warning. Water allocation evaluates these tables for [dtbl_mx](../../water-allocation/place_of_use.wro/dtbl_mx.md), [dtbl_pod_fr](../../water-allocation/place_of_use.wro/dtbl_pod_fr.md), and [dtbl_por_fr](../../water-allocation/place_of_use.wro/dtbl_por_fr.md); saturated buffers evaluate the table named in [satbuffer.str](../../structural-practices/satbuffer.str/README.md). [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L152-L202) · [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L637-L652)

Outside-source, water-use, and treatment records with type `dtbl` also match their `org_min_name` here, but the simulation then uses the matched position to index the `lum.dtl` tables. [`water_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_osrc_read.f90#L67-L74) · [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L61-L66)
