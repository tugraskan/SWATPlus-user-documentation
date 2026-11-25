---
description: "Number of source objects providing manure to this allocation object"
---

# src\_obs

**Code reference:** `mallo(imro)%src_obs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_module.f90#L60), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L51)).

Integer count (default `0`) of manure source objects in the allocation block. It allocates `mallo(imro)%src` and `withdr` arrays and controls reading source rows in [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L56-L88) as well as source loops in [`manure_source_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_source_output.f90#L14) and [`manure_demand_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_demand_output.f90#L16).
