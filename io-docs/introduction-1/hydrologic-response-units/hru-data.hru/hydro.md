---
description: Pointer to the hydrology file
---

# hydro

**Code reference:** `hru_db(i)%dbsc%hyd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L161)).

The pointer to the hydrology file is a foreign key referencing [name](../../hydrology/hydrology.hyd/name.md) in [**hydrology.hyd**](../../hydrology/hydrology.hyd/). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L141-L148) matches the name, and [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L34-L46) copies the record to the HRU.

If the name matches no record, the HRU silently keeps the first record in hydrology.hyd: the index starts at 1, so the "not found" check for 0 never triggers ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)). Check the spelling of this name.
