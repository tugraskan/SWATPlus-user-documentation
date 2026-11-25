---
description: CO2 concentration in the atmosphere at start of simulation
---

# co2

**Code reference:** `bsn_prm%co2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L131), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Atmospheric CO2 concentration (`ppm`, default `400`, range `>=100`; values `< 100.` are reset to `400.` in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L51)).

When [**co2\_yr.dat**](../../climate/co2_yr.dat/) is absent or contains zero rows, [`co2_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/co2_read.f90#L70-L75) assigns `bsn_prm%co2` to every simulation year in `co2y`. The annual CO2 concentration adjusts canopy resistance in Penman-Monteith PET ([`et_pot.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L187), [`#L251`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L251)), and `bsn_prm%co2 > 350.` enables CO2 radiation-use efficiency adjustment in [`pl_biomass_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_biomass_gro.f90#L43-L45).
