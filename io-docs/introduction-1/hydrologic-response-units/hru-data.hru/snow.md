---
description: Pointer to the snow file
---

# snow

**Code reference:** `hru_db(i)%dbsc%snow` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L166)).

The pointer to the snow file is a foreign key referencing [name](../../hydrology/snow.sno/name.md) in [**snow.sno**](../../hydrology/snow.sno/). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L159-L166) matches the name, and [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L49-L52) copies the snow parameters to the HRU.

An unmatched name keeps the first record in snow.sno without a warning. `null` also leaves the first record selected; it does not turn snow processes off ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)).
