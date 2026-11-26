---
description: "Number of records"
---

# imax

**Code reference:** `imax / db_mx%out_rcv` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L37,L39)).

Number of outside-basin receiving object records in `outside_rcv.wal` (stored in `db_mx%out_rcv` to allocate `orcv` in [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L42)). Note that [`water_orcv_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_orcv_read.f90#L1-L54) is not called in SWAT+ main (`6f515368`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
