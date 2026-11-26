---
description: "Place-of-use array index"
---

# ip

**Code reference:** `ipou / ip` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L23-L24), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L65-L69)).

First integer token on each POU record. In [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L65-L69), the reader reads the token into `ipou` to select the `pou(ipou)` array slot, backspaces one record, and rereads the line with the first column placed into local `ip` (which is not referenced afterward).
