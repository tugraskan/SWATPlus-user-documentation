---
description: "Place-of-use object type"
---

# typ

**Code reference:** `pou(ipou)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L69), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L69)).

10-character POU type code (default: `""`). During delivery in [`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L32-L147), SWAT+ dispatches on `irr`, `cha`, `res`, `aqu`, `wtp`, `use`, `wtow`, `can`, and `orcv`.

When `typ == "irr"`, [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L122-L138) links the HRUs and landuse-management decision tables from [water_hru_irr.wal](../water_hru_irr.wal/README.md), and on SWAT+ dev [`wallo_pou_deliv.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L36-L101) evaluates each HRU's decision table, sums the irrigation demand and supplies HRUs while water and `rate_max` allow. For POUs with `pods == 0`, [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L96-L107) directly runs `wtp` and `use` treatment/use and returns. Additionally, `typ == "wtp"` bypasses uniform POR fraction scaling in [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L24-L28) because [`wallo_treatment.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treatment.f90#L61-L85) treats each POR separately.
