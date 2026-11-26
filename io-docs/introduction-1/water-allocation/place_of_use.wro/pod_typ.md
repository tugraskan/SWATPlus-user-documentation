---
description: "Type of POD within the POU record"
---

# typ (POD)

**Code reference:** `pou(ipou)%pod(ipod)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L95)).

10-character POD source type label (default: `""`). Active source dispatch in [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L43-L129) uses `pod(ipod)%typ` from [point_of_diver.wro](../point_of_diver.wro/README.md), not this POU-level copy.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
