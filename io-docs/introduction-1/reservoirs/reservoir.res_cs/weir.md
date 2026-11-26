---
description: "Weir input name linked to this reservoir (not used)"
---

# weir

**Code reference:** `res_dat_c_cs(ires)%weir` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L19)).

Character name parsed into `res_dat_c_cs(ires)%weir` by [`res_read_salt_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_salt_cs.f90#L43). `res_dat%weir` is never assigned or read during simulation; reservoir weir releases are instead linked through [**res\_rel.dtl**](../../decision-tables/res_rel.dtl/).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
