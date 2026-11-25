---
description: "Flow-control decision table name for POD fractions"
---

# dtbl_pod_fr

**Code reference:** `pou(ipou)%dtbl_pod_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L79), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L71)).

25-character name of a flow-control decision table in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`dtbl_flo`), or `"null"` to use constant input fractions. Crosswalked into `dtbl_pod_fr_num` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L141-L149). When active (`dtbl_pod_fr_num > 0`), [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L167-L178) overwrites each POD's `frac` with `trn_fr(ipod)` and sets its daily duty to `trn_fr(ipod) * pou(ipou)%demand`; otherwise constant [frac](pod_frac.md) is used ([`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L181-L185)).
