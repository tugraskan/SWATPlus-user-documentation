---
description: ID of the routing unit
---

# id (rout\_unit.rtu)

**Code reference:** `i`, `k` ([`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L22-L24), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L227-L230)).

The ID of the Routing Unit is a primary key referenced by [hru](../../connectivity/hru.con/hru.md) in [**rout\_unit.con**](../../connectivity/hru.con/). All IDs in the **rout\_unit.rtu** file must be unique.

During input parsing, `id` directly indexes the `ru(i)` array (`1` to `sp_ob%ru`), and reading terminates if a row has `id == 0` ([`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L46)).
