---
description: >-
  Biomass-energy ratio corresponding to the 2nd point on the radiation use
  efficiency curve
---

# bm\_e\_hi

**Code reference:** `pldb(ic)%bioehi` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L72)).

**Current use:** the second point of the CO2 response curve, used only when the basin CO2 value is above 350 ppm ([`pl_biomass_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_biomass_gro.f90#L43-L48)).

The 1st point on the radiation use efficiency curve is comprised of the ambient CO2 concentration, 330 μL CO2/L air, and the biomass-energy ratio reported for [bm\_e](untitled-17.md).

Please read the explanation for parameters [co2\_hi](co2_hi.md) and [bm\_e](untitled-17.md) to obtain additional information about this parameter and methods used to measure it.
