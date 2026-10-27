---
description: Pointer to the topography file
---

# topo

**Code reference:** `ru(i)%dbsc%toposub_db` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_module.f90#L14)).

The pointer to the topography file is a foreign key referencing [name](../../hydrology/topography.hyd/name.md) in [**topography.hyd**](../../hydrology/topography.hyd/).

The topography variables for Routing Units are used to compute time of concentration for sub-daily routing.
