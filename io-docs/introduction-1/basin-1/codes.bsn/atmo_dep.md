---
description: Legacy atmospheric deposition code (read but not used in main 6f515368)
---

# atmo\_dep

**Code reference:** `bsn_cc%atmo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L66), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Legacy 1-character string placeholder for atmospheric deposition timestep (struct default `"a"`). Atmospheric deposition is instead configured through [**atmo.cli**](../../climate/atmo.cli/) and linked per weather station in [**weather-sta.cli**](../../climate/weather-sta.cli/).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
