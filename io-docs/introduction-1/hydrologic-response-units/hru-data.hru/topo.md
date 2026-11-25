---
description: Pointer to the topography file
---

# topo

**Code reference:** `hru_db(i)%dbsc%topo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L160)).

The pointer to the topography file is a foreign key referencing [name](../../hydrology/topography.hyd/name.md) in [**topography.hyd**](../../hydrology/topography.hyd/). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L132-L139) matches the name, and [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L30-L38) copies the record to the HRU.

If the name matches no record, the HRU silently keeps the first record in topography.hyd: the index starts at 1, so the "not found" check for 0 never triggers ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)). Check the spelling of this name.
