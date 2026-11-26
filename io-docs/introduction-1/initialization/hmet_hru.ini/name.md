---
description: "Record name (read and crosswalked, but not used in simulation in main 6f515368)"
---

# name

**Code reference:** `hmet_soil_ini(ihmeti)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L290)).

Name of the HRU heavy-metal initialization set, read in [`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L57). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L109-L110) matches it against [hmet](../soil_plant.ini/hmet.md) in [**soil\_plant.ini**](../soil_plant.ini/) to set `sol_plt_ini(isp_ini)%hmet`, which is never subsequently read.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
