---
description: "Number of records"
---

# imax

**Code reference:** `imax / db_mx%stor` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L15), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L31,L33)).

Number of water-tower records in `water_tower.wal` (stored in `db_mx%stor`). Allocates `wtow`, `wtow_om_stor`, `wtow_om_out`, and `wtow_cs_stor` in [`water_tower_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L36-L39), and bounds the start-of-day water-tower allocation loop in [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L111).
