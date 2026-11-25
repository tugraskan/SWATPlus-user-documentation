---
description: "Number of places of use (POUs) served by the POD"
---

# pous

**Code reference:** `pod(ipod)%pous` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L106), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L212,L221)).

Number of repeated 6-field POU groups appended to this POD row (default: `0`). Read first into local `ipous` ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L212)) to allocate `pod(ipod)%pou`, then reread after `backspace` ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_allocation_read.f90#L219-L221)). Bounds loops over served POUs in [`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L20,L29).
