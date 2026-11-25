---
description: "Average daily solar radiation"
---

# solarad

**Code reference:** `hpw_d(j)%solrad = w%solrad` ([assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L866); [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L213)).

Daily station solar radiation after the monthly radiation adjustment and the zero floor. Longer-period rows average the daily values. [Climate adjustment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_control.f90#L268-L274) [Daily calculations](plant-weather-output.md#daily-weather-and-heat-units)

**Unit:** MJ/m2 (megajoules per square metre). The printed source units row spells this `mj/m^2`; it does not mean millijoules.

[Back to the plant and weather schema](plant-weather-output.md).
