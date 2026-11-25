---
description: Pointer to the soil file
---

# soil

**Code reference:** `hru_db(i)%dbsc%soil` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L162)).

The pointer to the soil file is a foreign key referencing [name](../../soils/soils.sol/name-soils.sol.md) in [**soils.sol**](../../soils/soils.sol/) ([`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L150-L157)).

If the name matches no record, the HRU silently keeps the first record in soils.sol: the index starts at 1, so the "not found" check for 0 never triggers ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)). Check the spelling of this name.
