---
description: "Number of demand objects receiving manure from this allocation object"
---

# trn\_obs

**Code reference:** `mallo(imro)%trn_obs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L61), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L52)).

Integer count (default `0`) of manure demand (receiving) objects in the allocation block. It allocates `mallo(imro)%trn` and controls receiver row reading in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L58-L83), daily demand evaluation and application in [`mallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mallo_control.f90#L39-L51), and demand reporting in [`manure_demand_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_demand_output.f90#L14).
