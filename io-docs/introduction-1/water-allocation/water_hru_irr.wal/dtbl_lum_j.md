---
description: "Decision table name for the j-th HRU"
---

# dtbl_lum(j)

**Code reference:** `hruirr_db(irr)%dtbl_lum(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L62), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L45)).

25-character name of a landuse-management decision table in [lum.dtl](../../decision-tables/lum.dtl/README.md) (`dtbl_lum`). Copied into `pou(ipou)%irr%dtbl_lum(ihru)` and crosswalked into `dtbl_num(ihru)` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L130-L136). On SWAT+ dev it is evaluated once per delivery in [`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L41-L48); its `irr_wallo` action sets the HRU irrigation demand, application and runoff ([`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L242-L260)).
