---
description: "Flow-control decision table name for POR fractions"
---

# dtbl_por_fr

**Code reference:** `pou(ipou)%dtbl_por_fr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L81), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L71)).

25-character name of a flow-control decision table in [flo_con.dtl](../../decision-tables/flo_con.dtl/README.md) (`dtbl_flo`), or `"null"` to use constant input fractions. Crosswalked into `dtbl_por_fr_num` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L152-L160). When active (`dtbl_por_fr_num > 0`), [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L189-L202) updates each POR's `frac` daily from `trn_fr(ipor)`; otherwise constant [frac](por_frac.md) is kept.
