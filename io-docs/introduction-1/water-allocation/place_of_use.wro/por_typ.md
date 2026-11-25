---
description: "POR receiving object type"
---

# typ (POR)

**Code reference:** `pou(ipou)%por(ipor)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L38), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104)).

10-character receiving object type code (default: `""`). Dispatched in [`wallo_return.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_return.f90#L30-L68) to route return flows to `cha` (`ob%trans`), `res`, `aqu`, `wtp` (`wtp_om_stor`), `use` (`wuse_om_stor`), `wtow` (`wtow_om_stor`), `can` (`canal_om_stor`), `orcv` (`orcv_om`), or `hru` (no-op in `6f515368`).
